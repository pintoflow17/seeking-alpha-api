# SEEKING ALPHA API DOCUMENTATION

The **Seeking Alpha API** provides users with comprehensive access to a wealth of financial information, including news, market dynamics, price quotations, charts, indices, and analyses from investors and specialists. This API is designed for developers and financial analysts seeking to enhance their applications with real-time market data and insights.

With a wide range of endpoints available, the **Seeking Alpha API** enables users to retrieve up-to-date information on market trends, stock performance, and expert analyses. Its structured JSON responses facilitate easy integration into various platforms, making it an invaluable resource for anyone looking to stay informed about financial markets and investment opportunities.

# Authentication
The URL you need to use is the following: `https://seeking-alpha-api.p.rapidapi.com/`
The API requires the headers listed below:

 - **`x-rapidapi-host`**: `seeking-alpha-api.p.rapidapi.com`
 - **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/seeking-alpha-api/pricing).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

# Endpoints
The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

#### 1. **`GET /screener`**
-   **Description**: Retrieve a list of ETFs or stocks based on specified filters.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `type`  | string   | `etf` | Specify the type: `etf` | `stocks`.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/screener?type=etf', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "metrics": {
    "data": [
      {
        "id": "967aaa441700",
        "type": "screener",
        "attributes": {
          "name": "All ETFs",
          "description": "All ETF screener - search and filter ETFs by fund type, class, sector, quant rating and more. ",
          "filters": {},
          "category": "public",
          "userId": null
        },
        "relationships": {
          "contentLinkBlock": {
            "data": null
          }
        },
        "meta": {
          "results_count": 4691,
          "introText": null
        }
      },
      {
        "id": "922b797269",
        "type": "screener",
        "attributes": {
          "name": "Top Rated ETFs",
          "description": "Traditional ETFs with a Quant rating of Buy or Strong Buy",
          "filters": {
            "quant_rating": {
              "gte": 3.5,
              "lte": 5,
              "exclude": false
            },
            "fund_type": {
              "in": [
                "traditional"
              ],
              "exclude": false
            }
          },
          "category": "public",
          "userId": null
        },
        "relationships": {
          "contentLinkBlock": {
            "data": null
          }
        },
        "meta": {
          "results_count": 526,
          "introText": null
        }
      },
      {
        "id": "922b7973d6",
        "type": "screener",
        "attributes": {
          "name": "Top Allocation ETFs",
          "description": "Top Allocation ETFs rated by Quant rating",
          "filters": {
            "quant_rating": {
              "gte": 3.5,
              "lte": 5,
              "exclude": false
            },
            "asset_class_id": {
              "exclude": false,
              "in": [
                11304,
                11305,
                11306,
                "..."
              ]
            }
          },
          "category": "public",
          "userId": null
        },
        "relationships": {
          "contentLinkBlock": {
            "data": null
          }
        },
        "meta": {
          "results_count": 2,
          "introText": null
        }
      },
      "..."
    ],
    "meta": {
      "page": {
        "title": "ETF Screener - Build Your Own Screener | Seeking Alpha",
        "description": "ETF ratings screener ranks by Quant or Author rating. Create your own screener or use Seeking Alpha's preset screeners."
      },
      "h1Title": "ETF Ratings Screener",
      "introText": "<p>Welcome to the Seeking Alpha ETF Screener. This is a great, easy-to-use screener, which enables you to pinpoint the market's most compelling ETFs for your specific investing strategy. Filter ETFs with Buy/Hold/Sell Quant Ratings and author recommendations. You can also screen ETFs from a range of metrics including asset class, sub-class, performance, momentum and expenses. Create your screener from scratch or use one of Seeking Alpha's preset screeners.</p>"
    }
  }
}
```



#### 2. **`GET /leading-story`**
-   **Description**: Retrieve the latest leading news stories related to the market.

-   **Parameters**:
  This endpoint has no parameters.

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/leading-story', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "leading_news_story": [
    {
      "id": 0,
      "type": "leadingNewsStory",
      "attributes": {
        "type": "MarketCurrent",
        "headline": "AMD soft guidance",
        "url": "https://seekingalpha.com/news/4218628-amd-q3-earnings-stock-falling"
      }
    },
    {
      "id": 1,
      "type": "leadingNewsStory",
      "attributes": {
        "type": "MarketCurrent",
        "headline": "GOOG sales growth",
        "url": "https://seekingalpha.com/news/4220953-key-takeaways-from-alphabets-q3-earnings-as-stock-rises-4"
      }
    },
    {
      "id": 2,
      "type": "leadingNewsStory",
      "attributes": {
        "type": "MarketCurrent",
        "headline": "RDDT surges",
        "url": "https://seekingalpha.com/news/4221090-solid-user-engagement-drives-reddits-robust-results-shares-soar"
      }
    },
    "..."
  ]
}
```



#### 3. **`GET /dividend-investing`**
-   **Description**: Retrieve information on trending dividend stocks, recent dividend increases, and upcoming ex-dividend dates.

-   **Parameters**:
  This endpoint has no parameters.

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/dividend-investing', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "dividend_investing": {
    "id": "0",
    "type": "dividend_investing",
    "attributes": {
      "trending_dividend_stocks": [
        {
          "slug": "PFE",
          "name": "Pfizer Inc.",
          "div_yield_fwd": 5.903022
        },
        {
          "slug": "BABA",
          "name": "Alibaba Group Holding Limited",
          "div_yield_fwd": 2.0034058
        },
        {
          "slug": "O",
          "name": "Realty Income Corporation",
          "div_yield_fwd": 5.234233
        },
        "..."
      ],
      "dividend_increases": [
        {
          "slug": "CVX",
          "name": "Chevron Corporation"
        },
        {
          "slug": "USB",
          "name": "U.S. Bancorp"
        },
        {
          "slug": "C",
          "name": "Citigroup Inc."
        },
        "..."
      ],
      "upcoming_exdates": [
        {
          "slug": "KTH",
          "name": "Corts Trust For Peco Energy Capital Trust III CORTS 8.00%",
          "date": "2024-10-30"
        },
        {
          "slug": "MCBS",
          "name": "MetroCity Bankshares, Inc.",
          "date": "2024-10-30"
        },
        {
          "slug": "CFG",
          "name": "Citizens Financial Group, Inc.",
          "date": "2024-10-30"
        },
        "..."
      ]
    }
  }
}
```



#### 4. **`GET /comparison`**
-   **Description**: This endpoint compares financial instruments based on predefined options.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `option`  | string   | `-` | The comparison option to use.   | Yes       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/comparison?option=1', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "comparison": {
    "data": {
      "id": "9e",
      "type": "keyComparison",
      "attributes": {
        "name": "FAANG Stocks",
        "description": "Compare Facebook, Amazon, Apple, Netflix & Google.",
        "chartPreferences": {},
        "public": true,
        "lineOrder": 21,
        "userId": 53069392,
        "typeId": 0
      },
      "relationships": {
        "tickers": {
          "data": [
            {
              "id": "36222",
              "type": "ticker"
            },
            {
              "id": "562",
              "type": "ticker"
            },
            {
              "id": "146",
              "type": "ticker"
            },
            "..."
          ]
        }
      },
      "meta": {
        "links": {
          "canonical": "https://seekingalpha.com/comparison/9e-FAANG-Stocks"
        }
      }
    },
    "included": [
      {
        "id": "50",
        "type": "sector",
        "attributes": {
          "name": "Communication Services",
          "quant_tickers_count": 238
        },
        "meta": {
          "screener_links": {
            "self": "/screeners/96793116-Top-Communication-Stocks",
            "canonical": "https://seekingalpha.com/screeners/96793116-Top-Communication-Stocks"
          }
        }
      },
      {
        "id": "50203010",
        "type": "sub_industry",
        "attributes": {
          "name": "Interactive Media and Services",
          "quant_tickers_count": 59
        },
        "meta": {
          "screener_links": {
            "self": "/screeners/940837608b-Top-Interactive-Media-and-Services-Stocks",
            "canonical": "https://seekingalpha.com/screeners/940837608b-Top-Interactive-Media-and-Services-Stocks"
          }
        }
      },
      {
        "id": "36222",
        "type": "ticker",
        "attributes": {
          "slug": "meta",
          "name": "META",
          "companyName": "Meta Platforms, Inc.",
          "equityType": "stocks",
          "indexGroup": null,
          "currency": "USD",
          "tradingViewSlug": "NASDAQ:META",
          "exchange": "NASDAQ",
          "exchangeDescription": null,
          "company": "Meta Platforms, Inc.",
          "isBdc": false,
          "visible": true,
          "searchable": true,
          "private": false,
          "pending": false,
          "isDefunct": false,
          "followersCount": 1018259,
          "fundTypeId": 0,
          "articleRtaCount": 17,
          "newsRtaCount": 74,
          "divYieldType": "forward",
          "primaryEpsConsensusMeanType": "normalized",
          "mergedOn": null,
          "isReit": false
        },
        "relationships": {
          "sector": {
            "data": {
              "id": "50",
              "type": "sector"
            }
          },
          "subIndustry": {
            "data": {
              "id": "50203010",
              "type": "subIndustry"
            }
          }
        },
        "meta": {
          "companyLogoUrlLight": "https://static.seekingalpha.com/cdn/s3/company_logos/mark_vector_light/META.svg",
          "companyLogoUrlDark": "https://static.seekingalpha.com/cdn/s3/company_logos/mark_vector_dark/META.svg"
        }
      },
      "..."
    ],
    "meta": {
      "isOwner": false,
      "page": {
        "title": "FAANG Stock Prices, Valuation and Dividends Today",
        "description": "Compare FAANG stocks on financial statistics like market cap and valuation. Click here to see a detailed comparison of Meta, Amazon, Apple, Netflix and Google."
      },
      "introText": "<p>Are you looking to review FAANG stocks for your investment portfolio? Compare FAANG stocks with Seeking Alpha's stock comparison tool. This tool shows key financial statistics and data for Meta Platforms, Amazon, Apple, Netflix, and Alphabet. You can also view graphs and charts to compare metrics such as market cap, revenue, total returns, ratings, valuations and dividends.</p>",
      "h1Title": "FAANG Stock Comparison"
    }
  }
}
```



