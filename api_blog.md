### API Blog


| API                                 | Action          | Date       |
|-------------------------------------|-----------------|------------|
| /metaDeck/articleList               | 新增取得上位卡表文章api   | 2021/07/11 |
| /seriesIntroduction/articleList     | 新增取得系列介紹文章api   | 2021/07/11 |
| /usefulCardIntroduction/articleList | 新增取得泛用卡介紹文章api  | 2021/07/11 |
| /productInformation/articleList     | 新增取得卡表資料文章api   | 2021/07/14 |
| /rules/articleList                  | 新增取得規則相關文章api   | 2021/07/14 |
| /seriesStory/articleList            | 新增取得卡片故事文章api   | 2021/07/14 |
| /calendar/list                      | 新增日曆表api        | 2021/07/14 |
| /banner/list                        | 新增banner列表api   | 2021/07/28 |
| /banner/list                        | 修改banner列表api欄位 | 2021/07/28 |
| /search                             | 新增search api    | 2021/08/08 |
| /cards/                             | 新增cards相關api    | 2022/10/30 |
| /deck/                              | 新增deck相關api     | 2022/10/30 |
| /member/                            | 新增會員相關api       | 2022/10/31 |

***

# blog-server
* url: https://xxxxxxx.com.tw/api/[path]
* method: POST


