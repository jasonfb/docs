---
title: Habilitar o acesso automático a GitHub.com usando o GitHub Connect
intro: 'Para permitir que {% data variables.product.prodname_actions %} na sua empresa use ações a partir de {% data variables.product.prodname_dotcom_the_website %}, você pode conectar a sua instância corporativa a {% data variables.product.prodname_ghe_cloud %}.'
permissions: 'Enterprise owners can enable access to all {% data variables.product.prodname_dotcom_the_website %} actions.'
redirect_from:
  - /enterprise/admin/github-actions/enabling-automatic-access-to-githubcom-actions-using-github-connect
  - /admin/github-actions/enabling-automatic-access-to-githubcom-actions-using-github-connect
versions:
  ghes: '*'
  ghae: '*'
type: how_to
topics:
  - Actions
  - Enterprise
  - GitHub Connect
shortTitle: Use GitHub Connect for actions
ms.openlocfilehash: 85942d047f8bce5c2f58e8f92148b5fb85f5d871
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '145095896'
---
{% data reusables.actions.enterprise-beta %} {% data reusables.actions.enterprise-github-hosted-runners %}

## Sobre o acesso automático a ações de {% data variables.product.prodname_dotcom_the_website %}

Por padrão, os fluxos de trabalho de {% data variables.product.prodname_actions %} no {% data variables.product.product_name %} não podem usar ações diretamente do {% data variables.product.prodname_dotcom_the_website %} ou [{% data variables.product.prodname_marketplace %}](https://github.com/marketplace?type=actions). Para tornar todas as ações de {% data variables.product.prodname_dotcom_the_website %} disponíveis na sua instância corporativa, você pode usar {% data variables.product.prodname_github_connect %} para integrar o {% data variables.product.product_name %} ao {% data variables.product.prodname_ghe_cloud %}. 

{% data reusables.actions.self-hosted-runner-networking-to-dotcom %}

Como alternativa, se você quiser ter um controle mais rigoroso sobre as ações que são permitidas na sua empresa, faça o download e sincronize manualmente as ações na instância da sua empresa usando a ferramenta `actions-sync`. Para obter mais informações, confira "[Como sincronizar as ações manualmente no {% data variables.product.prodname_dotcom_the_website %}](/enterprise/admin/github-actions/manually-syncing-actions-from-githubcom)".

## Sobre resolução para ações usando {% data variables.product.prodname_github_connect %}

{% data reusables.actions.github-connect-resolution %}

Se um usuário tiver criado uma organização e um repositório em sua empresa, que corresponde a uma organização e nome do repositório em {% data variables.product.prodname_dotcom_the_website %}, o repositório da sua empresa será usado em vez do repositório de {% data variables.product.prodname_dotcom_the_website %}. {% ifversion ghes < 3.3 or ghae %}Um usuário mal intencionado poderia aproveitar esse comportamento para executar um código como parte de um fluxo de trabalho{% else %}Para obter mais informações, confira "[Desativação automática de namespaces para ações acessadas no {% data variables.product.prodname_dotcom_the_website%}](#automatic-retirement-of-namespaces-for-actions-accessed-on-githubcom)".
{% endif %}

## Habilitar o acesso automático a todas as ações de {% data variables.product.prodname_dotcom_the_website %}

Antes de permitir o acesso a todas as ações de {% data variables.product.prodname_dotcom_the_website %} para sua empresa, você deve {% ifversion ghes %}:
- Configure {% data variables.product.product_location %} para usar {% data variables.product.prodname_actions %}. Para obter mais informações, confira "[Introdução ao {% data variables.product.prodname_actions %} para GitHub Enterprise Server](/admin/github-actions/enabling-github-actions-for-github-enterprise-server/getting-started-with-github-actions-for-github-enterprise-server)".
- Habilitar {% else %} habilitar{% endif %} {% data variables.product.prodname_github_connect %}. Para obter mais informações, confira "[Como gerenciar o {% data variables.product.prodname_github_connect %}](/admin/configuration/configuring-github-connect/managing-github-connect)".

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.github-connect-tab %}
1. Em "Usuários podem utilizar ações do GitHub.com em execuções de fluxo de trabalho", use o menu suspenso e selecione **Habilitado**.
  ![Menu suspenso para ações do GitHub.com em execuções do fluxos de trabalho](/assets/images/enterprise/site-admin-settings/enable-marketplace-actions-drop-down-ae.png)
1. {% data reusables.actions.enterprise-limit-actions-use %}

{% ifversion ghes > 3.2 or ghae %}

## Retirada automática de namespaces para ações acessadas em {% data variables.product.prodname_dotcom_the_website %}

Ao habilitar {% data variables.product.prodname_github_connect %}, os usuários não verão nenhuma alteração no comportamento para fluxos de trabalho existentes porque {% data variables.product.prodname_actions %} procura {% data variables.product.product_location %} para cada ação antes de voltar a {% data variables.product.prodname_dotcom_the_website%}. Isso garante que todas as versões personalizadas de ações que a sua empresa criou sejam usadas em preferência para suas contrapartes em {% data variables.product.prodname_dotcom_the_website%}.

A desativação automática de namespaces para ações acessadas em {% data variables.product.prodname_dotcom_the_website %} bloqueia o potencial de um ataque de um intermediário por um usuário malicioso com acesso a {% data variables.product.product_location %}. Quando uma ação em {% data variables.product.prodname_dotcom_the_website %} é usada pela primeira vez, esse namespace fica desativado em {% data variables.product.product_location %}. Isso bloqueia qualquer usuário que criar uma organização e repositório na sua empresa que corresponda a essa organização e nome do repositório em {% data variables.product.prodname_dotcom_the_website %}. Isso garante que, quando um fluxo de trabalho é executado, a ação pretendida é sempre executada.

Depois de usar uma ação de {% data variables.product.prodname_dotcom_the_website %}, se você deseja criar uma ação em {% data variables.product.product_location %} com o mesmo nome, primeiro você precisa tornar o namespace para a organização e repositório disponíveis.

{% data reusables.enterprise_site_admin_settings.access-settings %}
2. Na barra lateral à esquerda, em **Administrador do site**, clique em **Namespaces desativados**.
3. Localize o namespace que você quer usar no {% data variables.product.product_location %} e clique em **Cancelar desativação**.
   ![Cancelar desativação do namespace](/assets/images/enterprise/site-admin-settings/unretire-namespace.png)
4. Acesse a organização relevante e crie um novo repositório.

   {% tip %}

   **Dica:** quando você cancelar a desativação de um namespace, sempre crie o novo repositório com esse nome o mais rápido possível. Se um fluxo de trabalho chamar a ação associada em {% data variables.product.prodname_dotcom_the_website %} antes de criar o repositório local, o namespace será desativado novamente. Para ações usadas em fluxos de trabalho frequentemente, você pode considerar que um namespace foi desativado novamente antes de ter tempo para criar o repositório local. Neste caso, você pode desabilitar temporariamente os fluxos de trabalho relevantes até criar o novo repositório.

   {% endtip %}

{% endif %}