#### 5. **`GET /podcast`**
-   **Description**: This endpoint retrieves podcast episodes.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `limit`  | string   | `40` | The maximum number of episodes to return.   | Yes       |
| `page`  | string   | `1` | The page number for pagination.   | Yes       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/podcast?limit=2', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "podcast": [
    {
      "id": "4730685",
      "type": "article",
      "attributes": {
        "publishOn": "2024-10-30T05:00:00-04:00",
        "isLockedPro": false,
        "commentCount": 0,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/1338344120/image_1338344120.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {},
        "title": "AI, Data Centers And Energy Demand",
        "structuredInsights": null,
        "isPaywalled": false
      },
      "relationships": {
        "author": {
          "data": {
            "id": "106712",
            "type": "author"
          }
        },
        "sentiments": {
          "data": []
        },
        "primaryTickers": {
          "data": []
        },
        "secondaryTickers": {
          "data": [
            {
              "id": "146",
              "type": "tag"
            },
            {
              "id": "764528",
              "type": "tag"
            },
            {
              "id": "893",
              "type": "tag"
            },
            "..."
          ]
        },
        "otherTags": {
          "data": [
            {
              "id": "634377",
              "type": "tag"
            },
            {
              "id": "112862",
              "type": "tag"
            },
            {
              "id": "762205",
              "type": "tag"
            },
            "..."
          ]
        }
      },
      "links": {
        "self": "/article/4730685-ai-data-centers-and-energy-demand"
      }
    },
    {
      "id": "4730515",
      "type": "article",
      "attributes": {
        "publishOn": "2024-10-29T13:30:00-04:00",
        "isLockedPro": false,
        "commentCount": 8,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/1412721464/image_1412721464.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {},
        "title": "Wall Street Lunch: 10,000 Times Smarter Than Humans By 2035",
        "structuredInsights": null,
        "isPaywalled": false
      },
      "relationships": {
        "author": {
          "data": {
            "id": "25250",
            "type": "author"
          }
        },
        "sentiments": {
          "data": []
        },
        "primaryTickers": {
          "data": [
            {
              "id": "1150",
              "type": "tag"
            },
            {
              "id": "602191",
              "type": "tag"
            },
            {
              "id": "586843",
              "type": "tag"
            }
          ]
        },
        "secondaryTickers": {
          "data": [
            {
              "id": "31222",
              "type": "tag"
            },
            {
              "id": "781",
              "type": "tag"
            },
            {
              "id": "1216",
              "type": "tag"
            },
            "..."
          ]
        },
        "otherTags": {
          "data": [
            {
              "id": "35794",
              "type": "tag"
            },
            {
              "id": "762205",
              "type": "tag"
            },
            {
              "id": "9082",
              "type": "tag"
            },
            "..."
          ]
        }
      },
      "links": {
        "self": "/article/4730515-wall-street-lunch-masayoshi-son-says-nvidia-is-undervalued"
      }
    }
  ]
}
```



#### 6. **`GET /price`**
-   **Description**: This endpoint retrieves the price of a specific stock.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `sa_id`  | string   | `-` | The Seeking Alpha ID of the stock.   | Yes       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/price?sa_id=765080', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "real_time_quote": [
    {
      "ticker_id": 765080,
      "sa_id": 765080,
      "sa_slug": "brrr",
      "symbol": "BRRR",
      "high": 20.86,
      "low": 20.07,
      "open": 20.17,
      "prev_close": 19.72,
      "last": 20.53,
      "volume": 295794,
      "last_time": "2024-10-29T16:00:00.000-04:00",
      "ext_time": "2024-10-29T18:05:42.000-04:00",
      "ext_price": 20.39,
      "ext_market": "post",
      "info": "Market Close",
      "src": "XigniteQuotePuller",
      "updated_at": "2024-10-30T05:58:05.130-04:00"
    }
  ]
}
```



#### 7. **`GET /day-watch`**
-   **Description**: This endpoint provides the day watch report.

