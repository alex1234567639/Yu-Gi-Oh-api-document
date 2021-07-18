### API Admin

| API                              | Action                                | Date       |
| -------------------------------- | ------------------------------------- | ---------- |
| /admin/login                     | 新增登入api                             | 2021/07/03 |
| /admin/                          | 新增登出、重設密碼api                    | 2021/07/10 |
| /seriesIntroduction/             | 新增系列介紹相關api                      | 2021/07/10 |
| /usefulCardIntroduction/         | 新增泛用卡介紹相關api                    | 2021/07/15 |
| /metaDeck/                       | 新增上位卡表相關api                      | 2021/07/15 |
| /productIntroduction/            | 新增卡表介紹相關api                      | 2021/07/15 |
| /rules/                          | 新增規則相關api                         | 2021/07/15 |
| /seriesStory/                    | 新增卡片故事相關api                      | 2021/07/15 |
| /calander/                       | 新增日曆表相關api                        | 2021/07/15 |

***

# admin-server
* url: https://xxxxxxx.com.tw/api/[path]
* method: POST

| Path                                                                       | Description              |
| -------------------------------------------------------------------------- | ------------------------ |
| [/admin/login](#adminLogin)                                                | 登入                      |
| [/admin/logout](#adminlogout)                                              | 登出                      |
| [/admin/resetpassword](#adminresetpassword)                                | 重設密碼                   |
| [/seriesIntroduction/articleList](#seriesIntroductionarticleList)          | 取得系列介紹文章            |
| [/seriesIntroduction/addArticle](#seriesIntroductionaddArticle)            | 新增系列介紹文章            |
| [/seriesIntroduction/editArticle](#seriesIntroductioneditArticle)          | 編輯系列介紹文章            |
| [/usefulCardIntroduction/articleList](#usefulCardIntroductionarticleList)  | 取得泛用卡介紹文章          |
| [/usefulCardIntroduction/addArticle](#usefulCardIntroductionaddArticle)    | 新增泛用卡介紹文章          |
| [/usefulCardIntroduction/editArticle](#usefulCardIntroductioneditArticle)  | 編輯泛用卡介紹文章          |
| [/metaDeck/articleList](#metaDeckarticleList)                              | 取得上位卡表文章            |
| [/metaDeck/addArticle](#metaDeckaddArticle)                                | 新增上位卡表文章            |
| [/metaDeck/editArticle](#metaDeckeditArticle)                              | 編輯上位卡表文章            |
| [/productIntroduction/articleList](#productIntroductionarticleList)        | 取得卡表介紹文章            |
| [/productIntroduction/addArticle](#productIntroductionaddArticle)          | 新增卡表介紹文章            |
| [/productIntroduction/editArticle](#productIntroductioneditArticle)        | 編輯卡表介紹文章            |
| [/rules/articleList](#rulesarticleList)                                    | 取得規則相關文章            |
| [/rules/addArticle](#rulesaddArticle)                                      | 新增規則相關文章            |
| [/rules/editArticle](#ruleseditArticle)                                    | 編輯規則相關文章            |
| [/seriesStory/articleList](#seriesStoryarticleList)                        | 取得卡片故事文章            |
| [/seriesStory/addArticle](#seriesStoryaddArticle)                          | 新增卡片故事文章            |
| [/seriesStory/editArticle](#seriesStoryeditArticle)                        | 編輯卡片故事文章            |
| [/calander/articleList](#calanderarticleList)                              | 取得日曆表                 |
| [/calander/addArticle](#calanderaddArticle)                                | 新增日曆表                 |
| [/calander/editArticle](#calandereditArticle)                              | 編輯日曆表                 |


***

### Admin
#### /admin/login
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

#### /admin/logout
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

#### /admin/resetpassword
request:
```json
{
    "*token":        "string",
    "*old_password": "string",
    "*new_password": "string",
}
```

response:
```json
{}
```

### Series Introduction
#### /seriesIntroduction/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "type":   0,
        "status": 0,
    },

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
            "status":         0,
            "to_top":         true,
        },
    ],

    "_comment_id": "自動生成的數字",
    "_comment_type": "0=主題牌組, 1=外掛系列",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_commemt_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

#### /seriesIntroduction/addArticle
request:
```json
{
    "*token":        "string",
    "*type":         0, 
    "*title":        "string",
    "*publish_date": "string", 
    "*photo":        "string",
    "*content":      "string", 

    "_comment_type": "0=主題牌組, 1=外掛系列",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

#### /seriesIntroduction/editArticle
request:
```json
{
    "*token":         "string",
    "id":             0,
    "type":           0,
    "title":          "string",
    "publish_date":   "string",
    "photo":          "string",
    "content":        "string", 
    "status":         0,
    "to_top":         true,

    "_comment_type": "0=主題牌組, 1=外掛系列",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### UsefulCardIntroduction
#### /usefulCardIntroduction/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "type":   0,
        "status": 0,
    },

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
            "status":         0,
            "to_top":         true,
        },
    ],

    "_comment_id": "自動生成的數字",
    "_comment_type": "0=單卡介紹, 1=戰術分析",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_commemt_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

#### /usefulCardIntroduction/addArticle
request:
```json
{
    "*token":        "string",
    "*type":         0, 
    "*title":        "string",
    "*publish_date": "string", 
    "*photo":        "string",
    "*content":      "string", 

    "_comment_type": "0=單卡介紹, 1=戰術分析",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

#### /usefulCardIntroduction/editArticle
request:
```json
{
    "*token":         "string",
    "id":             0,
    "type":           0,
    "title":          "string",
    "publish_date":   "string",
    "photo":          "string",
    "content":        "string", 
    "status":         0,
    "to_top":         true,

    "_comment_type": "0=單卡介紹, 1=戰術分析",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### MetaDeck
#### /metaDeck/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "status": 0,
    }
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
        },
    ],

    "_comment_id": "自動生成的數字",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_commemt_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

#### /metaDeck/addArticle
request:
```json
{
    "*token":        "string",
    "*title":        "string",
    "*publish_date": "string", 
    "*photo":        "string",
    "*content":      "string", 

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

#### /metaDeck/editArticle
request:
```json
{
    "*token":         "string",
    "id":             0,
    "title":          "string",
    "publish_date":   "string",
    "photo":          "string",
    "content":        "string", 
    "status":         0,
    "to_top":         true,

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```


### ProductIntroduction
#### /productIntroduction/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "type":   0,
        "status": 0,
    }
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
            "status":         0,
            "to_top":         true,
        },
    ],

    "_comment_id": "自動生成的數字",
    "_comment_type": "0=補充包, 1=預組，2=禮盒商品，3=活動贈品",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_commemt_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

#### /productIntroduction/addArticle
request:
```json
{
    "*token":        "string",
    "*type":           0,
    "*title":        "string",
    "*publish_date": "string", 
    "*photo":        "string",
    "*content":      "string", 

    "_comment_type": "0=補充包, 1=預組，2=禮盒商品，3=活動贈品",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

#### /productIntroduction/editArticle
request:
```json
{
    "*token":         "string",
    "id":             0,
    "*type":           0,
    "title":          "string",
    "publish_date":   "string",
    "photo":          "string",
    "content":        "string", 
    "status":         0,
    "to_top":         true,

    "_comment_type": "0=補充包, 1=預組，2=禮盒商品，3=活動贈品",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
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
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "type":   0,
        "status": 0,
    },

    "_comment_type": "0=禁限卡表, 1=判例說明"
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
            "status":         0,
            "to_top":         true,
        },
    ],

    "_comment_id": "自動生成的數字",
    "_comment_type": "0=禁限卡表, 1=判例說明",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_commemt_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

#### /rules/addArticle
request:
```json
{
    "*token":        "string",
    "*type":         0, 
    "*title":        "string",
    "*publish_date": "string", 
    "*photo":        "string",
    "*content":      "string", 

    "_comment_type": "0=禁限卡表, 1=判例說明",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

#### /rules/editArticle
request:
```json
{
    "*token":         "string",
    "id":             0,
    "type":           0,
    "title":          "string",
    "publish_date":   "string",
    "photo":          "string",
    "content":        "string", 
    "status":         0,
    "to_top":         true,

    "_comment_type": "0=禁限卡表, 1=判例說明",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

### SeriesStory
#### /seriesStory/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "status": 0,
    }
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
        },
    ],

    "_comment_id": "自動生成的數字",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_commemt_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

#### /seriesStory/addArticle
request:
```json
{
    "*token":        "string",
    "*title":        "string",
    "*publish_date": "string", 
    "*photo":        "string",
    "*content":      "string", 

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

#### /seriesStory/editArticle
request:
```json
{
    "*token":         "string",
    "id":             0,
    "title":          "string",
    "publish_date":   "string",
    "photo":          "string",
    "content":        "string", 
    "status":         0,
    "to_top":         true,

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```




### Calander

#### /calander/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "title":   "string",
    "url":     "string",
    "*filter": {
            "date":    "string",
            "type":    0,
    }
}
```

response:
```json
{
    "*list":
    [
        {
            "id":      0,
            "title":   "string",
            "date":    "string",
            "url":     "string",
            "type":    0,
        },
    ],

    "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_type": "0=賽事, 1=發售日期,2=其他相關活動"
}
```

#### /calander/addArticle

request:
```json
{
    "*token":        "string",
    "*title":        "string",
    "*date":         "string", 
    "*url":          "string",
    "*content":      "string", 
    "＊type":    0,

    "_comment_type": "0=賽事, 1=發售日期,2=其他相關活動",
    "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

#### /calander/editArticle

request:
```json
{
    "*token":        "string",
    "id":             0,
    "*title":        "string",
    "*date":         "string", 
    "*url":          "string",
    "*content":      "string", 
    "＊type":    0,

    "_comment_type": "0=賽事, 1=發售日期,2=其他相關活動",
    "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_content": "副文本編輯產出的html字串"
}
```
