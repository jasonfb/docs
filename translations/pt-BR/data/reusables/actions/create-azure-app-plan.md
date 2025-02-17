---
ms.openlocfilehash: 6058de00ebbc05baaa2e29cfba275fa2249b44a3
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: "145095043"
---
1. Criar um Plano do Serviço de Aplicativo do Azure.

   Por exemplo, você pode usar o CLI do Azure para criar um novo plano de App Service:

   ```bash{:copy}
   az appservice plan create \
      --resource-group MY_RESOURCE_GROUP \
      --name MY_APP_SERVICE_PLAN \
      --is-linux
   ```

   No comando acima, substitua `MY_RESOURCE_GROUP` pelo grupo de recursos preexistente do Azure e `MY_APP_SERVICE_PLAN` por um novo nome para o Plano do Serviço de Aplicativo.

   Confira a documentação do Azure para obter mais informações sobre como usar a [CLI do Azure](https://docs.microsoft.com/cli/azure/):

   * Para autenticação, confira "[Conectar-se com a CLI do Azure](https://docs.microsoft.com/cli/azure/authenticate-azure-cli)".
   * Caso precise criar um grupo de recursos, confira "[az group](https://docs.microsoft.com/cli/azure/group?view=azure-cli-latest#az_group_create)".
