---
title: Habilitar o GitHub Packeges com o MinIO
intro: 'Configure {% data variables.product.prodname_registry %} com o MinIO como seu armazenamento externo.'
versions:
  ghes: '*'
type: tutorial
topics:
  - Enterprise
  - Packages
  - Storage
shortTitle: Enable Packages with MinIO
ms.openlocfilehash: 2e7d76ee696dfbcd2369c577ef2d2ee803a09638
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '145094907'
---
{% warning %}

**Avisos:**
- É fundamental que você defina as políticas de acesso restritivas necessárias para o seu bucket de armazenamento, porque {% data variables.product.company_short %} não aplica permissões específicas de objeto ou listas de controle de acesso adicionais (ACLs) à sua configuração do bucket de armazenamento. Por exemplo, se você tornar o seu bucket público, os dados no bucket poderão ser acessados através da Internet pública.
- Recomendamos usar um bucket dedicado para {% data variables.product.prodname_registry %}, separar do bucket que você usa para o armazenamento de {% data variables.product.prodname_actions %}.
- Certifique-se de configurar o bucket que você vai querer usar no futuro. Não recomendamos alterar seu armazenamento depois de começar a usar {% data variables.product.prodname_registry %}.

{% endwarning %}

## Pré-requisitos

Antes de poder habilitar e configurar {% data variables.product.prodname_registry %} em {% data variables.product.product_location_enterprise %}, você precisa preparar seu grupo de armazenamento do MinIO. Para ajudar você a configurar rapidamente um bucket do MinIO e navegar pelas opções de personalização do MinIO, confira o "[Guia de início rápido para configurar o bucket de armazenamento do MinIO para o {% data variables.product.prodname_registry %}](/admin/packages/quickstart-for-configuring-your-minio-storage-bucket-for-github-packages)".

Certifique-se de que que o seu ID da chave de acesso e o segredo de armazenamento externo do MinIO tenham essas permissões:
  - `s3:PutObject`
  - `s3:GetObject`
  - `s3:ListBucketMultipartUploads`
  - `s3:ListMultipartUploadParts`
  - `s3:AbortMultipartUpload`
  - `s3:DeleteObject`
  - `s3:ListBucket`

## Habilitar {% data variables.product.prodname_registry %} com armazenamento externo do MinIO

Embora o MinIO atualmente não apareça na interface do usuário em "Armazenamento de Pacote", ele ainda é compatível com {% data variables.product.prodname_registry %} em {% data variables.product.prodname_enterprise %}. Além disso, observe que o armazenamento de objetos do MinIO é compatível com a API do S3 e você pode inserir detalhes do bucket do MinIO no lugar dos detalhes do AWS S3.

{% data reusables.enterprise_site_admin_settings.access-settings %} {% data reusables.enterprise_site_admin_settings.management-console %} {% data reusables.enterprise_site_admin_settings.packages-tab %} {% data reusables.package_registry.enable-enterprise-github-packages %}

{% ifversion ghes %}
1. Em "Armazenamento de Pacotes", selecione **Amazon S3**.
1. Insira os detalhes do seu bucket de armazenamento do MinIO nas configurações de armazenamento do AWS.
    - **URL de Serviço da AWS:** a URL de hospedagem do bucket do MinIO.
    - **Bucket da AWS S3:** o nome do bucket do MinIO compatível com a S3 dedicado ao {% data variables.product.prodname_registry %}.
    - **Chave de Acesso da AWS S3** e **Chave Secreta da AWS S3**: insira a ID da chave de acesso e a chave secreta do MinIO para acessar o bucket.

    ![Caixas de entrada usadas para os detalhes do bucket da S3 AWS](/assets/images/help/package-registry/s3-aws-storage-bucket-details.png) {% endif %} {% data reusables.enterprise_management_console.save-settings %}

## Próximas etapas

{% data reusables.package_registry.next-steps-for-packages-enterprise-setup %}