-   **Parameters**:
  This endpoint has no parameters.

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/day-watch', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "day_watch": {
    "id": "0",
    "type": "day_watch",
    "attributes": {
      "top_gainers": [
        {
          "id": 605187,
          "slug": "WGS",
          "name": "GeneDx Holdings Corp."
        },
        {
          "id": 1551,
          "slug": "VFC",
          "name": "V.F. Corporation"
        },
        {
          "id": 4800,
          "slug": "CVLT",
          "name": "Commvault Systems, Inc."
        },
        "..."
      ],
      "top_losers": [
        {
          "id": 610822,
          "slug": "JBI",
          "name": "Janus International Group, Inc."
        },
        {
          "id": 598814,
          "slug": "TMDX",
          "name": "TransMedics Group, Inc."
        },
        {
          "id": 4126,
          "slug": "HLIT",
          "name": "Harmonic Inc."
        },
        "..."
      ],
      "cryptocurrencies": [
        {
          "id": 581328,
          "slug": "BTC-USD",
          "name": "Bitcoin USD"
        },
        {
          "id": 579496,
          "slug": "ETH-USD",
          "name": "Ethereum USD"
        },
        {
          "id": 580755,
          "slug": "BNB-USD",
          "name": "Binance Coin USD"
        },
        "..."
      ],
      "most_active": [
        {
          "id": 605944,
          "slug": "SOFI",
          "name": "SoFi Technologies, Inc."
        },
        {
          "id": 691,
          "slug": "F",
          "name": "Ford Motor Company"
        },
        {
          "id": 1150,
          "slug": "NVDA",
          "name": "NVIDIA Corporation"
        },
        "..."
      ],
      "in_the_news": [
        {
          "id": 601358,
          "slug": "xauusd:cur",
          "name": "Gold Spot Price"
        },
        {
          "id": 544,
          "slug": "goog",
          "name": "Alphabet Inc."
        },
        {
          "id": 1016,
          "slug": "amd",
          "name": "Advanced Micro Devices, Inc."
        },
        "..."
      ],
      "faang_stocks": [
        {
          "id": 36222,
          "slug": "META",
          "name": "Meta Platforms, Inc."
        },
        {
          "id": 562,
          "slug": "AMZN",
          "name": "Amazon.com, Inc."
        },
        {
          "id": 146,
          "slug": "AAPL",
          "name": "Apple Inc."
        },
        "..."
      ],
      "sp500_gainers": [
        {
          "id": 1948,
          "slug": "CDNS",
          "name": "Cadence Design Systems, Inc."
        },
        {
          "id": 1092,
          "slug": "INCY",
          "name": "Incyte Corporation"
        },
        {
          "id": 679,
          "slug": "FFIV",
          "name": "F5, Inc."
        },
        "..."
      ],
      "sp500_losers": [
        {
          "id": 3061,
          "slug": "SWK",
          "name": "Stanley Black & Decker, Inc."
        },
        {
          "id": 691,
          "slug": "F",
          "name": "Ford Motor Company"
        },
        {
          "id": 2182,
          "slug": "DHI",
          "name": "D.R. Horton, Inc."
        },
        "..."
      ],
      "cap400_gainers": [
        {
          "id": 4800,
          "slug": "CVLT",
          "name": "Commvault Systems, Inc."
        },
        {
          "id": 4044,
          "slug": "THC",
          "name": "Tenet Healthcare Corporation"
        },
        {
          "id": 1725,
          "slug": "RMBS",
          "name": "Rambus Inc."
        },
        "..."
      ],
      "cap400_losers": [
        {
          "id": 2113,
          "slug": "CROX",
          "name": "Crocs, Inc."
        },
        {
          "id": 91851,
          "slug": "PBF",
          "name": "PBF Energy Inc."
        },
        {
          "id": 3861,
          "slug": "UFPI",
          "name": "UFP Industries, Inc."
        },
        "..."
      ],
      "cap600_gainers": [
        {
          "id": 1551,
          "slug": "VFC",
          "name": "V.F. Corporation"
        },
        {
          "id": 604910,
          "slug": "HRMY",
          "name": "Harmony Biosciences Holdings, Inc."
        },
        {
          "id": 601218,
          "slug": "NARI",
          "name": "Inari Medical, Inc."
        },
        "..."
      ],
      "cap600_losers": [
        {
          "id": 598814,
          "slug": "TMDX",
          "name": "TransMedics Group, Inc."
        },
        {
          "id": 4126,
          "slug": "HLIT",
          "name": "Harmonic Inc."
        },
        {
          "id": 9103,
          "slug": "CVI",
          "name": "CVR Energy, Inc."
        },
        "..."
      ]
    }
  }
}
```



#### 8. **`GET /recommendation`**
-   **Description**: This endpoint retrieves recommended quotes.

-   **Parameters**:
  This endpoint has no parameters.

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/recommendation', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "real_time_quotes": [
    {
      "ticker_id": 146,
      "sa_id": 146,
      "sa_slug": "aapl",
      "symbol": "AAPL",
      "high": 234.325,
      "low": 232.32,
      "open": 233.1,
      "prev_close": 233.4,
      "last": 233.67,
      "volume": 51453,
      "last_time": "2024-10-29T16:00:00.000-04:00",
      "ext_time": "2024-10-30T05:43:46.000-04:00",
      "ext_price": 233.19,
      "ext_market": "pre",
      "info": "Market Close",
      "src": "XigniteQuotePuller",
      "updated_at": "2024-10-30T05:59:00.502-04:00"
    },
    {
      "ticker_id": 36222,
      "sa_id": 36222,
      "sa_slug": "meta",
      "symbol": "META",
      "high": 593.67,
      "low": 575.398,
      "open": 580.145,
      "prev_close": 578.16,
      "last": 593.28,
      "volume": 139130,
      "last_time": "2024-10-29T16:00:00.000-04:00",
      "ext_time": "2024-10-30T05:43:50.000-04:00",
      "ext_price": 605.33,
      "ext_market": "pre",
      "info": "Market Close",
      "src": "XigniteQuotePuller",
      "updated_at": "2024-10-30T05:59:01.549-04:00"
    },
    {
      "ticker_id": 544,
      "sa_id": 544,
      "sa_slug": "goog",
      "symbol": "GOOG",
      "high": 171.86,
      "low": 168.66,
      "open": 169.385,
      "prev_close": 168.34,
      "last": 171.14,
      "volume": 436087,
      "last_time": "2024-10-29T16:00:00.000-04:00",
      "ext_time": "2024-10-30T05:43:56.000-04:00",
      "ext_price": 180.64,
      "ext_market": "pre",
      "info": "Market Close",
      "src": "XigniteQuotePuller",
      "updated_at": "2024-10-30T05:59:00.502-04:00"
    },
    "..."
  ]
}
```



#### 9. **`GET /stock-ideas`**
-   **Description**: This endpoint retrieves categorized stock ideas.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `categoryNumber`  | string   | `-` | The category of stock ideas to retrieve.   | No       |
| `limit`  | string   | `40` | The maximum number of results to return.   | No       |
| `page`  | string   | `1` | The page number for pagination.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/stock-ideas?categoryNumber=2&limit=2', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "stock_ideas": [
    {
      "id": "4730717",
      "type": "article",
      "attributes": {
        "publishOn": "2024-10-29T23:43:25-04:00",
        "isLockedPro": false,
        "commentCount": 10,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/1398845506/image_1398845506.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {
          "long-ideas": {
            "title": "Long Ideas",
            "slug": "long-ideas"
          }
        },
        "title": "The Market Overreacts, I Am Buying Ford's 17% Earnings Yield",
        "structuredInsights": null,
        "isPaywalled": false
      },
      "relationships": {
        "author": {
          "data": {
            "id": "106128",
            "type": "author"
          }
        },
        "sentiments": {
          "data": [
            {
              "id": "579512",
              "type": "sentiment"
            },
            {
              "id": "579758",
              "type": "sentiment"
            }
          ]
        },
        "primaryTickers": {
          "data": [
            {
              "id": "691",
              "type": "tag"
            },
            {
              "id": "780194",
              "type": "tag"
            }
          ]
        },
        "secondaryTickers": {
          "data": []
        },
        "otherTags": {
          "data": [
            {
              "id": "609367",
              "type": "tag"
            },
            {
              "id": "1936",
              "type": "tag"
            },
            {
              "id": "17335",
              "type": "tag"
            },
            "..."
          ]
        }
      },
      "links": {
        "self": "/article/4730717-the-market-overreacts-i-am-buying-fords-17-percent-earnings-yield"
      }
    },
    {
      "id": "4730558",
      "type": "article",
      "attributes": {
        "publishOn": "2024-10-29T15:26:26-04:00",
        "isLockedPro": false,
        "commentCount": 0,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/1152450129/image_1152450129.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {},
        "title": "Kandi Technologies: Split Focus More Likely To Destroy Than Build Shareholder Value",
        "structuredInsights": null,
        "isPaywalled": false
      },
      "relationships": {
        "author": {
          "data": {
            "id": "24361",
            "type": "author"
          }
        },
        "sentiments": {
          "data": [
            {
              "id": "579581",
              "type": "sentiment"
            }
          ]
        },
        "primaryTickers": {
          "data": [
            {
              "id": "15138",
              "type": "tag"
            }
          ]
        },
        "secondaryTickers": {
          "data": []
        },
        "otherTags": {
          "data": [
            {
              "id": "17522",
              "type": "tag"
            },
            {
              "id": "17335",
              "type": "tag"
            },
            {
              "id": "764066",
              "type": "tag"
            },
            "..."
          ]
        }
      },
      "links": {
        "self": "/article/4730558-kandi-technologies-split-focus-more-likely-to-destroy-than-build-shareholder-value"
      }
    }
  ]
}
```



#### 10. **`GET /metrics-grades`**
-   **Description**: This endpoint retrieves grades for specific financial metrics associated with given financial instruments.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `slugs`  | string   | `-` | A comma-separated list of financial instrument slugs for which to retrieve grades.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/metrics-grades', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "metrics_grades": [
    {
      "slug": "arco",
      "tickerId": 17796,
      "eps_revisions_category": 10,
      "growth_category": 5,
      "momentum_category": 10,
      "profitability_category": 7,
      "value_category": 3
    },
    {
      "slug": "asc",
      "tickerId": 108282,
      "eps_revisions_category": 5,
      "growth_category": 12,
      "momentum_category": 11,
      "profitability_category": 3,
      "value_category": 2
    },
    {
      "slug": "axahy",
      "tickerId": 15846,
      "eps_revisions_category": 1,
      "growth_category": 6,
      "momentum_category": 7,
      "profitability_category": 2,
      "value_category": 5
    },
    "..."
  ]
}
```



