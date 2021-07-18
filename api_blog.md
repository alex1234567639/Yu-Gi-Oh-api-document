### API Blog

| API                                    | Action                                | Date       |
| -------------------------------------- | ------------------------------------- | ---------- |
| /metaDeck/articleList                  | 新增取得上位卡表文章api                   | 2021/07/11 |
| /seriesIntroduction/articleList        | 新增取得系列介紹文章api                   | 2021/07/11 |
| /usefulCardIntroduction/articleList    | 新增取得泛用卡介紹文章api                 | 2021/07/11 |
| /productIntroduction/articleList       | 新增取得卡表介紹文章api                   | 2021/07/14 |
| /rules/articleList                     | 新增取得規則相關文章api                   | 2021/07/14 |
| /seriesStory/articleList               | 新增取得卡片故事文章api                   | 2021/07/14 |
| /calander/list                         | 新增日曆表api                           | 2021/07/14 |

***

# blog-server
* url: https://xxxxxxx.com.tw/api/[path]
* method: POST

| Path                                                                       | Description              |
| -------------------------------------------------------------------------- | ------------------------ |
| [/metaDeck/articleList](#metaDeckarticleList)                              | 取得上位卡表文章            |
| [/seriesIntroduction/articleList](#seriesIntroductionarticleList)          | 取得系列介紹文章            |
| [/usefulCardIntroduction/articleList](#usefulCardIntroductionarticleList)  | 取得泛用卡介紹文章          |
| [/productIntroduction/articleList](#productIntroductionarticleList)        | 取得卡表介紹文章            |
| [/rules/articleList](#rulesarticleList)                                    | 取得規則相關文章            |
| [/seriesStory/articleList](#seriesStoryarticleList)                        | 取得卡片故事文章            |
| [/calander/list](#calanderlist)                                            | 取得日曆表                 |

***

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
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "status":         0,
            "to_top":         true,
            "tag":            "array"
        },
    ],

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂",
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
            "type":           0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true,
        },
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
            "type":           0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true,
        },
    ],

    "_comment_type": "0=單卡介紹, 1=戰術分析",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### Production Introduction
#### /productIntroduction/articleList
request:
```json
{
    "page":  0,
    "limit": 0,
    "type":  0,

    "_comment_type": "0=補充包, 1=預組"
}
```

response:
```json
{
    "*list":
    [
        {
            "id":             0,
            "type":           0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true,
        },
    ],

    "_comment_type": "0=補充包, 1=預組, 2=禮盒商品, 3=活動贈品",
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
            "type":           0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true,
        },
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
    "limit": 0,
}
```

response:
```json
{
    "*list":
    [
        {
            "id":             0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "tag":            "array",
            "status":         0,
            "to_top":         true,
        },
    ],

    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### Calendar
#### /calander/list
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
            "url":   "string",
            "type":  0,
        },
    ],

    "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_type": "0=賽事, 1=發售日期, 2=其他相關活動"
}
```
