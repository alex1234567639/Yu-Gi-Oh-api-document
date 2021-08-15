### API Admin

| API                              | Action                                | Date       |
| -------------------------------- | ------------------------------------- | ---------- |
| /admin/login                     | 新增登入api                             | 2021/07/03 |
| /admin/                          | 新增登出、重設密碼api                    | 2021/07/10 |
| /seriesIntroduction/             | 新增系列介紹相關api                      | 2021/07/10 |
| /usefulCardIntroduction/         | 新增泛用卡介紹相關api                    | 2021/07/15 |
| /metaDeck/                       | 新增上位卡表相關api                      | 2021/07/15 |
| /productInformation/             | 新增卡表資料相關api                      | 2021/07/15 |
| /rules/                          | 新增規則相關api                         | 2021/07/15 |
| /seriesStory/                    | 新增卡片故事相關api                      | 2021/07/15 |
| /calander/                       | 新增日曆表相關api                        | 2021/07/15 |
| /productionInformation_subtype/  | 新增productionInformation_subtype api  | 2021/08/04 |
| /tag/                            | 新增tag api                            | 2021/08/04 |
| /admin/                          | 新增admin list/add/edit api            | 2021/08/04 |
| /banner/                         | 新增banner api                         | 2021/08/14 |
***

# admin-server
* url: https://xxxxxxx.com.tw/api/[path]
* method: POST