#### 11. **`GET /analyst-recommendation`**
-   **Description**: This endpoint retrieves the level of analyst recommendations for specific financial instruments.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `slugs`  | string   | `-` | A comma-separated list of financial instrument slugs for which to retrieve grades.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/analyst-recommendation', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "metrics": [
    {
      "slug": "qqq",
      "tickerId": 53,
      "tot_analysts_recommendations": 0,
      "marketcap_display": 303079683471,
      "authors_count": 17
    },
    {
      "slug": "spy",
      "tickerId": 54,
      "tot_analysts_recommendations": 0,
      "marketcap_display": 598562563671,
      "authors_count": 25
    },
    {
      "slug": "dia",
      "tickerId": 55,
      "tot_analysts_recommendations": 0,
      "marketcap_display": 35621584623,
      "authors_count": 4
    },
    "..."
  ]
}
```



#### 12. **`GET /metrics`**
-   **Description**: This endpoint retrieves metrics for specific financial instruments.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `slugs`  | string   | `-` | A comma-separated list of financial instrument slugs for which to retrieve grades.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/metrics', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "metrics": [
    {
      "slug": "qqq",
      "tickerId": 53,
      "price_return_1m": 2.755007704160262,
      "price_return_3m": 7.816339728389754,
      "price_return_6m": 15.57712305025998,
      "price_return_ytd": 22.13322914631766,
      "price_return_1y": 44.84376357475892,
      "price_return_3y": 29.53821449845899,
      "price_high_52w": 503.52,
      "price_low_52w": 351.62,
      "price_close_1m": 486.75,
      "price_close_3m": 463.9,
      "price_close_6m": 432.75,
      "price_close_1y": 345.31
    },
    {
      "slug": "spy",
      "tickerId": 54,
      "price_return_1m": 1.802369328223685,
      "price_return_3m": 6.79381746090022,
      "price_return_6m": 14.05913029839627,
      "price_return_ytd": 22.3980139277524,
      "price_return_1y": 41.66017337099444,
      "price_return_3y": 26.6782798040283,
      "price_high_52w": 586.12,
      "price_low_52w": 418.6499,
      "price_close_1m": 571.47,
      "price_close_3m": 544.76,
      "price_close_6m": 510.06,
      "price_close_1y": 410.68
    },
    {
      "slug": "dia",
      "tickerId": 55,
      "price_return_1m": -0.1063955550301476,
      "price_return_3m": 4.189785701955562,
      "price_return_6m": 10.0833767587285,
      "price_return_ytd": 12.10762331838564,
      "price_return_1y": 30.32480952527838,
      "price_return_3y": 17.94098763364318,
      "price_high_52w": 433.2,
      "price_low_52w": 330.1,
      "price_close_1m": 422.95,
      "price_close_3m": 405.51,
      "price_close_6m": 383.8,
      "price_close_1y": 324.19
    },
    "..."
  ]
}
```



