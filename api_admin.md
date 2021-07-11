### API Admin

| API                              | Action                                | Date       |
| -------------------------------- | ------------------------------------- | ---------- |
| /admin/login                     | 新增登入api                             | 2021/07/03 |
| /admin/                          | 新增登出、重設密碼api                    | 2021/07/10 |
| /seriesIntroduction/             | 新增系列介紹相關api                      | 2021/07/10 |

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

### SeriesIntroduction
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
    "_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
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
