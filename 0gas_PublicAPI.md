---
title: 0gas Public API v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.17"

---

# 0gas Public API

> v1.0.0

Base URLs:

* <a href="https://api.alienswap.xyz">正式环境: https://api.alienswap.xyz</a>

# 


## 1、GET 列举 collections

GET /api/v1/public/mirror/collections

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|id|query|string| 否 |collection_id|
|slug|query|string| 否 |集合的slug|
|limit|query|integer| 否 |一页返回多少个collection,默认且最多20个|
|sortBy|query|string| 否 |排序字段|
|continuation|query|string| 否 |base64编码的字符串，如果要取下一页要传|
|name|query|string| 否 |集合名字|
|sortDirection|query|string| 否 |传desc,asc|

#### 详细说明

**sortBy**: 排序字段
createdAt
1DayVolume
7DayVolume
30DayVolume
1DaySales
7DaySales
30DaySales
marketCap
floorAskPrice

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "collections": [
      {
        "id": "0x1a9980f50d57c050023c3074adedbf0cea4ed0c9",
        "slug": "shinsei-galverse-official",
        "name": "Shinsei Galverse Official",
        "image": "https://d1ynu5ttzco4qz.cloudfront.net/f8c92e74e3878903f7df2826bbc64dec.jpg",
        "description": "Shinsei Galverse is a collection",
        "externalUrl": "https://www.galverse.art/",
        "discordUrl": null,
        "twitterUsername": null,
        "twitter": null,
        "discord": null,
        "tokenCount": 100,
        "mintCount": 100,
        "mintCount1H": 0,
        "marketCap": 64.70294791666667,
        "onSaleCount": 0,
        "primaryContract": "0x1a9980f50d57c050023c3074adedbf0cea4ed0c9",
        "royalties": {
          "recipient": "0x0c1d9b8a7abd0c1e12d88dedbd4e5b0ef72f3abc",
          "breakdown": [
            {
              "bps": 500,
              "base_bps": 10000,
              "recipient": "0x0c1d9b8a7abd0c1e12d88dedbd4e5b0ef72f3abc"
            }
          ],
          "bps": 500
        },
        "createdAt": "2023-05-19T12:04:29.431000",
        "ownerCount": 4,
        "avgMintPrice": null,
        "mintStartTime": null,
        "mintEndTime": null,
        "mintFeeRecipient": null,
        "mintFee": null,
        "mintPriceRecipient": null,
        "mintPrice": null,
        "mintQtyPerUser": null,
        "preMintStartTime": null,
        "preMintEndTime": null,
        "preMintPriceRecipient": null,
        "source": null,
        "kind": "erc721",
        "isTradingAllowed": true,
        "tradeStartTime": 0,
        "floorAsk": {
          "id": null,
          "price": null,
          "maker": null
        },
        "topBid": {
          "id": "e07e307c04fa11ee8c880e60fa5fa6fd825022e08acb4763a0bd54f91c352f14",
          "price": 1.1,
          "maker": "0x1003F726e9ed99d30f7Cd1dD1cb2a32cC4778257"
        },
        "sales": {
          "1day": 2,
          "7day": 1,
          "30day": 2
        },
        "salesChange": {
          "1day": 0,
          "7day": 0.0909091,
          "30day": 0.0196078
        },
        "volume": {
          "1day": 1.1,
          "7day": 1.1,
          "30day": 1.1,
          "allTime": 85.56717
        },
        "volumeChange": {
          "1day": 0,
          "7day": 0.19530070982930717,
          "30day": 0.013156766339537626
        },
        "averagePrice": {
          "1day": 1,
          "7day": 1,
          "30day": 1
        },
        "averagePriceChange": {
          "1day": 0,
          "7day": 8.19292,
          "30day": 2.07946
        },
        "floorSale": {
          "1day": 0.5,
          "7day": 0.5,
          "30day": 0.5
        },
        "floorSaleChange": {
          "1day": null,
          "7day": null,
          "30day": null
        },
        "is_mirror": true
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» collections|[object]|true|none||none|
|»»» id|string|true|none||none|
|»»» slug|string|true|none||none|
|»»» name|string|true|none||none|
|»»» image|string|true|none||none|
|»»» description|string|true|none||none|
|»»» externalUrl|string|true|none||官网链接
|»»» twitterUsername|string|true|none||twitter用户名|
|»»» discordUrl|string|true|none||discord地址
|»»» tokenCount|integer|true|none||none|
|»»» ownerCount|integer|true|none||none|
|»»» onSaleCount|integer|true|none||none|
|»»» primaryContract|string|true|none||none|
|»»» createdAt|string|true|none||none|
|»»» royalties|object|true|none||none|
|»»»» recipient|string|true|none||none|
|»»»» bps|integer|true|none||none|
|»»»» breakdown|[object]|true|none||none|
|»»»»» recipient|string|true|none||none|
|»»»»» bps|integer|true|none||none|
|»»» floorAsk|object|true|none||none|
|»»»» id|string|true|none||none|
|»»»» price|number|true|none||none|
|»»»» maker|string|true|none||none|
|»»» topBid|object|true|none||none|
|»»»» id|string|true|none||none|
|»»»» price|number|true|none||none|
|»»»» maker|string|true|none||none|
|»»» sales|object|true|none||none|
|»»»» 1day|integer|true|none||none|
|»»»» 7day|integer|true|none||none|
|»»»» 30day|integer|true|none||none|
|»»» salesChange|object|true|none||none|
|»»»» 1day|number|true|none||小数|
|»»»» 7day|number|true|none||none|
|»»»» 30day|number|true|none||none|
|»»» volume|object|false|none||none|
|»»»» 1day|integer|true|none||none|
|»»»» 7day|integer|true|none||none|
|»»»» 30day|integer|true|none||none|
|»»»» allTime|number|true|none||none|
|»»» volumeChange|object|false|none||none|
|»»»» 1day|number|true|none||小数
|»»»» 7day|number|true|none||none|
|»»»» 30day|number|true|none||none|
|»»» averagePrice|object|false|none||none|
|»»»» 1day|integer|true|none||none|
|»»»» 7day|integer|true|none||none|
|»»»» 30day|integer|true|none||none|
|»»» averagePriceChange|object|false|none||none|
|»»»» 1day|number|true|none||小数
|»»»» 7day|number|true|none||none|
|»»»» 30day|number|true|none||none|
|»»» mintStartTime|integer|false|none||开始mint时间|
|»»» mintEndTime|integer|false|none||结束mint时间|
|»»» avgMintPrice|number|true|none||平均铸造价格|
|»»» kind|string|true|none||合约类型|
|»»» mintFeeRecipient|string|true|none||none|
|»»» mintFee|number|true|none||创建平台收|
|»»» mintPriceRecipient|string|true|none||none|
|»»» mintPrice|number|true|none||发行方收|
|»»» source|string|true|none||合集来源|
|»»» mintCount|integer|true|none||合集已经mint的数量|
|»»» mintCount1H|integer|true|none||过去一小时已mint的数量|
|»» continuation|string|true|none||none|

## 2、GET 列举 attributes

GET /api/v1/public/mirror/attributes

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|collection_id|query|string| 否 |集合id|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": [
    {
      "key": "S-Karrots",
      "attributeCount": 25,
      "kind": "number",
      "values": [
        null
      ]
    },
    {
      "key": "Faction",
      "attributeCount": 7,
      "kind": "string",
      "values": [
        {
          "count": 4,
          "value": "Bunners",
          "floor_sell_value": null
        },
        {
          "count": 18,
          "value": "Cypher Buns",
          "floor_sell_value": null
        },
        {
          "count": 30,
          "value": "Hare Raisers",
          "floor_sell_value": null
        }
      ]
    }
  ]
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» data|[object]|true|none||none|
|»» key|string|true|none||none|
|»» attributeCount|integer|true|none||none|
|»» kind|string|true|none||none|
|»» values|[array]|true|none||none|
|»»» count|integer|true|none||none|
|»»» value|string|true|none||none|
|»»» floor_sell_value|null|true|none||none|

*continued*

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none||none|
|» msg|string|true|none||none|

## 3、GET 列举 bid 订单

GET /api/v1/public/mirror/orders/bid

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|ids|query|string| 否 |order_id，订单id，支持多个|
|token|query|string| 否 |形如 contract:token_id|
|maker|query|string| 否 |none|
|collection|query|string| 否 |collection id|
|limit|query|string| 否 |default 50; max 1000|
|sortBy|query|string| 否 |支持按 createdAt、price 排序|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "orders": [
      {
        "id": "5584b9d8fb0311ed98d00e60fa5fa6fd04897abd40fb465984ecfc74a3615143",
        "side": "buy",
        "status": "active",
        "contract": "0x1a9980f50d57c050023c3074adedbf0cea4ed0c9",
        "maker": "0xB8796EE0DD780882a95aE6FA9574ca2372D2066a",
        "taker": "0x0000000000000000000000000000000000000000",
        "price": {
          "currency": "ETH",
          "amount": 0.01,
          "netAmount": 0.01
        },
        "validFrom": null,
        "validUntil": null,
        "quantityFilled": 0,
        "quantityRemaining": 1,
        "criteria": {
          "kind": "token",
          "data": {
            "token": {
              "tokenId": "2",
              "name": "Hooligan #2",
              "image": "https://test-alien-static.s3.ap-northeast-1.amazonaws.com/files/b3827eb35605f6f79f9de66ece8c7ec1.png"
            },
            "collection": {
              "id": "0x1a9980f50d57c050023c3074adedbf0cea4ed0c9",
              "name": "Shinsei Galverse Official",
              "image": "https://test-alien-static.s3.ap-northeast-1.amazonaws.com/files/f8c92e74e3878903f7df2826bbc64dec.jpg"
            }
          }
        },
        "feeBps": 0,
        "feeBreakdown": [],
        "expiration": null,
        "createdAt": 1685022725664,
        "updatedAt": 1685625648444
      }
    ],
    "continuation": "MTY4NTAyMjcyNTY2NA=="
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» orders|[object]|true|none||none|
|»»» id|string|true|none||collection id|
|»»» side|string|true|none||none|
|»»» status|string|true|none||active|
|»»» contract|string|true|none||none|
|»»» maker|string|true|none||none|
|»»» taker|string|true|none||none|
|»»» price|object|true|none||none|
|»»»» currency|object|true|none||none|
|»»»»» symbol|string|true|none||none|
|»»»»» decimals|string|true|none||none|
|»»» validFrom|string|false|none||none|
|»»» validUntil|string|false|none||none|
|»»» quantityFilled|string|false|none||none|
|»»» quantityRemaining|string|false|none||none|
|»»» criteria|object|false|none||none|
|»»»» kind|string|true|none||none|
|»»»» data|object|true|none||none|
|»»»»» collection|object|true|none||none|
|»»»»»» id|string|true|none||none|
|»»»»»» name|string|true|none||none|
|»»»»»» image|string|true|none||none|
|»»» expiration|string|false|none||none|
|»»» createdAt|string|false|none||none|
|»»» updatedAt|string|false|none||none|

#### 枚举值

|属性|值|
|---|---|
|side|buy|
|side|sell|

## 4、GET 列举用户收到的 top offer

GET /api/v1/public/mirror/orders/users/{user_address}/top-bids

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|user_address|path|string| 是 |none|
|collection|query|string| 否 |collection id|
|limit|query|string| 否 |default 20; max 100|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "topBids": [
      {
        "id": "7945a172029a11ee8c880e60fa5fa6fd8c96e3ff46e14d5ab24aaf6633443232",
        "side": "buy",
        "status": "active",
        "contract": "0x231d3559aa848bf10366fb9868590f01d34bf240",
        "maker": "0xB8796EE0DD780882a95aE6FA9574ca2372D2066a",
        "taker": "0x0000000000000000000000000000000000000000",
        "price": {
          "currency": "ETH",
          "amount": 0.234,
          "netAmount": 0.234
        },
        "validFrom": null,
        "validUntil": null,
        "quantityFilled": 0,
        "quantityRemaining": 1,
        "criteria": {
          "kind": "token",
          "data": {
            "token": {
              "tokenId": "3",
              "name": "meme alien",
              "image": "https://test-alien-static.s3.ap-northeast-1.amazonaws.com/files/747543dcfb3c7aff7d2b0879d6f12c5d.png"
            },
            "collection": {
              "id": "0x231d3559aa848bf10366fb9868590f01d34bf240",
              "name": "bg test col",
              "image": "https://test-alien-static.s3.ap-northeast-1.amazonaws.com/files/ba26d408d531189397b2d692c0183b7a.png"
            }
          }
        },
        "feeBps": 0,
        "feeBreakdown": [],
        "expiration": null,
        "createdAt": 1685857297795,
        "updatedAt": 1685857297795,
        "token": {
          "contract": "0x231d3559aa848bf10366fb9868590f01d34bf240",
          "tokenId": 3,
          "name": "meme alien",
          "image": "https://test-alien-static.s3.ap-northeast-1.amazonaws.com/files/747543dcfb3c7aff7d2b0879d6f12c5d.png",
          "collection": {
            "id": "0x231d3559aa848bf10366fb9868590f01d34bf240",
            "name": "bg test col",
            "imageUrl": "https://test-alien-static.s3.ap-northeast-1.amazonaws.com/files/ba26d408d531189397b2d692c0183b7a.png"
          }
        }
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» topBids|[object]|true|none||none|
|»»» id|string|true|none||collection id|
|»»» side|string|true|none||none|
|»»» status|string|true|none||active|
|»»» contract|string|true|none||none|
|»»» maker|string|true|none||none|
|»»» taker|string|true|none||none|
|»»» price|object|true|none||none|
|»»»» currency|object|true|none||none|
|»»»»» symbol|string|true|none||none|
|»»»»» decimals|string|true|none||none|
|»»» validFrom|string|true|none||none|
|»»» validUntil|string|true|none||none|
|»»» quantityFilled|string|true|none||none|
|»»» quantityRemaining|string|true|none||none|
|»»» criteria|object|true|none||none|
|»»»» kind|string|true|none||none|
|»»»» data|object|true|none||none|
|»»»»» collection|object|true|none||none|
|»»»»»» id|string|true|none||none|
|»»»»»» name|string|true|none||none|
|»»»»»» image|string|true|none||none|
|»»» expiration|string|true|none||none|
|»»» createdAt|string|true|none||none|
|»»» updatedAt|string|true|none||none|
|»»» token|object|true|none||none|
|»»»» contract|string|true|none||none|
|»»»» tokenId|string|true|none||none|
|»»»» name|string|true|none||none|
|»»»» image|string|true|none||none|
|»»»» collection|object|true|none||none|
|»»»»» id|string|true|none||none|
|»»»»» name|string|true|none||none|
|»»»»» imageUrl|string|true|none||none|

#### 枚举值

|属性|值|
|---|---|
|side|buy|
|side|sell|

## 5、GET 列举免 gas 交易的tokens

GET /api/v1/public/mirror/tokens

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|tokens|query|string| 否 |token_id，合约:数字的形式，支持传多个|
|collection|query|string| 否 |集合id，地址小写|
|tokenName|query|string| 否 |token名，支持模糊匹配|
|limit|query|integer| 否 |默认20，最大100|
|sortBy|query|string| 否 |排序字段，目前支持floorAskPrice, createdAt, rarity|
|sortDirection|query|string| 否 |排序顺序，只能传 asc,desc|
|minFloorAskPrice|query|number| 否 |最低挂单价|
|maxFloorAskPrice|query|number| 否 |最高挂单价|
|includeAttributes|query|string| 否 |是否返回 attributes，默认false，如果需要返回则传true|
|includeTopBid|query|string| 否 |是否返回 topbid|
|minCreatedAt|query|integer| 否 |token最小创建时间，查询出来的结果createdAt都比参数大|
|maxCreatedAt|query|integer| 否 |token最大创建时间，查询出来的结果createdAt都比参数小|
|minRarityRank|query|integer| 否 |稀有度排名|
|maxRarityRank|query|integer| 否 |稀有度排名|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "tokens": [
      {
        "token": {
          "tokenState": 0,
          "contract": "0xD8b4e2e9A327AEc87F968AaaF553A07569395202",
          "tokenId": "0",
          "name": "AKB48 Card #0",
          "description": "",
          "image": "https://d1ynu5ttzco4qz.cloudfront.net/fit-in/500x500/files/ae049f850bd0a8142757e889e82140c1.png",
          "media": "https://d1ynu5ttzco4qz.cloudfront.net/fit-in/500x500/files/ae049f850bd0a8142757e889e82140c1.png",
          "mediaType": "image/png",
          "kind": "erc721",
          "supply": 0,
          "remainingSupply": 1,
          "createdAt": 1689664299,
          "mintPrice": null,
          "rarity": 1,
          "rarityRank": null,
          "owner": "0x7e727520B29773e7F23a8665649197aAf064CeF1"
        },
        "market": {
          "floorAsk": {
            "id": null,
            "price": {
              "currency": "ETH",
              "amount": null,
              "netAmount": null
            },
            "maker": null,
            "validFrom": null,
            "validUntil": null
          }
        }
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» tokens|[object]|true|none||none|
|»»» token|object|true|none||none|
|»»»» tokenState|integer|true|none||none|
|»»»» contract|string|true|none||none|
|»»»» tokenId|string|true|none||none|
|»»»» name|string|true|none||none|
|»»»» description|string|true|none||none|
|»»»» image|string|true|none||缩略图|
|»»»» media|string|true|none||资源链接|
|»»»» mediaType|string|true|none||image/video|
|»»»» kind|string|true|none||none|
|»»»» supply|integer|true|none||none|
|»»»» remainingSupply|integer|true|none||none|
|»»»» createdAt|integer|true|none||创建时间/mint时间|
|»»»» mintPrice|string|true|none||token mint出来是花费的价格|
|»»»» rarity|number|true|none||稀有度数值|
|»»»» rarityRank|string|true|none||稀有度排名|
|»»»» owner|string|true|none||none|
|»»» market|object|true|none||none|
|»»»» floorAsk|object|true|none||none|
|»»»»» id|integer|true|none||none|
|»»»»» price|object|true|none|最低挂单价|none|
|»»»»»» currency|string|true|none||none|
|»»»»»» amount|integer|true|none||none|
|»»»»»» netAmount|integer|true|none||none|
|»»»»» maker|string|true|none|挂单人|none|
|»»»»» validFrom|integer|true|none|订单有效期unixts|none|
|»»»»» validUntil|integer|true|none|订单有效期unix ts|none|

## 6、GET 列举免 gas 交易的token activity

GET /api/v1/public/mirror/tokens/{token}/activity

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|token|path|string| 是 |要查询的token，合约:id的形式|
|limit|query|integer| 否 |默认1000，最大1000|
|sortBy|query|string| 否 |排序字段，支持 eventTimestamp | createdAt|
|continuation|query|string| 否 |分页参数|
|types|query|array[string]| 否 |事件类型，目前支持mint, transfer, ask, bid, bid_cancel, ask_cancel, sale|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "activities": [
      {
        "type": "mint",
        "fromAddress": "0x0000000000000000000000000000000000000000",
        "toAddress": "0x38CA4DE19CD5Ec01D3e07468773C12743C7F6c0A",
        "price": null,
        "amount": 1,
        "timestamp": 1684942349916,
        "createdAt": "2023-05-24T15:32:29.916000",
        "contract": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
        "token": {
          "tokenId": 0,
          "tokenName": "Hooligan #0",
          "tokenImage": "https://d1ynu5ttzco4qz.cloudfront.net/fit-in/500x500/files/d634c952fef6937d8e8bba3fabc252b3.jpeg",
          "rarityRank": null,
          "rarityScore": null
        },
        "collection": {
          "collectionId": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
          "collectionName": "Hooligan",
          "collectionImage": "https://test-static.alienswap.xyz/files/a48f83542dcd7c1ac50a0b50733b8440.gif"
        },
        "order": {
          "id": null,
          "side": "mint",
          "is_active": false,
          "criteria": {
            "kind": "token",
            "data": {
              "token": {
                "tokenId": 0,
                "tokenName": "Hooligan #0",
                "tokenImage": "https://d1ynu5ttzco4qz.cloudfront.net/fit-in/500x500/files/d634c952fef6937d8e8bba3fabc252b3.jpeg",
                "rarityRank": null,
                "rarityScore": null
              },
              "collection": {
                "collectionId": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
                "collectionName": "Hooligan",
                "collectionImage": "https://test-static.alienswap.xyz/files/a48f83542dcd7c1ac50a0b50733b8440.gif"
              }
            }
          }
        }
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» activities|[object]|true|none||none|
|»»» type|string|false|none||none|
|»»» fromAddress|string|false|none||none|
|»»» toAddress|string|false|none||none|
|»»» price|null|false|none||none|
|»»» amount|integer|false|none||none|
|»»» timestamp|integer|false|none||none|
|»»» createdAt|string|false|none||none|
|»»» contract|string|false|none||none|
|»»» token|object|false|none||none|
|»»»» tokenId|integer|true|none||none|
|»»»» tokenName|string|true|none||none|
|»»»» tokenImage|string|true|none||none|
|»»»» rarityRank|object|true|none||none|
|»»»» rarityScore|object|true|none||none|
|»»» collection|object|false|none||none|
|»»»» collectionId|string|true|none||none|
|»»»» collectionName|string|true|none||none|
|»»»» collectionImage|string|true|none||none|
|»»» order|object|false|none||none|
|»»»» id|string|true|none|订单uuid|none|
|»»»» is_active|boolean|true|none||none|
|»»»» side|string|true|none|ask/bid|none|
|»»»» criteria|object|true|none||none|
|»»»»» kind|string|true|none|目前只返回token|none|
|»»»»» data|object|true|none||none|
|»»»»»» token|object|true|none||none|
|»»»»»»» tokenId|string|true|none|token的id|none|
|»»»»»»» tokenName|string|true|none|token名称|none|
|»»»»»»» tokenImage|string|true|none|token图片|none|
|»»»»»»» rarityRank|object|true|none||none|
|»»»»»»» rarityScore|object|true|none||none|
|»»»»»» collection|object|true|none||none|
|»»»»»»» collectionId|string|true|none|collection的id|none|
|»»»»»»» collectionName|string|true|none|collection名称|none|
|»»»»»»» collectionImage|string|true|none|collection图片|none|

## 7、GET 列举免 gas 交易的 user activity

GET /api/v1/public/mirror/users/activity

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|limit|query|integer| 否 |默认1000，最大1000|
|sortBy|query|string| 否 |排序字段，支持 eventTimestamp | createdAt|
|continuation|query|string| 否 |分页参数|
|types|query|array[string]| 否 |事件类型，目前支持mint, transfer, ask, bid, bid_cancel, ask_cancel, sale|
|collection|query|array[string]| 否 |collection_id，支持多个|
|users|query|array[string]| 否 |用户地址，支持多个|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "activities": [
      {
        "type": "mint",
        "fromAddress": "0x0000000000000000000000000000000000000000",
        "toAddress": "0x38CA4DE19CD5Ec01D3e07468773C12743C7F6c0A",
        "price": null,
        "amount": 1,
        "timestamp": 1685094495807,
        "createdAt": "2023-05-26T09:48:15.808000",
        "contract": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
        "token": {
          "tokenId": 20,
          "tokenName": "Hooligan #20",
          "tokenImage": "https://d1ynu5ttzco4qz.cloudfront.net/fit-in/500x500/files/d634c952fef6937d8e8bba3fabc252b3.jpeg",
          "rarityRank": null,
          "rarityScore": null
        },
        "collection": {
          "collectionId": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
          "collectionName": "Hooligan",
          "collectionImage": "https://test-static.alienswap.xyz/files/a48f83542dcd7c1ac50a0b50733b8440.gif"
        },
        "order": {
          "id": null,
          "side": "mint",
          "is_active": false,
          "criteria": {
            "kind": "token",
            "data": {
              "token": {
                "tokenId": 20,
                "tokenName": "Hooligan #20",
                "tokenImage": "https://d1ynu5ttzco4qz.cloudfront.net/fit-in/500x500/files/d634c952fef6937d8e8bba3fabc252b3.jpeg",
                "rarityRank": null,
                "rarityScore": null
              },
              "collection": {
                "collectionId": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
                "collectionName": "Hooligan",
                "collectionImage": "https://test-static.alienswap.xyz/files/a48f83542dcd7c1ac50a0b50733b8440.gif"
              }
            }
          }
        }
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» activities|[object]|true|none||none|
|»»» type|string|false|none||none|
|»»» fromAddress|string|false|none||none|
|»»» toAddress|string|false|none||none|
|»»» price|null|false|none||none|
|»»» amount|integer|false|none||none|
|»»» timestamp|integer|false|none||none|
|»»» createdAt|string|false|none||none|
|»»» contract|string|false|none||none|
|»»» token|object|false|none||none|
|»»»» tokenId|integer|true|none||none|
|»»»» tokenName|string|true|none||none|
|»»»» tokenImage|string|true|none||none|
|»»»» rarityRank|object|true|none||none|
|»»»» rarityScore|object|true|none||none|
|»»» collection|object|false|none||none|
|»»»» collectionId|string|true|none||none|
|»»»» collectionName|string|true|none||none|
|»»»» collectionImage|string|true|none||none|
|»»» order|object|false|none||none|
|»»»» id|string|true|none|订单uuid|none|
|»»»» is_active|boolean|true|none||none|
|»»»» side|string|true|none|ask/bid|none|
|»»»» criteria|object|true|none||none|
|»»»»» kind|string|true|none|目前只返回token|none|
|»»»»» data|object|true|none||none|
|»»»»»» token|object|true|none||none|
|»»»»»»» tokenId|string|true|none||none|
|»»»»»»» tokenName|string|true|none||none|
|»»»»»»» tokenImage|string|true|none||none|
|»»»»»»» rarityRank|object|true|none||none|
|»»»»»»» rarityScore|object|true|none||none|
|»»»»»» collection|object|true|none||none|
|»»»»»»» collectionId|string|true|none||none|
|»»»»»»» collectionName|string|true|none||none|
|»»»»»»» collectionImage|string|true|none||none|

## 8、GET 列举 collection activity

GET /api/v1/public/mirror/collections/activity

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|limit|query|integer| 否 |默认1000，最大1000|
|sortBy|query|string| 否 |排序字段，支持 eventTimestamp | createdAt|
|continuation|query|string| 否 |分页参数|
|types|query|array[string]| 否 |事件类型，目前支持mint, transfer, ask, bid, bid_cancel, ask_cancel, sale|
|collection|query|string| 否 |集合地址|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "activities": [
      {
        "type": "mint",
        "fromAddress": "0x0000000000000000000000000000000000000000",
        "toAddress": "0x38CA4DE19CD5Ec01D3e07468773C12743C7F6c0A",
        "price": null,
        "amount": 1,
        "timestamp": 1685094495807,
        "createdAt": "2023-05-26T09:48:15.808000",
        "contract": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
        "token": {
          "tokenId": 20,
          "tokenName": "Hooligan #20",
          "tokenImage": "https://d1ynu5ttzco4qz.cloudfront.net/fit-in/500x500/files/d634c952fef6937d8e8bba3fabc252b3.jpeg",
          "rarityRank": null,
          "rarityScore": null
        },
        "collection": {
          "collectionId": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
          "collectionName": "Hooligan",
          "collectionImage": "https://test-static.alienswap.xyz/files/a48f83542dcd7c1ac50a0b50733b8440.gif"
        },
        "order": {
          "id": null,
          "side": "mint",
          "is_active": false,
          "criteria": {
            "kind": "token",
            "data": {
              "token": {
                "tokenId": 20,
                "tokenName": "Hooligan #20",
                "tokenImage": "https://d1ynu5ttzco4qz.cloudfront.net/fit-in/500x500/files/d634c952fef6937d8e8bba3fabc252b3.jpeg",
                "rarityRank": null,
                "rarityScore": null
              },
              "collection": {
                "collectionId": "0x9Df304b4FA64461d75e86B2E7E82B455e4C64250",
                "collectionName": "Hooligan",
                "collectionImage": "https://test-static.alienswap.xyz/files/a48f83542dcd7c1ac50a0b50733b8440.gif"
              }
            }
          }
        }
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» activities|[object]|true|none||none|
|»»» type|string|true|none||none|
|»»» fromAddress|string|true|none||none|
|»»» toAddress|string|true|none||none|
|»»» price|number¦null|true|none||none|
|»»» amount|integer|true|none||none|
|»»» timestamp|integer|true|none||none|
|»»» createdAt|string|true|none||none|
|»»» contract|string|true|none||none|
|»»» token|object|true|none||none|
|»»»» tokenId|integer|true|none||none|
|»»»» tokenName|string¦null|true|none||none|
|»»»» tokenImage|string¦null|true|none||none|
|»»»» rarityRank|object|true|none||none|
|»»»» rarityScore|object|true|none||none|
|»»» collection|object|true|none||none|
|»»»» collectionId|string|true|none||none|
|»»»» collectionName|string|true|none||none|
|»»»» collectionImage|string|true|none||none|
|»»» order|object|true|none||none|
|»»»» id|string|true|none|订单uuid|none|
|»»»» is_active|boolean|true|none|是否活跃|none|
|»»»» side|string|true|none|ask/bid|none|
|»»»» criteria|object|true|none||none|
|»»»»» kind|string|true|none|目前只返回token|none|
|»»»»» data|object|true|none||none|
|»»»»»» token|object|true|none||none|
|»»»»»»» tokenId|string|true|none||none|
|»»»»»»» tokenName|string|true|none||none|
|»»»»»»» tokenImage|string|true|none||none|
|»»»»»»» rarityScore|object|true|none||none|
|»»»»»»» rarityRank|object|true|none||none|
|»»»»»» collection|object|true|none||none|
|»»»»»»» collectionId|string|true|none||none|
|»»»»»»» collectionName|string|true|none||none|
|»»»»»»» collectionImage|string|true|none||none|
|»» continuation|string|true|none||none|

## 9、GET 列举成交记录

GET /api/v1/public/mirror/sales

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|limit|query|integer| 否 |default 20 max 20|
|collection|query|string| 否 |集合地址|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "sales": [
      {
        "price": {
          "currency": {
            "symbol": "ETH"
          },
          "amount": {
            "decimal": 0.01
          }
        },
        "createdAt": "2023-07-28T16:46:42.941000"
      },
      {
        "price": {
          "currency": {
            "symbol": "ETH"
          },
          "amount": {
            "decimal": 0.01
          }
        },
        "createdAt": "2023-07-28T16:46:42.941000"
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» sales|[object]|true|none||none|
|»»» price|object|true|none||none|
|»»»» currency|object|true|none||none|
|»»»»» symbol|string|true|none||none|
|»»»» amount|object|true|none||none|
|»»»»» decimal|number|true|none||none|
|»»» createdAt|string|true|none||none|

## 10、GET 列举用户持有的 token
GET /api/v1/public/mirror/users/{address}/tokens

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|address|path|string| 是 |none|
|tokens|query|string| 否 |token_id，合约:数字的形式，支持传多个|
|collection|query|string| 否 |集合id，地址小写|
|includeTopBid|query|string| 否 |none|
|limit|query|integer| 否 |默认20，最大100|
|sortBy|query|string| 否 |排序字段，目前仅支持floorAskPrice|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "tokens": [
      {
        "token": {
          "tokenState": 0,
          "contract": "0xc17FB0570880d2d5B2356C64026aE08446Ebf2f1",
          "tokenId": "163",
          "name": "Genesis #163",
          "description": "The NFT Zero Gas us.\n",
          "image": "https://d2zu5dm88ki7it.cloudfrf7d2b0879d6f12c5d.png",
          "media": "https://d2zu5dm88ki7it.cl0879d6f12c5d.png",
          "mediaType": "image/png",
          "kind": "erc721",
          "supply": 0,
          "remainingSupply": 1,
          "createdAt": 1688465321,
          "mintPrice": null,
          "rarity": 1,
          "rarityRank": null,
          "collection": {
            "id": "0xc17FB0570880d2d5B2356C64026aE08446Ebf2f1",
            "name": "ZERO GAS Genesis Badge NFT",
            "image": "https://d2zu5dm88ki7it.cloudf9d6f12c5d.png",
            "floorAsk": {
              "id": "aa725eba510b11eeac9c06dbddb6216d3d0e05289f75026001",
              "price": 0.0029,
              "maker": "0x6096963E69aFADd3962A5954B912821e7f2AdCB1"
            }
          },
          "lastSale": {
            "timestamp": 1688526626741,
            "currency": "ETH",
            "price": 0.00995
          }
        },
        "ownership": {
          "tokenCount": 1,
          "onSaleCount": 0,
          "floorAsk": {
            "id": null,
            "price": {
              "currency": "ETH",
              "amount": null,
              "netAmount": null
            },
            "maker": null,
            "validFrom": null,
            "validUntil": null
          },
          "acquiredAt": "2023-07-05T03:10:26.695000"
        },
        "market": {
          "floorAsk": {
            "id": null,
            "price": {
              "currency": "ETH",
              "amount": null,
              "netAmount": null
            },
            "maker": null,
            "validFrom": null,
            "validUntil": null
          }
        }
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» tokens|[object]|true|none||none|
|»»» token|object|true|none||none|
|»»»» tokenState|integer|true|none||none|
|»»»» contract|string|true|none||none|
|»»»» tokenId|string|true|none||none|
|»»»» name|string|true|none||none|
|»»»» description|string|true|none||none|
|»»»» image|string|true|none||none|
|»»»» media|string|true|none||none|
|»»»» mediaType|string|true|none||none|
|»»»» kind|string|true|none||none|
|»»»» supply|integer|true|none||none|
|»»»» remainingSupply|integer|true|none||none|
|»»»» createdAt|integer|true|none||none|
|»»»» mintPrice|string|true|none||none|
|»»»» rarity|integer|true|none||none|
|»»»» rarityRank|string|true|none||none|
|»»»» collection|object|true|none||none|
|»»»»» id|string|true|none||contract id|
|»»»»» name|string|true|none||coll name|
|»»»»» image|string|true|none||合集封面图|
|»»»»» floorAsk|object|true|none||合集地板价|
|»»»»»» id|string|true|none||none|
|»»»»»» price|number|true|none||none|
|»»»»»» maker|string|true|none||none|
|»»»» attributes|[object]|true|none||none|
|»»»»» key|string|true|none||none|
|»»»»» value|string|true|none||none|
|»»»»» kind|string|true|none||none|
|»»»»» tokenCount|string|true|none||none|
|»»» ownership|object|true|none||none|
|»»»» tokenCount|integer|true|none||none|
|»»»» onSaleCount|integer|true|none||none|
|»»»» floorAsk|object|true|none||none|
|»»»»» id|string|true|none||none|
|»»»»» price|object|true|none||none|
|»»»»»» currency|string|true|none||none|
|»»»»»» amount|integer|true|none||none|
|»»»»»» netAmount|integer|true|none||none|
|»»»»» maker|string|true|none||none|
|»»»»» validFrom|integer|true|none||none|
|»»»»» validUntil|integer|true|none||none|
|»»»» acquiredAt|string|true|none||none|
|»»» market|object|true|none||none|
|»»»» floorAsk|object|true|none||none|
|»»»»» id|integer|true|none||none|
|»»»»» price|object|true|none|最低挂单价|none|
|»»»»»» currency|string|true|none||none|
|»»»»»» amount|integer|true|none||none|
|»»»»»» netAmount|integer|true|none||none|
|»»»»» maker|string|true|none|挂单人|none|
|»»»»» validFrom|integer|true|none|订单有效期unixts|none|
|»»»»» validUntil|integer|true|none|订单有效期unix ts|none|


### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|status|integer|true|none|请求状态|none|
|msg|string|true|none|请求信息|none|

## 11、GET 列举 tokens 地板价

GET /api/v1/public/mirror/tokens/floor

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|collection|query|string| 否 |集合id，地址小写|
|contract|query|string| 否 |合约地址|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "tokens": {
      "123": 0.618,
      "233": 0.212
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» tokens|object|true|none||key 是 token_id，value 是 token 的地板价|

## 12、POST 查询用户充值资产的余额

POST /api/v1/public/mirror/wallet/balance

> Body 请求参数

```json
{
  "address": "0x309B945946710E770074BB9361A5Cc7de508eA6f"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|body|body|object| 否 |none|
|» address|body|string| 是 |用户地址|

> 返回示例

> 成功

```json
{
  "status": 0,
  "msg": "ok",
  "data": {
    "ETH": {
      "balance": 1.01,
      "avail": 0.9,
      "frozen": 0.11
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» status|integer|true|none|请求状态|none|
|» msg|string|true|none|请求信息|none|
|» data|object|true|none||none|
|»» ETH|object|true|none||none|
|»»» balance|number|true|none||总余额，balance=avail+frozen|
|»»» avail|number|true|none||可用余额|
|»»» frozen|number|true|none||因提币等操作临时冻结的余额，冻结部分不可用|

###

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|status|integer|true|none|请求状态|none|
|msg|string|true|none|请求信息|none|

