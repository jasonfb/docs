---
ms.openlocfilehash: 67ef84929e93a9f0fa1acc99e2035b2d62cb1574
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: "145065401"
---
O fluxo de trabalho configura um contêiner de serviço com o rótulo `postgres`. Todos os serviços precisam ser executados em um contêiner, ou seja, cada serviço exige que você especifique o contêiner `image`. Este exemplo usa a imagem de contêiner `postgres`, fornece a senha padrão do PostgreSQL e inclui opções de verificação de integridade para verificar se o serviço está em execução. Para obter mais informações, confira a [imagem do Postgres](https://hub.docker.com/_/postgres) no Docker Hub.
