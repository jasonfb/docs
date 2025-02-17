---
title: Solucionar problemas de consultas de pesquisa
intro: 'Se você encontrar resultados inesperados ao pesquisar no {% data variables.product.product_name %}, poderá solucionar os problemas analisando problemas comuns e limitações.'
redirect_from:
  - /articles/troubleshooting-search-queries
  - /github/searching-for-information-on-github/troubleshooting-search-queries
  - /github/searching-for-information-on-github/getting-started-with-searching-on-github/troubleshooting-search-queries
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - GitHub search
shortTitle: Troubleshoot search queries
ms.openlocfilehash: 2c90d144401974ebc44f4b80a1509593fe987329
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '145095532'
---
## Possíveis tempos limite

Algumas consultas têm uma computação dispendiosa para a nossa infraestrutura de pesquisa executar. Para manter a pesquisa rápida para todos, limitamos o tempo de execução das consultas individuais. Nas raras situações em que uma consulta excede o tempo limite, a pesquisa retorna todas as correspondências encontradas antes do tempo limite e informa a ocorrência dele.

Atingir um tempo limite não significa necessariamente que os resultados da pesquisa estão incompletos. Significa apenas que a consulta foi interrompida antes que ela pesquisasse todos os dados possíveis.

## Limitações no tamanho da consulta

Há alguns limites no tamanho das consultas ao pesquisar no {% data variables.product.product_name %}:

* Não são aceitas consultas com mais de 256 caracteres
* Não é possível construir uma consulta usando mais de cinco operadores `AND`, `OR` ou `NOT`

Determinados tipos de pesquisa, como pesquisa de código, podem ter limitações adicionais. Consulte a documentação desses tipos de pesquisa para obter mais informações.

## Leitura adicional

- "[Sobre a pesquisa no GitHub](/search-github/getting-started-with-searching-on-github/about-searching-on-github)"
