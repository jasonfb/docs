---
title: GitHub Marketplace API 的 REST 端点
intro: '要帮助管理 {% data variables.product.prodname_marketplace %} 上的应用程序，请使用这些 {% data variables.product.prodname_marketplace %} API 端点。'
redirect_from:
  - /apps/marketplace/github-marketplace-api-endpoints
  - /apps/marketplace/integrating-with-the-github-marketplace-api/github-marketplace-rest-api-endpoints
  - /marketplace/integrating-with-the-github-marketplace-api/github-marketplace-rest-api-endpoints
  - /developers/github-marketplace/rest-endpoints-for-the-github-marketplace-api
versions:
  fpt: '*'
  ghec: '*'
topics:
  - Marketplace
shortTitle: REST API
ms.openlocfilehash: aac7df5600863521c482b8a13c31abf8fd103ecf
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: '145098016'
---
以下是一些可用于 Marketplace 上架产品的有用端点：

* [列出计划](/rest/reference/apps#list-plans)
* [列出计划的帐户](/rest/reference/apps#list-accounts-for-a-plan)
* [获取帐户的订阅计划](/rest/reference/apps#get-a-subscription-plan-for-an-account)
* [列出经验证用户的订阅](/rest/reference/apps#list-subscriptions-for-the-authenticated-user)

有关在使用 {% data variables.product.prodname_marketplace %} API 时如何进行身份验证的详细信息，请参阅以下页面：

* [OAuth 应用程序的授权选项](/apps/building-oauth-apps/authorizing-oauth-apps/)
* [GitHub 应用程序的身份验证选项](/apps/building-github-apps/authenticating-with-github-apps/)

{% note %}

**注意**：[REST API 的速率限制](/rest/overview/resources-in-the-rest-api#rate-limiting)适用于所有 {% data variables.product.prodname_marketplace %} API 终结点。

{% endnote %}