#### 13. **`GET /chart`**
-   **Description**: This endpoint generates a stock chart graphic based on the provided parameters.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `ticker_id`  | string   | `-` | The unique identifier for the stock.   | Yes       |
| `period`  | string   | `-` | The time period for the chart data.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/chart?ticker_id=146', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "chart": {
    "id": "AAPL",
    "type": "chart_1d_price",
    "attributes": {
      "2024-10-29 09:30:00": {
        "open": 233.4,
        "high": 233.4,
        "low": 232.74,
        "close": 232.74,
        "volume": 977,
        "adj": 1
      },
      "2024-10-29 09:31:00": {
        "open": 233.14,
        "high": 233.47,
        "low": 232.75,
        "close": 232.75,
        "volume": 3485,
        "adj": 1
      },
      "2024-10-29 09:32:00": {
        "open": 232.42,
        "high": 232.76,
        "low": 232.42,
        "close": 232.56,
        "volume": 637,
        "adj": 1
      },
      "2024-10-29 09:33:00": {
        "open": 232.7,
        "high": 232.79,
        "low": 232.64,
        "close": 232.79,
        "volume": 639,
        "adj": 1
      },
      "2024-10-29 09:34:00": {
        "open": 232.82,
        "high": 233.12,
        "low": 232.82,
        "close": 233.12,
        "volume": 357,
        "adj": 1
      },
      ...
    }
  }
}
```



#### 14. **`GET /articles`**
-   **Description**: This endpoint retrieves articles based on specified parameters.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `category`  | string   | `all` | Filters articles by category.   | No       |
| `limit`  | string   | `10` | Number of articles to retrieve per request.   | No       |
| `page`  | string   | `1` | Page number for pagination.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/articles?limit=2', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "articles": [
    {
      "id": "4222200",
      "type": "news",
      "attributes": {
        "publishOn": "2024-10-30T05:55:48-04:00",
        "isLockedPro": false,
        "commentCount": 0,
        "gettyImageUrl": null,
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {
          "earnings": {
            "id": 10,
            "path": "/market-news/earnings",
            "slug": "earnings",
            "title": "Earnings News",
            "sasource": "theme_breadcrumb",
            "non_theme": false
          },
          "taiwan": {
            "id": 18101,
            "path": "/",
            "slug": "taiwan",
            "title": null,
            "sasource": "",
            "non_theme": true
          },
          "large-cap": {
            "id": 115402,
            "path": "/",
            "slug": "large-cap",
            "title": null,
            "sasource": "",
            "non_theme": true
          },
          "hidden-from-qp": {
            "id": 578794,
            "path": "/",
            "slug": "hidden-from-qp",
            "title": null,
            "sasource": "",
            "non_theme": true
          },
          "breaking-news": {
            "id": 614459,
            "path": "/",
            "slug": "breaking-news",
            "title": null,
            "sasource": "",
            "non_theme": true
          },
          "templated": {
            "id": 778493,
            "path": "/",
            "slug": "templated",
            "title": null,
            "sasource": "",
            "non_theme": true
          }
        },
        "title": "United Microelectronics reports Q3 results",
        "isPaywalled": false,
        "lastModified": "2024-10-30T05:57:41-04:00",
        "status": "Active",
        "content": "<ul>\n<li>United Microelectronics <a href=\"https://www.umc.com/upload/media/08_Investors/Financials/Quarterly_Results/Quarterly_2020-2029_English_pdf/2024/Q3_2024/UMC24Q3_report.pdf\" target=\"_blank\" rel=\"nofollow\">press release</a>  (<span class=\"ticker-hover-wrapper\">NYSE:<a href=\"https://seekingalpha.com/symbol/UMC\" title=\"United Microelectronics Corporation\">UMC</a></span>): Q3  GAAP EPADS of $0.183.</li>\n<li>Revenue of $1.91B (+6% Y/Y)</li>\n</ul>\n<div id=\"more-links\">\n<h2>More on United Microelectronics</h2>   <ul>            <li><a href=\"https://seekingalpha.com/article/4720019-united-microelectronics-performance-gets-better-with-every-quarter\" class=\"more-link\">United Microelectronics: Performance Gets Better With Every Quarter</a></li>            <li><a href=\"https://seekingalpha.com/news/4218983-united-microelectronics-q3-2024-earnings-preview\" class=\"more-link\">United Microelectronics Q3 2024 Earnings Preview</a></li>            <li><a href=\"https://seekingalpha.com/news/4213045-globalfoundries-united-microelectronics-cut-by-morgan-stanley-on-competition\" class=\"more-link\">GlobalFoundries, United Microelectronics cut by Morgan Stanley on competition</a></li>            <li><a href=\"https://seekingalpha.com/symbol/UMC/ratings/quant-ratings\" class=\"more-link\">Seeking Alpha’s Quant Rating on United Microelectronics</a></li>            <li><a href=\"https://seekingalpha.com/symbol/UMC/earnings\" class=\"more-link\">Historical earnings data for United Microelectronics</a></li>        </ul>\n</div>",
        "metered": false,
        "correctionReason": null,
        "audioDuration": 14.52
      },
      "relationships": {
        "author": {
          "data": {
            "id": "51785401",
            "type": "newsAuthorUser"
          }
        },
        "sentiments": {
          "data": []
        },
        "primaryTickers": {
          "data": [
            {
              "id": "1410",
              "type": "tag"
            }
          ]
        },
        "secondaryTickers": {
          "data": []
        },
        "otherTags": {
          "data": []
        },
        "ratingChangeNotice": {}
      },
      "links": {
        "self": "/news/4222200-united-microelectronics-reports-q3-results",
        "canonical": "https://seekingalpha.com/news/4222200-united-microelectronics-reports-q3-results",
        "uriImage": "https://static.seekingalpha.com/assets/og_image_1200-29b2bfe1a595477db6826bd2126c63ac2091efb7ec76347a8e7f81ba17e3de6c.png",
        "schemaImage": {
          "@type": "ImageObject",
          "url": "https://static.seekingalpha.com/assets/og_image_1200-29b2bfe1a595477db6826bd2126c63ac2091efb7ec76347a8e7f81ba17e3de6c.png"
        }
      }
    },
    {
      "id": "4222125",
      "type": "news",
      "attributes": {
        "publishOn": "2024-10-30T05:46:59-04:00",
        "isLockedPro": false,
        "commentCount": 0,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/145158250/image_145158250.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {
          "us": {
            "id": 326,
            "path": "/",
            "slug": "us",
            "title": null,
            "sasource": "",
            "non_theme": true
          },
          "commodities": {
            "id": 375,
            "path": "/market-news/commodities",
            "slug": "commodities",
            "title": "Commodities ",
            "sasource": "theme_breadcrumb",
            "non_theme": false
          },
          "hidden-from-qp": {
            "id": 578794,
            "path": "/",
            "slug": "hidden-from-qp",
            "title": null,
            "sasource": "",
            "non_theme": true
          },
          "na-cap": {
            "id": 614453,
            "path": "/",
            "slug": "na-cap",
            "title": null,
            "sasource": "",
            "non_theme": true
          },
          "on-the-move": {
            "id": 614457,
            "path": "/market-news/on-the-move",
            "slug": "on-the-move",
            "title": "On the Move",
            "sasource": "theme_breadcrumb",
            "non_theme": false
          },
          "news-metered": {
            "id": 614465,
            "path": "/",
            "slug": "news-metered",
            "title": null,
            "sasource": "",
            "non_theme": true
          }
        },
        "title": "Investment flows key to gold’s performance in Q3, value of demand exceeded $100B - WGC",
        "isPaywalled": false,
        "lastModified": "2024-10-30T05:49:50-04:00",
        "status": "Active",
        "content": "<div> <p>Gold demand, including over-the-counter (OTC) trading, gained 5% year-on-year to 1,313tonne – a record for a third quarter, the World Gold Council (WGC) said on Wednesday.</p> <p>Spot gold prices (<a href=\"https://seekingalpha.com/symbol/XAUUSD:CUR\" title=\"Gold Spot Price\">XAUUSD:CUR</a>) have advanced over 34% since the beginning of the year, registering a series of<span class=\"paywall-full-content invisible\"> record highs during the quarter amid heightened geopolitical risks, expectations of lower interest rates, and ongoing uncertainty surrounding next week's U.S. presidential election.</span></p> <p class=\"paywall-full-content invisible\">Bullion (<a href=\"https://seekingalpha.com/symbol/XAUUSD:CUR\" title=\"Gold Spot Price\">XAUUSD:CUR</a>), up <span class=\"green\">+0.27% to $2,782.44</span> an ounce, <a href=\"https://seekingalpha.com/news/4221565-gold-futures-hit-new-record-high-analyst-sees-trump-trade-pointing-to-surging-us-debt\">scaled a fresh record</a> of $2,771.61 per ounce on Tuesday.</p> <p class=\"paywall-full-content invisible\">As such, the value of demand jumped 35% y/y to exceed $100 billion for the first time ever. </p> <p class=\"paywall-full-content invisible\"><a href=\"https://static.seekingalpha.com/uploads/2024/10/30/saupload_1730280992701.png\" rel=\"lightbox\" target=\"_blank\"><img src=\"https://static.seekingalpha.com/uploads/2024/10/30/saupload_1730280992701_thumb1.png\" width=\"100%\"></a></p> <p class=\"paywall-full-content invisible\">Global gold ETF inflows (95t) were a major driver of growth; Q3 was the first positive quarter since Q1’22, with a y/y swing from hefty (-139t) Q3’23 outflows, the report said. </p> <p class=\"paywall-full-content invisible\">On the contrary, wary of the higher prices, gold jewellery consumption sank 12% y/y despite strong growth in second-biggest buyer India. The pace of central bank buying also slowed in Q3.</p> <p class=\"paywall-full-content invisible\">\"Resurgent professional flows combined with solid bar and coin investment will offset weaker consumer demand and slower central bank buying,\" the WGC said in a quarterly report.</p> <p class=\"paywall-full-content invisible\">OTC investment, meanwhile, almost doubled y/y to 137t. This was the seventh consecutive quarter in which OTC investment has been positive for gold demand and remains a notable component of the market.</p> <p class=\"paywall-full-content invisible\">On the supply side, mine production grew 6% y/y to another quarterly record and y-t-d output has eclipsed the 2018 prior high.</p> <p class=\"paywall-full-content invisible\">ETFs: (<span class=\"ticker-hover-wrapper\">NYSEARCA:<a href=\"https://seekingalpha.com/symbol/GLD\" title=\"SPDR® Gold Shares ETF\">GLD</a></span>), (<span class=\"ticker-hover-wrapper\">NYSEARCA:<a href=\"https://seekingalpha.com/symbol/GDX\" title=\"VanEck Gold Miners ETF\">GDX</a></span>), (<a href=\"https://seekingalpha.com/symbol/GDXJ\" title=\"VanEck Vectors Junior Gold Miners ETF\">GDXJ</a>), (<a href=\"https://seekingalpha.com/symbol/IAU\" title=\"iShares Gold Trust ETF\">IAU</a>), (<a href=\"https://seekingalpha.com/symbol/NUGT\" title=\"Direxion Daily Gold Miners Index Bull 2x Shares ETF\">NUGT</a>), (<a href=\"https://seekingalpha.com/symbol/PHYS\" title=\"Sprott Physical Gold Trust\">PHYS</a>), (<a href=\"https://seekingalpha.com/symbol/GLDM\" title=\"World Gold Trust - SPDR Gold MiniShares Trust\">GLDM</a>), (<a href=\"https://seekingalpha.com/symbol/AAAU\" title=\"Goldman Sachs Physical Gold ETF\">AAAU</a>), (<a href=\"https://seekingalpha.com/symbol/SGOL\" title=\"Aberdeen Standard Physical Gold Shares ETF\">SGOL</a>), (<a href=\"https://seekingalpha.com/symbol/RING\" title=\"iShares MSCI Global Gold Miners ETF\">RING</a>), (<a href=\"https://seekingalpha.com/symbol/BAR\" title=\"GraniteShares Gold Trust\">BAR</a>), (<a href=\"https://seekingalpha.com/symbol/OUNZ\" title=\"VanEck Merk Gold Trust\">OUNZ</a>), (<a href=\"https://seekingalpha.com/symbol/SLV\" title=\"iShares Silver Trust ETF\">SLV</a>), (<a href=\"https://seekingalpha.com/symbol/PSLV\" title=\"Sprott Physical Silver Trust\">PSLV</a>), (<a href=\"https://seekingalpha.com/symbol/SIVR\" title=\"Aberdeen Standard Physical Silver Shares ETF\">SIVR</a>), (<a href=\"https://seekingalpha.com/symbol/SIL\" title=\"Global X Silver Miners ETF\">SIL</a>), (<a href=\"https://seekingalpha.com/symbol/SILJ\" title=\"ETFMG Prime Junior Silver Miners ETF\">SILJ</a>)</p> </div> <div class=\"paywall-full-content invisible\"> </div> <div id=\"more-links\" class=\"paywall-full-content invisible\"> <h2>More on gold</h2> <ul> <li><a href=\"https://seekingalpha.com/article/4730553-gold-price-reclaims-2750oz-amid-record-3-billion-inflows-into-gold-funds\" class=\"more-link\">Gold Price Reclaims $2750/Oz Amid Record $3 Billion Inflows Into Gold Funds</a></li> <li><a href=\"https://seekingalpha.com/article/4730269-gld-loss-confidence-in-dollar-will-ensure-gold-rises\" class=\"more-link\">GLD: Loss Of Confidence In The Dollar Will Ensure Gold Rises</a></li> <li><a href=\"https://seekingalpha.com/article/4729255-gdx-dips-are-buys-from-here\" class=\"more-link\">GDX: Dips Are Buys From Here</a></li> <li><a href=\"https://seekingalpha.com/news/4221565-gold-futures-hit-new-record-high-analyst-sees-trump-trade-pointing-to-surging-us-debt\" class=\"more-link\">Gold futures hit new record high; analyst sees 'Trump trade' pointing to surging U.S. debt</a></li> <li><a href=\"https://seekingalpha.com/news/4217178-commodity-roundup-brent-near-72bbl-gold-near-record-highs-with-focus-on-us-election\" class=\"more-link\">Commodity Roundup: Brent above $72/bbl; gold near record highs with focus on U.S. election</a></li> </ul> </div>",
        "metered": true,
        "correctionReason": null,
        "audioDuration": 120.456
      },
      "relationships": {
        "author": {
          "data": {
            "id": "59093036",
            "type": "newsAuthorUser"
          }
        },
        "sentiments": {
          "data": []
        },
        "primaryTickers": {
          "data": [
            {
              "id": "80",
              "type": "tag"
            },
            {
              "id": "3196",
              "type": "tag"
            }
          ]
        },
        "secondaryTickers": {
          "data": [
            {
              "id": "81",
              "type": "tag"
            },
            {
              "id": "481",
              "type": "tag"
            },
            {
              "id": "1217",
              "type": "tag"
            },
            "..."
          ]
        },
        "otherTags": {
          "data": []
        },
        "ratingChangeNotice": {}
      },
      "links": {
        "self": "/news/4222125-investment-flows-key-to-golds-performance-in-q3-as-value-of-demand-exceeded-100b---wgc",
        "canonical": "https://seekingalpha.com/news/4222125-investment-flows-key-to-golds-performance-in-q3-as-value-of-demand-exceeded-100b---wgc",
        "uriImage": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/145158250/image_145158250.jpg?io=getty-c-w750",
        "schemaImage": [
          "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/145158250/image_145158250.jpg?io=getty-c-w1280",
          "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/145158250/image_145158250.jpg?io=getty-c-crop-16-9",
          "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/145158250/image_145158250.jpg?io=getty-c-crop-4-3"
        ]
      }
    }
  ]
}
```



