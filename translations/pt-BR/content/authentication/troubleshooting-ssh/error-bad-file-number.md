---
title: 'Erro: número de arquivo inadequado'
intro: Este erro normalmente significa que você não conseguiu se conectar ao servidor. Quase sempre isso é causado por firewalls e servidores proxy.
redirect_from:
  - /articles/error-bad-file-number
  - /github/authenticating-to-github/error-bad-file-number
  - /github/authenticating-to-github/troubleshooting-ssh/error-bad-file-number
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - SSH
ms.openlocfilehash: db2a47ad6029790cdbf9f0212087acc659326941
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '145083556'
---
Ao executar SSH ou comandos do Git remotos, o tempo limite da conexão pode expirar:

```shell
$ ssh -vT git@{% data variables.command_line.codeblock %}
> OpenSSH_8.1p1, LibreSSL 2.7.3
> debug1: Connecting to {% data variables.command_line.codeblock %} [207.97.227.239] port 22.
> debug1: connect to address 207.97.227.239 port 22: Connection timed out
> ssh: connect to host {% data variables.command_line.codeblock %} port 22: Connection timed out
> ssh: connect to host {% data variables.command_line.codeblock %} port 22: Bad file number
```

## Resolver o problema

### Usar HTTPS

Geralmente, a solução mais simples é simplesmente evitar SSH por completo. A maioria dos firewalls e proxies permite tráfego HTTPS sem problemas. Para aproveitar isso, altere [a URL remota](/github/getting-started-with-github/about-remote-repositories) que está sendo usada:

```shell
$ git clone https://{% data variables.command_line.codeblock %}/<em>username</em>/<em>reponame</em>.git
> Cloning into 'reponame'...
> remote: Counting objects: 84, done.
> remote: Compressing objects: 100% (45/45), done.
> remote: Total 84 (delta 43), reused 78 (delta 37)
> Unpacking objects: 100% (84/84), done.
```

### Testar em outra rede

Se você conectar o computador a outra rede que não tem firewall, conseguirá testar sua conexão SSH com o {% data variables.product.product_name %}. Se tudo funcionar como deveria, entre em contato o administrador de rede para saber como alterar as configurações de firewall e conseguir estabelecer conexão SSH com o {% data variables.product.product_name %}.

{% ifversion fpt or ghec %}

### Usar SSH na porta HTTPS

Se o uso de HTTPS não for uma opção e o administrador do firewall se recusar a permitir conexões SSH, experimente usar o [SSH na porta HTTPS](/articles/using-ssh-over-the-https-port).

{% endif %}

{% ifversion fpt or ghec %}

## Leitura adicional

- "[Solução de problemas de conectividade](/articles/troubleshooting-connectivity-problems)"

{% endif %}