| Path                                                                      | Description |
|---------------------------------------------------------------------------|-------------|
| [/member/login](#memberlogin)                                             | 登入          |
| [/member/logout](#memberlogout)                                           | 登出          |
| [/member/resetPassword](#memberresetpassword)                             | 重設密碼        |
| [/member/add](#memberadd)                                                 | 會員註冊        |
| [/member/edit](#memberedit)                                               | 編輯會員帳號      |
| [/metaDeck/articleList](#metadeckarticlelist)                             | 取得上位卡表文章    |
| [/seriesIntroduction/articleList](#seriesintroductionarticlelist)         | 取得系列介紹文章    |
| [/usefulCardIntroduction/articleList](#usefulcardintroductionarticlelist) | 取得泛用卡介紹文章   |
| [/productInformation/articleList](#productinformationarticlelist)         | 取得卡表資料文章    |
| [/rules/articleList](#rulesarticlelist)                                   | 取得規則相關文章    |
| [/seriesStory/articleList](#seriesstoryarticlelist)                       | 取得卡片故事文章    |
| [/calendar/list](#calendarlist)                                           | 取得日曆表       |
| [/banner/list](#bannerlist)                                               | 取得banner列表  |
| [/search](#search)                                                        | Search文章    |
| [/cards/cardsList](#cardscardslist)                                       | 取得卡片資料      |
| [/deck/deckList](#deckdecklist)                                           | 取得卡表列表      |
| [/deck/add](#deckadd)                                                     | 新增卡表        |
| [/deck/edit](#deckedit)                                                   | 編輯卡表        |
| [/deck/delete](#deckdelete)                                               | 刪除卡表        |
 
***

### Member
#### /member/login
request:
```json
{
    "*account":  "string",
    "*password": "string"
}
```

response:
```json
{
    "token": "string"
}
```

#### /member/logout
request:
```json
{
    "*token": "string",
    "*ip":    "string"
}
```

response:
```json
{}
```

#### /member/resetPassword
request:
```json
{
    "*token":        "string",
    "*old_password": "string",
    "*new_password": "string"
}
```

response:
```json
{}
```

#### /member/add
request:
```json
{
    "*name":        "string",
    "*create_date": "string", 
    "*account":     "string",
    "*password":    "sting",

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_name": "length = 20",
    "_comment_account": "length = 16",
    "_comment_password": "max length = 16, min length = 8"
}
```

response:
```json
{}
```

#### /member/edit
request:
```json
{
    "*token":  "string",
    "*id":     0,
    "*name":   "string",
    "*photo":  "string",

    "_comment_photo": "btoa()編碼的Base64字串"
}
```

response:
```json
{}
```

### Meta Deck
#### /metaDeck/articleList
request:
```json
{
    "page":  0,
    "limit": 0
}
```

response:
```json
{
    "*list":
    [
        {
            "id":             0,
            "author_id":      0,
            "author_name":    "string",
            "title":          "string",  
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "status":         0,
            "to_top":         true,
            "tag":            "array"
        }
    ],

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### Series Introduction
#### /seriesIntroduction/articleList
request:
```json
{
    "page":  0,
    "limit": 0,
    "type":  0,

    "_comment_type": "0=主題牌組, 1=外掛系列"
}
```

response:
```json
{
    "*list":
    [
        {
            "id":             0,
            "author_id":      0,
            "author_name":    "string",
            "type":           0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true
        }
    ],

    "_comment_type": "0=主題牌組, 1=外掛系列",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### Useful Card Introduction
#### /usefulCardIntroduction/articleList
request:
```json
{
    "page":  0,
    "limit": 0,
    "type":  0,

    "_comment_type": "0=單卡介紹, 1=戰術分析"
}
```

response:
```json
{
    "*list":
    [
        {
            "id":             0,
            "author_id":      0,
            "author_name":    "string",
            "type":           0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true
        }
    ],

    "_comment_type": "0=單卡介紹, 1=戰術分析",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### Product Information
#### /productInformation/articleList
request:
```json
{
    "page":    0,
    "limit":   0,
    "type":    0,
    "subtype": 0,

    "_comment_type": "0=RD, 1=補充包, 2=預組套牌, 3=禮盒, 4=活動贈品"
}
```

response:
```json
{
    "*list":
    [
        {
            "id":             0,
            "author_id":      0,
            "author_name":    "string",
            "type":           0,
            "subtype":        0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true
        }
    ],

    "_comment_type": "0=RD, 1=補充包, 2=預組套牌, 3=禮盒, 4=活動贈品",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### Rules
#### /rules/articleList
request:
```json
{
    "page":  0,
    "limit": 0,
    "type":  0,

    "_comment_type": "0=判例, 1=禁卡表"
}
```

response:
```json
{
    "*list":
    [
        {
            "id":             0,
            "author_id":      0,
            "author_name":    "string",
            "type":           0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true
        }
    ],

    "_comment_type": "0=判例, 1=禁卡表",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### Series Story
#### /seriesStory/articleList
request:
```json
{
    "page":  0,
    "limit": 0
}
```

response:
```json
{
    "*list":
    [
        {
            "id":             0,
            "author_id":      0,
            "author_name":    "string",
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true
        }
    ],

    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### Calendar
#### /calendar/list
request:
```json
{}
```

response:
```json
{
    "*list":
    [
        {
            "title": "string",
            "date":  "string",
            "photo": "string", 
            "url":   "string",
            "type":  0
        }
    ],

    "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_url": "連結",
    "_comment_type": "0=賽事, 1=發售日期, 2=其他相關活動"
}
```

### Banner
#### /banner/list
request:
```json
{}
```

response:
```json
{
    "*list":
    [
        {
            "title":        "string",
            "subtitle":     "string",
            "date":         "string",
            "photo_pc":     "string", 
            "photo_mobile": "string", 
            "url":          "string"
        }
    ],

    "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_url": "連結"
}
```

### Search
#### /search
request:
```json
{
    "content":         "string",
    "*article_type":   0,
    "article_subtype": 0,

    "_comment_content": "搜尋的文字",
    "_comment_article_type": "0=系列介紹, 1=泛用卡介紹, 2=卡表資料, 3=上位卡表, 4=卡片故事, 5=規則相關",
    "_comment_subtype": "article_type各自的子類型"
}
```


### Cards
#### /cards/cardsList

request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "number":    "string",
        "name":      "string",
        "type":      "string",
        "star":      "string",
        "attribute": "string",
        "rarity":    "string",
        "atk_t":       0,
        "atk_l":       0,
        "def_t":       0,
        "def_l":       0,
        "packType":  "string",
        "id":        0
    },

    "_comment_number": "卡號",
    "_comment_name": "卡名",
    "_comment_type": "種類",
    "_comment_star": "星數",
    "_comment_attribute": "屬性",
    "_comment_rarity": "稀有度、版本",
    "_comment_packType": "包裝分類",
    "_comment_id": "卡片密碼"
}
```

response:
```json
{
  "*total": 0,
  "*list":
  [
    {
      "number":    "string",
      "name":      "string",
      "type":      "string",
      "star":      "string",
      "attribute": "string",
      "rarity":    "string",
      "atk":       0,
      "def":       0,
      "packType":  "string",
      "id":        0,
      "effect":    "string",
      "photo":     "string",
      "price_info":     [
        {
          "time": "string",
          "price": 0
        }
      ]
    }
  ],

  "_comment_effect": "卡片效果",
  "_comment_photo": "卡圖"
}
```

### Deck
#### /deck/deckList
request:
```json
{
    "page":  0,
    "limit": 0,
    "*filter": {
        "number":         "string",
        "title":          "string",
        "last_edit_date": "string"
    },

    "_comment_number": "卡號",
    "_comment_title": "牌組名稱",
    "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss"
}
```

response:
```json
{
    "total": 0,
    "*list":
    [
        {
            "id":             0,
            "*author_name":   "string",
            "*author_id":     0,
            "title":          "string",  
            "create_date":    "string", 
            "last_edit_date": "string",
            "main_deck":[
              {
                "number":     "string",
                "name":       "string",
                "type":       "string",
                "star":       "string",
                "attribute":  "string",
                "rarity":     "string",
                "atk":        0,
                "def":        0,
                "packType":   "string",
                "id":         0,
                "effect":     "string",
                "photo":      "string",
                "price_info":[
                  {
                    "time":   "string",
                    "price":  0
                  }
                ]
              }
            ],
            "extra_deck":     [],
            "side_deck":      []
        }
    ],

    "_comment_create_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss"
}
```

#### /deck/add
request:
```json
{
    "*token":         "string",
    "title":          "string",  
    "create_date":    "string", 
    "last_edit_date": "string",
    "*author_name":   "string",
    "*author_id":     0,
    "main_deck":[
      {
        "number":     "string",
        "rarity":     "string"
      }
    ],
    "extra_deck":     [],
    "side_deck":      []
}
```

response:
```json
{}
```

#### /deck/edit
request:
```json
{
    "*token":         "string",
    "id":             0,
    "title":          "string",  
    "last_edit_date": "string",
    "*author_name":   "string",
    "*author_id":     0,
    "main_deck":[
      {
        "number":     "string",
        "rarity":     "string"
      }
    ],
    "extra_deck":     [],
    "side_deck":      []
}
```

response:
```json
{}
```

#### /deck/delete
request:
```json
{
    "*token":         "string",
    "id":             0
}
```

response:
```json
{}
```