#### 15. **`GET /article-editor`**
-   **Description**: This endpoint retrieves a list of article editors.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `limit`  | string   | `-` | The maximum number of article editors to return.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/article-editor?limit=2', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "articles_editors_picker": [
    {
      "id": "4730756",
      "type": "article",
      "attributes": {
        "publishOn": "2024-10-30T03:35:57-04:00",
        "isLockedPro": false,
        "commentCount": 0,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/157335971/image_157335971.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {
          "reits": {
            "title": "REITs",
            "slug": "reits"
          }
        },
        "title": "Realty Income Q3 Earnings Preview: What To Look For",
        "structuredInsights": null,
        "isPaywalled": false
      },
      "relationships": {
        "author": {
          "data": {
            "id": "106329",
            "type": "author"
          }
        },
        "sentiments": {
          "data": [
            {
              "id": "579711",
              "type": "sentiment"
            }
          ]
        },
        "primaryTickers": {
          "data": [
            {
              "id": "4685",
              "type": "tag"
            }
          ]
        },
        "secondaryTickers": {
          "data": [
            {
              "id": "598899",
              "type": "tag"
            },
            {
              "id": "583376",
              "type": "tag"
            },
            {
              "id": "3007",
              "type": "tag"
            }
          ]
        },
        "otherTags": {
          "data": [
            {
              "id": "612709",
              "type": "tag"
            },
            {
              "id": "1302",
              "type": "tag"
            },
            {
              "id": "393",
              "type": "tag"
            },
            "..."
          ]
        }
      },
      "links": {
        "self": "/article/4730756-realty-income-q3-earnings-preview-what-to-look-for"
      }
    },
    {
      "id": "4730377",
      "type": "article",
      "attributes": {
        "publishOn": "2024-10-29T10:03:30-04:00",
        "isLockedPro": false,
        "commentCount": 51,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/2161516337/image_2161516337.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {
          "market-outlook": {
            "title": "Market Outlook",
            "slug": "market-outlook"
          }
        },
        "title": "My Apolitical Post-Election Investment Strategy",
        "structuredInsights": null,
        "isPaywalled": false
      },
      "relationships": {
        "author": {
          "data": {
            "id": "42871",
            "type": "author"
          }
        },
        "sentiments": {
          "data": []
        },
        "primaryTickers": {
          "data": [
            {
              "id": "603907",
              "type": "tag"
            },
            {
              "id": "598187",
              "type": "tag"
            },
            {
              "id": "590407",
              "type": "tag"
            },
            "..."
          ]
        },
        "secondaryTickers": {
          "data": [
            {
              "id": "612203",
              "type": "tag"
            },
            {
              "id": "600804",
              "type": "tag"
            },
            {
              "id": "600803",
              "type": "tag"
            },
            "..."
          ]
        },
        "otherTags": {
          "data": [
            {
              "id": "95431",
              "type": "tag"
            },
            {
              "id": "1302",
              "type": "tag"
            },
            {
              "id": "506",
              "type": "tag"
            },
            "..."
          ]
        }
      },
      "links": {
        "self": "/article/4730377-my-apolitical-post-election-investment-strategy"
      }
    }
  ]
}
```



#### 16. **`GET /screener-filter`**
-   **Description**: This endpoint retrieves filters for screening financial instruments.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `type`  | string   | `-` | The type of filter to apply.   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/screener-filter', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "screener_filter": [
    {
      "id": "etf_details",
      "label": "ETF Details",
      "filters": [
        {
          "type": "dropdown",
          "id": "fund_type",
          "label": "Fund Types",
          "values": [
            {
              "id": "traditional",
              "name": "Traditional (stocks, bonds...)"
            },
            {
              "id": "leveraged",
              "name": "Leveraged (2x, 3x...)"
            },
            {
              "id": "inverse",
              "name": "Inverse (shorts)"
            },
            "..."
          ],
          "default": [
            "traditional"
          ]
        },
        {
          "type": "dropdown",
          "id": "asset_class_id",
          "label": "Asset Class & Sub-Class",
          "values": [
            {
              "id": 11228,
              "name": "U.S. Equity",
              "values": [
                {
                  "id": 11229,
                  "name": "Large Blend"
                },
                {
                  "id": 11230,
                  "name": "Large Growth"
                },
                {
                  "id": 11231,
                  "name": "Large Value"
                },
                "..."
              ]
            },
            {
              "id": 11239,
              "name": "Sector Equity",
              "values": [
                {
                  "id": 11240,
                  "name": "Communications"
                },
                {
                  "id": 11241,
                  "name": "Consumer Cyclical"
                },
                {
                  "id": 11242,
                  "name": "Consumer Defensive"
                },
                "..."
              ]
            },
            {
              "id": 11256,
              "name": "International Equity",
              "values": [
                {
                  "id": 11257,
                  "name": "China Region"
                },
                {
                  "id": 11258,
                  "name": "Diversified Emerging Mkts"
                },
                {
                  "id": 11259,
                  "name": "Diversified Pacific/Asia"
                },
                "..."
              ]
            },
            "..."
          ]
        },
        {
          "type": "dropdown",
          "id": "issuer",
          "label": "Issuer",
          "values": [
            {
              "id": "Invesco",
              "name": "Invesco"
            },
            {
              "id": "SPDR State Street Global Advisors",
              "name": "SPDR State Street Global Advisors"
            },
            {
              "id": "iShares",
              "name": "iShares"
            },
            "..."
          ],
          "options": [
            "exclude"
          ]
        },
        "..."
      ]
    },
    {
      "id": "ratings",
      "label": "Ratings",
      "filters": [
        {
          "type": "ratings_slider",
          "id": "quant_rating",
          "label": "Quant Rating",
          "options": [
            "exclude_containing"
          ],
          "min": null,
          "max": null
        },
        {
          "type": "grades_slider",
          "id": "performance_category",
          "label": "Momentum"
        },
        {
          "type": "grades_slider",
          "id": "expenses_category",
          "label": "Expenses"
        },
        "..."
      ]
    },
    {
      "id": "performance",
      "label": "Performance",
      "filters": [
        {
          "type": "slider",
          "id": "close_to_52w",
          "label": "52 Week Range (Last Close as % of)",
          "min": 1,
          "max": 100,
          "unit": "percent"
        },
        {
          "type": "slider",
          "id": "total_return_5d",
          "label": "5D Performance",
          "min": -6,
          "max": 20,
          "unit": "percent"
        },
        {
          "type": "slider",
          "id": "price_return_1m",
          "label": "1M Performance",
          "min": -20,
          "max": 50,
          "unit": "percent"
        },
        "..."
      ]
    },
    "..."
  ]
}
```