| Path                                                                       | Description              |
| -------------------------------------------------------------------------- | ------------------------ |
| [/admin/login](#adminLogin)                                                | 登入                      |
| [/admin/logout](#adminlogout)                                              | 登出                      |
| [/admin/resetpassword](#adminresetpassword)                                | 重設密碼                   |
| [/admin/list](#adminlist)                                                  | 取得帳號                   |
| [/admin/add](#adminadd)                                                    | 新增帳號                   |
| [/admin/edit](#adminedit)                                                  | 編輯帳號                   |
| [/seriesIntroduction/articleList](#seriesIntroductionarticleList)          | 取得系列介紹文章            |
| [/seriesIntroduction/addArticle](#seriesIntroductionaddArticle)            | 新增系列介紹文章            |
| [/seriesIntroduction/editArticle](#seriesIntroductioneditArticle)          | 編輯系列介紹文章            |
| [/usefulCardIntroduction/articleList](#usefulCardIntroductionarticleList)  | 取得泛用卡介紹文章          |
| [/usefulCardIntroduction/addArticle](#usefulCardIntroductionaddArticle)    | 新增泛用卡介紹文章          |
| [/usefulCardIntroduction/editArticle](#usefulCardIntroductioneditArticle)  | 編輯泛用卡介紹文章          |
| [/metaDeck/articleList](#metaDeckarticleList)                              | 取得上位卡表文章            |
| [/metaDeck/addArticle](#metaDeckaddArticle)                                | 新增上位卡表文章            |
| [/metaDeck/editArticle](#metaDeckeditArticle)                              | 編輯上位卡表文章            |
| [/productInformation/articleList](#productInformationarticleList)          | 取得卡表資料文章            |
| [/productInformation/addArticle](#productInformationaddArticle)            | 新增卡表資料文章            |
| [/productInformation/editArticle](#productInformationeditArticle)          | 編輯卡表資料文章            |
| [/rules/articleList](#rulesarticleList)                                    | 取得規則相關文章            |
| [/rules/addArticle](#rulesaddArticle)                                      | 新增規則相關文章            |
| [/rules/editArticle](#ruleseditArticle)                                    | 編輯規則相關文章            |
| [/seriesStory/articleList](#seriesStoryarticleList)                        | 取得卡片故事文章            |
| [/seriesStory/addArticle](#seriesStoryaddArticle)                          | 新增卡片故事文章            |
| [/seriesStory/editArticle](#seriesStoryeditArticle)                        | 編輯卡片故事文章            |
| [/calander/articleList](#calanderarticleList)                              | 取得日曆表                 |
| [/calander/addArticle](#calanderaddArticle)                                | 新增日曆表                 |
| [/calander/editArticle](#calandereditArticle)                              | 編輯日曆表                 |
| [/productionInformation_subtype/articleList](#productionInformation_subtypearticleList) | 取得sunbtype |
| [/productionInformation_subtype/addArticle](#productionInformation_subtypeaddArticle)   | 新增sunbtype |
| [/productionInformation_subtype/editArticle](#productionInformation_subtypeeditArticle) | 編輯sunbtype |
| [/tag/articleList](#tagarticleList)                                        | tag                      |
| [/tag/editArticle](#tageditArticle)                                        | tag                      |
| [/banner/articleList](#bannerarticleList)                                  | 取得sunbtype              |
| [/banner/addArticle](#banneraddArticle)                                    | 新增sunbtype              |
| [/banner/editArticle](#bannereditArticle)                                  | 編輯sunbtype              |


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

#### /admin/list
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "type":    0,
        "status":  0,
        "name" :   "string",
        "acount" : "string"
    },

    "_comment_type": "0=管理者, 1=一般用戶",
    "_comment_status": "0=正常, 1=停用中"
}
```

response:
```json
{
    "*list":
    [
        {
            "id":          0,
            "type":        0,
            "name":        "string",
            "create_date": "string", 
            "photo":       "string",
            "status":      0,
            "acount":      "string",
            "password":    "sting"
        },
    ],

    "_comment_id": "自動生成的數字",
    "_comment_type": "0=管理者, 1=一般用戶",
    "_comment_status": "0=正常, 1=停用中",
    "_comment_name": "length = 20",
    "_comment_acount": "max length = 16, min length = 8",
    "_comment_password": "max length = 16, min length = 8",
}
```

#### /admin/add

request:
```json
{
    "*id":          0,
    "*type":        0,
    "*name":        "string",
    "*create_date": "string", 
    "*photo":       "string",
    "*status":      0,
    "acount":       "string",
    "password":     "sting",

    "_comment_type": "0=主題牌組, 1=外掛系列",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_name": "length = 20",
    "_comment_acount": "length = 16",
    "_comment_password": "max length = 16, min length = 8",
}
```

response:
```json
{}
```

#### /admin/edit

request:
```json
{
    "*id":          0,
    "*type":        0,
    "*name":        "string",
    "*create_date": "string", 
    "*photo":       "string",
    "*status":      0,

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



### Series Introduction
#### /seriesIntroduction/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "type":       0,
        "status":     0,
        "begin_date": "string",
        "end_date":   "string"
    },

    "_comment_type": "0=主題牌組, 1=外掛系列",
    "_comment_begin_date": "搜尋publish_date range"
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
            "author_name":    "string", 
            "author_id":      0, 
            "tag":            [], 
            
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
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

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
    "*token":        "string",
    "*id":           0,
    "*type":         0,
    "*title":        "string",
    "*publish_date": "string",
    "*photo":        "string",
    "*content":      "string", 
    "*status":       0,
    "*to_top":       true,
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

    "_comment_type": "0=主題牌組, 1=外掛系列",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

response:
```json
{}
```

### Useful Card Introduction
#### /usefulCardIntroduction/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "type":       0,
        "status":     0,
        "begin_date": "string",
        "end_date":   "string"
    },

    "_comment_type": "0=單卡介紹, 1=戰術分析",
    "_comment_begin_date": "搜尋publish_date range"
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
            "*author_name":   "string", 
            "*author_id":     0, 
            "*tag":           [], 
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
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

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
    "*token":        "string",
    "id":            0,
    "*type":         0,
    "*title":        "string",
    "*publish_date": "string",
    "*photo":        "string",
    "*content":      "string", 
    "*status":       0,
    "*to_top":       true,
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

    "_comment_type": "0=單卡介紹, 1=戰術分析",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
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
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "status":     0,
        "begin_date": "string",
        "end_date":   "string"
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
            "*author_name":  "string", 
            "*author_id":    0, 
            "*tag":          [], 
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
    "*author_name":  "string",  
    "*author_id":    0, 
    "*tag":          [], 

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
    "*token":        "string",
    "*id":           0,
    "*title":        "string",
    "*publish_date": "string",
    "*photo":        "string",
    "*content":      "string", 
    "*status":       0,
    "*to_top":       true,
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

response:
```json
{}
```

### Product Information
#### /productInformation/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "type":       0,
        "status":     0,
        "begin_date": "string",
        "end_date":   "string"
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
            "*productionInformation_subtype":       0,
            "title":          "string",
            "publish_date":   "string", 
            "last_edit_date": "string",
            "photo":          "string",
            "content":        "string", 
            "status":         0,
            "to_top":         true,
            "*author_name":   "string", 
            "*author_id":     0, 
            "*tag":           [], 
        },
    ],

    "_comment_id": "自動生成的數字",
    "_comment_type": "0=RD, 1=補充包, 2=預組套牌, 3=禮盒, 4=活動商品",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_commemt_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

#### /productInformation/addArticle
request:
```json
{
    "*token":        "string",
    "*type":         0,
    "*productionInformation_subtype":        0,
    "*title":        "string",
    "*publish_date": "string", 
    "*photo":        "string",
    "*content":      "string", 
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

    "_comment_type": "0=RD, 1=補充包, 2=預組套牌, 3=禮盒, 4=活動商品",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

#### /productInformation/editArticle
request:
```json
{
    "*token":        "string",
    "*id":           0,
    "*type":         0,
    "*productionInformation_subtype":        0,
    "*title":        "string",
    "*publish_date": "string",
    "*photo":        "string",
    "*content":      "string", 
    "*status":       0,
    "*to_top":       true,
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

    "_comment_type": "0=RD, 1=補充包, 2=預組套牌, 3=禮盒, 4=活動商品",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

response:
```json
{}
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
        "type":       0,
        "status":     0,
        "begin_date": "string",
        "end_date":   "string"
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
            "*author_name":   "string", 
            "*author_id":     0, 
            "*tag":           [], 
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
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

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
    "*token":        "string",
    "*id":           0,
    "*type":         0,
    "*title":        "string",
    "*publish_date": "string",
    "*photo":        "string",
    "*content":      "string", 
    "*status":       0,
    "*to_top":       true,
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

    "_comment_type": "0=禁限卡表, 1=判例說明",
    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

response:
```json
{}
```

### Series Story
#### /seriesStory/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "status":     0,
        "begin_date": "string",
        "end_date":   "string"
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
            "*author_name":   "string",  
            "*author_id":     0, 
            "*tag":           [], 
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
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

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
    "*token":        "string",
    "*id":           0,
    "*title":        "string",
    "*publish_date": "string",
    "*photo":        "string",
    "*content":      "string", 
    "*status":       0,
    "*to_top":       true,
    "*author_name":  "string", 
    "*author_id":    0, 
    "*tag":          [], 

    "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_photo": "btoa()編碼的Base64字串",
    "_comment_content": "副文本編輯產出的html字串",
    "_comment_status": "0=上架中, 1=下架中",
    "_comment_to_top": "true=置頂, false=非置頂"
}
```

response:
```json
{}
```


### Calander
#### /calander/articleList
request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "title":  "string",
    "url":    "string",
    "*filter": {
        "date":  "string",
         "type": 0,
    }
}
```

response:
```json
{
    "*list":
    [
        {
            "id":    0,
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

#### /calander/addArticle

request:
```json
{
    "*token":   "string",
    "*title":   "string",
    "*date":    "string", 
    "*url":     "string",
    "*content": "string", 
    "＊type":   0,

    "_comment_type": "0=賽事, 1=發售日期, 2=其他相關活動",
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
    "*token":   "string",
    "id":       0,
    "*title":   "string",
    "*date":    "string", 
    "*url":     "string",
    "*content": "string", 
    "＊type":   0,
    "*photo":   "string",

    "_comment_type": "0=賽事, 1=發售日期, 2=其他相關活動",
    "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
    "_comment_content": "副文本編輯產出的html字串"
}
```

response:
```json
{}
```

### productionInformation_subtype
#### /productionInformation_subtype/articleList

request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "maintype": 0,
    }
}
```

response:
```json
{
    "*list":
    [
        {
            "id":    0,
            "productionInformation_subtype": "string",
            "maintype":  0,
        },
    ],
}
```


#### /productionInformation_subtype/addArticle

request:
```json
{
    "*token":   "string",
    "*productionInformation_subtype": "string",
    "maintype": 0,

}
```

response:
```json
{}
```

#### /productionInformation_subtype/editArticle

request:
```json
{
    "*token":   "string",
    "id":       0,
    "*productionInformation_subtype": "string",
    "maintype": 0,
}
```

response:
```json
{}
```

### tag
#### /tag/articleList

request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "tag": "string",
    }
}
```

response:
```json
{
    "*list":
    [
        {
            "id":    0,
            "tag": "string",
        },
    ],
}
```

response:
```json
{}
```

#### /tag/editArticle

request:
```json
{
    "*token": "string",
    "id":     0,
    "*tag":   "string",
}
```

response:
```json
{}
```

### banner
#### /banner/articleList

request:
```json
{
    "*token": "string",
    "page":   0,
    "limit":  0,
    "*filter": {
        "begin_date": 0,
        "end_date":   0
    }
}
```

response:
```json
{
    "*list":
    [
        {
            "id":           0,
            "title":        "string",
            "subtitle":     "string",
            "date":         "string",
            "photo_pc":     "string",
            "photo_mobile": "string",
            "url":          "string"
        },
    ],
}
```


#### /banner/addArticle

request:
```json
{
    "*token":        "string",
    "*title":        "string",
    "*subtitle":     "string",
    "*date":         "string",
    "*photo_pc":     "string",
    "*photo_mobile": "string",
    "*url":          "string"

}
```

response:
```json
{}
```

#### /banner/editArticle

request:
```json
{
    "*token":        "string",
    "*title":        "string",
    "*subtitle":     "string",
    "*date":         "string",
    "*photo_pc":     "string",
    "*photo_mobile": "string",
    "*url":          "string"
}
```

response:
```json
{}
```