#### 17. **`GET /screener`**
-   **Description**: This endpoint performs screening of financial instruments based on specified criteria.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `type`  | string   | `etf` | Accepted value: `etf` | `stocks`   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/screener?type=etf', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "metrics": {
    "data": [
      {
        "id": "967aaa441700",
        "type": "screener",
        "attributes": {
          "name": "All ETFs",
          "description": "All ETF screener - search and filter ETFs by fund type, class, sector, quant rating and more. ",
          "filters": {},
          "category": "public",
          "userId": null
        },
        "relationships": {
          "contentLinkBlock": {
            "data": null
          }
        },
        "meta": {
          "results_count": 4691,
          "introText": null
        }
      },
      {
        "id": "922b797269",
        "type": "screener",
        "attributes": {
          "name": "Top Rated ETFs",
          "description": "Traditional ETFs with a Quant rating of Buy or Strong Buy",
          "filters": {
            "quant_rating": {
              "gte": 3.5,
              "lte": 5,
              "exclude": false
            },
            "fund_type": {
              "in": [
                "traditional"
              ],
              "exclude": false
            }
          },
          "category": "public",
          "userId": null
        },
        "relationships": {
          "contentLinkBlock": {
            "data": null
          }
        },
        "meta": {
          "results_count": 526,
          "introText": null
        }
      },
      {
        "id": "922b7973d6",
        "type": "screener",
        "attributes": {
          "name": "Top Allocation ETFs",
          "description": "Top Allocation ETFs rated by Quant rating",
          "filters": {
            "quant_rating": {
              "gte": 3.5,
              "lte": 5,
              "exclude": false
            },
            "asset_class_id": {
              "exclude": false,
              "in": [
                11304,
                11305,
                11306,
                "..."
              ]
            }
          },
          "category": "public",
          "userId": null
        },
        "relationships": {
          "contentLinkBlock": {
            "data": null
          }
        },
        "meta": {
          "results_count": 2,
          "introText": null
        }
      },
      "..."
    ],
    "meta": {
      "page": {
        "title": "ETF Screener - Build Your Own Screener | Seeking Alpha",
        "description": "ETF ratings screener ranks by Quant or Author rating. Create your own screener or use Seeking Alpha's preset screeners."
      },
      "h1Title": "ETF Ratings Screener",
      "introText": "<p>Welcome to the Seeking Alpha ETF Screener. This is a great, easy-to-use screener, which enables you to pinpoint the market's most compelling ETFs for your specific investing strategy. Filter ETFs with Buy/Hold/Sell Quant Ratings and author recommendations. You can also screen ETFs from a range of metrics including asset class, sub-class, performance, momentum and expenses. Create your screener from scratch or use one of Seeking Alpha's preset screeners.</p>"
    }
  }
}
```



#### 18. **`GET /screener-result`**
-   **Description**: This endpoint retrieves the results of screening financial instruments based on specified criteria.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `type`  | string   | `stock` | Accepted value: `etf` | `stocks`   | No       |
| `page`  | string   | `1` | The page number of results   | No       |
| `per_page`  | string   | `100` | Number of results per page   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/screener-result?page=1&per_page=2', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "screener": {
    "data": [
      {
        "id": "604811",
        "type": "ticker",
        "attributes": {
          "slug": "clov",
          "name": "CLOV",
          "company": "Clover Health Investments, Corp.",
          "companyName": "Clover Health Investments, Corp."
        },
        "relationships": {},
        "meta": {
          "companyLogoUrlLight": "https://static.seekingalpha.com/cdn/s3/company_logos/mark_vector_light/CLOV.svg",
          "companyLogoUrlDark": "https://static.seekingalpha.com/cdn/s3/company_logos/mark_vector_dark/CLOV.svg"
        }
      },
      {
        "id": "45331",
        "type": "ticker",
        "attributes": {
          "slug": "psix",
          "name": "PSIX",
          "company": "Power Solutions International, Inc.",
          "companyName": "Power Solutions International, Inc."
        },
        "relationships": {},
        "meta": {
          "companyLogoUrlLight": "https://static.seekingalpha.com/cdn/s3/company_logos/mark_vector_light/PSIX.svg",
          "companyLogoUrlDark": "https://static.seekingalpha.com/cdn/s3/company_logos/mark_vector_dark/PSIX.svg"
        }
      }
    ],
    "meta": {
      "count": 45
    }
  }
}
```



#### 19. **`GET /market-outlook`**
-   **Description**: This endpoint retrieves market reports.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `limit`  | string   | `40` | Maximum number of reports to return   | No       |
| `page`  | string   | `1` | The page number of results   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/market-outlook?limit=2&page=1', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "market_outlook": [
    {
      "id": "4730538",
      "type": "article",
      "attributes": {
        "publishOn": "2024-10-29T14:54:48-04:00",
        "isLockedPro": false,
        "commentCount": 0,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/818871806/image_818871806.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {
          "gold-and-precious-metals": {
            "title": "Gold & Precious Metals",
            "slug": "gold-and-precious-metals"
          }
        },
        "title": "Alternative Assets Shine Amid Pre-Election Market Uncertainty",
        "structuredInsights": null,
        "isPaywalled": false
      },
      "relationships": {
        "author": {
          "data": {
            "id": "21456",
            "type": "author"
          }
        },
        "sentiments": {
          "data": []
        },
        "primaryTickers": {
          "data": []
        },
        "secondaryTickers": {
          "data": [
            {
              "id": "80",
              "type": "tag"
            },
            {
              "id": "1006",
              "type": "tag"
            },
            {
              "id": "601358",
              "type": "tag"
            }
          ]
        },
        "otherTags": {
          "data": [
            {
              "id": "10578",
              "type": "tag"
            },
            {
              "id": "4600",
              "type": "tag"
            },
            {
              "id": "9082",
              "type": "tag"
            },
            "..."
          ]
        }
      },
      "links": {
        "self": "/article/4730538-alternative-assets-shine-amid-pre-election-market-uncertainty"
      }
    },
    {
      "id": "4730553",
      "type": "article",
      "attributes": {
        "publishOn": "2024-10-29T14:21:00-04:00",
        "isLockedPro": false,
        "commentCount": 1,
        "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/1676709634/image_1676709634.jpg",
        "videoPreviewUrl": null,
        "videoDuration": null,
        "themes": {
          "gold-and-precious-metals": {
            "title": "Gold & Precious Metals",
            "slug": "gold-and-precious-metals"
          }
        },
        "title": "Gold Price Reclaims $2750/Oz Amid Record $3 Billion Inflows Into Gold Funds",
        "structuredInsights": null,
        "isPaywalled": false
      },
      "relationships": {
        "author": {
          "data": {
            "id": "24262",
            "type": "author"
          }
        },
        "sentiments": {
          "data": []
        },
        "primaryTickers": {
          "data": [
            {
              "id": "80",
              "type": "tag"
            },
            {
              "id": "81",
              "type": "tag"
            },
            {
              "id": "583597",
              "type": "tag"
            },
            "..."
          ]
        },
        "secondaryTickers": {
          "data": [
            {
              "id": "6043",
              "type": "tag"
            },
            {
              "id": "16782",
              "type": "tag"
            },
            {
              "id": "612431",
              "type": "tag"
            },
            "..."
          ]
        },
        "otherTags": {
          "data": [
            {
              "id": "17244",
              "type": "tag"
            },
            {
              "id": "4600",
              "type": "tag"
            },
            {
              "id": "9082",
              "type": "tag"
            },
            "..."
          ]
        }
      },
      "links": {
        "self": "/article/4730553-gold-price-reclaims-2750oz-amid-record-3-billion-inflows-into-gold-funds"
      }
    }
  ]
}
```



#### 20. **`GET /education/`**
-   **Description**: This endpoint retrieves educational resources based on specified categories.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `limit`  | string   | `40` | Maximum number of educational resources to return   | No       |
| `page`  | string   | `1` | The page number of results   | No       |

-   **Path Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `categoryNumber`  | string   | `40` | must be between `1`-`9`   | Yes       |


Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/education/1?limit=2&page=1', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "education": {
    "data": [
      {
        "id": "4683875",
        "type": "article",
        "attributes": {
          "publishOn": "2024-04-16T09:00:00-04:00",
          "isLockedPro": false,
          "commentCount": 0,
          "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/1214857151/image_1214857151.jpg",
          "videoPreviewUrl": null,
          "videoDuration": null,
          "themes": {
            "education-investing": {
              "title": "Investing",
              "slug": "education-investing"
            }
          },
          "title": "What Is Purchasing Power Parity?",
          "structuredInsights": null,
          "isPaywalled": false
        },
        "relationships": {
          "author": {
            "data": {
              "id": "22201",
              "type": "author"
            }
          },
          "sentiments": {
            "data": []
          },
          "primaryTickers": {
            "data": []
          },
          "secondaryTickers": {
            "data": []
          },
          "otherTags": {
            "data": [
              {
                "id": "12120",
                "type": "tag"
              },
              {
                "id": "612609",
                "type": "tag"
              },
              {
                "id": "608068",
                "type": "tag"
              },
              "..."
            ]
          }
        },
        "links": {
          "self": "/article/4683875-purchasing-power-parity"
        }
      },
      {
        "id": "4677699",
        "type": "article",
        "attributes": {
          "publishOn": "2024-03-12T16:00:00-04:00",
          "isLockedPro": false,
          "commentCount": 0,
          "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/188044888/image_188044888.jpg",
          "videoPreviewUrl": null,
          "videoDuration": null,
          "themes": {
            "education-investing": {
              "title": "Investing",
              "slug": "education-investing"
            }
          },
          "title": "Microeconomics Versus Macroeconomics - A Primer",
          "structuredInsights": null,
          "isPaywalled": false
        },
        "relationships": {
          "author": {
            "data": {
              "id": "106467",
              "type": "author"
            }
          },
          "sentiments": {
            "data": []
          },
          "primaryTickers": {
            "data": []
          },
          "secondaryTickers": {
            "data": []
          },
          "otherTags": {
            "data": [
              {
                "id": "614774",
                "type": "tag"
              },
              {
                "id": "612609",
                "type": "tag"
              },
              {
                "id": "610213",
                "type": "tag"
              },
              "..."
            ]
          }
        },
        "links": {
          "self": "/article/4677699-microeconomics-macroeconomics-differences"
        }
      }
    ],
    "meta": {
      "page": {
        "title": "Investing: How To Start, Basics, Strategies, & More",
        "description": "Know the terms, economic laws, and finance techniques investors use to participate in the stock, bond, commodity, and derivative markets. Click to see more.",
        "listTitle": "Investing Explained",
        "listDescription": "<p>Becoming a successful investor begins and continues with education. Learn more about the world of investing, from how to open a brokerage account to trading stocks, bonds, ETFs, commodities and derivatives.</p>",
        "proStatus": 0,
        "uriImage": "https://static.seekingalpha.com/assets/og_image_1200-29b2bfe1a595477db6826bd2126c63ac2091efb7ec76347a8e7f81ba17e3de6c.png",
        "size": 2,
        "totalPages": 137,
        "total": 274,
        "minmaxPublishOn": {
          "min": 1710273600,
          "max": 1713272400
        }
      },
      "mone": {
        "params": {
          "pu": ""
        }
      },
      "introText": "<p>Becoming a successful investor begins and continues with education. Learn more about the world of investing, from how to open a brokerage account to trading stocks, bonds, ETFs, commodities and derivatives.</p>",
      "h1Title": "Investing Explained"
    }
  }
}
```



#### 21. **`GET /education`**
-   **Description**: This endpoint retrieves educational resources.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `limit`  | string   | `40` | Maximum number of educational resources to return   | No       |
| `page`  | string   | `1` | The page number of results   | No       |

Example request:
```javascript
fetch('https://seeking-alpha-api.p.rapidapi.com/education?limit=2', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'seeking-alpha-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "education": {
    "data": [
      {
        "id": "4728676",
        "type": "article",
        "attributes": {
          "publishOn": "2024-10-23T12:30:49-04:00",
          "isLockedPro": false,
          "commentCount": 0,
          "gettyImageUrl": "https://static.seekingalpha.com/cdn/s3/uploads/getty_images/1297117981/image_1297117981.jpg",
          "videoPreviewUrl": null,
          "videoDuration": null,
          "themes": {
            "education-company-statistics": {
              "title": "Company Statistics",
              "slug": "education-company-statistics"
            }
          },
          "title": "Amazon Facts And Statistics In 2024",
          "structuredInsights": null,
          "isPaywalled": false
        },
        "relationships": {
          "author": {
            "data": {
              "id": "107408",
              "type": "author"
            }
          },
          "sentiments": {
            "data": []
          },
          "primaryTickers": {
            "data": []
          },
          "secondaryTickers": {
            "data": []
          },
          "otherTags": {
            "data": [
              {
                "id": "778452",
                "type": "tag"
              },
              {
                "id": "779911",
                "type": "tag"
              },
              {
                "id": "610213",
                "type": "tag"
              },
              "..."
            ]
          }
        },
        "links": {
          "self": "/article/4728676-amazon-amzn-stock-facts-statistics-2024"
        }
      },
      {
        "id": "4715551",
        "type": "article",
        "attributes": {
          "publishOn": "2024-08-19T14:00:00-04:00",
          "isLockedPro": false,
          "commentCount": 0,
          "gettyImageUrl": null,
          "videoPreviewUrl": null,
          "videoDuration": null,
          "themes": {
            "education-company-statistics": {
              "title": "Company Statistics",
              "slug": "education-company-statistics"
            }
          },
          "title": "Walmart Facts And Statistics In 2024",
          "structuredInsights": null,
          "isPaywalled": false
        },
        "relationships": {
          "author": {
            "data": {
              "id": "107408",
              "type": "author"
            }
          },
          "sentiments": {
            "data": []
          },
          "primaryTickers": {
            "data": []
          },
          "secondaryTickers": {
            "data": []
          },
          "otherTags": {
            "data": [
              {
                "id": "778452",
                "type": "tag"
              },
              {
                "id": "779911",
                "type": "tag"
              },
              {
                "id": "610213",
                "type": "tag"
              },
              "..."
            ]
          }
        },
        "links": {
          "self": "/article/4715551-walmart-2024-facts-statistics"
        }
      }
    ],
    "meta": {
      "page": {
        "title": "Investing 101: Basics for Beginner & Intermediate Investors",
        "description": "Let Seeking Alpha teach you about investing, from basic education for beginners to portfolio management and top-performance ETFs for more experienced investors.",
        "listTitle": "",
        "listDescription": "",
        "proStatus": 0,
        "uriImage": "https://static.seekingalpha.com/assets/og_image_1200-29b2bfe1a595477db6826bd2126c63ac2091efb7ec76347a8e7f81ba17e3de6c.png",
        "size": 2,
        "totalPages": 205,
        "total": 410,
        "minmaxPublishOn": {
          "min": 1724090400,
          "max": 1729701049
        }
      },
      "mone": {
        "params": {
          "pu": ""
        }
      },
      "introText": "",
      "h1Title": ""
    }
  }
}
```

## Error Handling
The  API returns standard HTTP status codes to indicate the success or failure of API requests. Below are common errors and suggestions for handling them.

|Status Code|Message|Description|Suggested Handling|
|--|--|--|--|
| **400** | Bad Request | The request was malformed or missing required parameters (e.g., `domain` parameter not provided). | Verify that all required parameters are included and correctly formatted. |
| **401** | Unauthorized | Invalid or missing API key in the request headers. | Check that a valid API key is included in `x-rapidapi-key`. |
| **403** | Forbidden | Access to the requested resource is denied, possibly due to rate limits or restricted access. | Review rate limits and ensure API permissions. Retry after a delay if rate limit exceeded. |
| **404** | Not Found | The requested domain information could not be found (e.g., domain does not exist). | Check the spelling or availability of the domain. |
| **429** | Too Many Requests | The API rate limit has been exceeded. | Implement rate-limiting logic and retry after the specified rate limit reset time. |
| **500** | Internal Server Error | A server error occurred while processing the request. | Retry the request after a few seconds. If the error persists, contact API support. |
| **503** | Service Unavailable | The API service is temporarily unavailable (e.g., due to maintenance). | Retry the request later or check the API status page for maintenance alerts. |
