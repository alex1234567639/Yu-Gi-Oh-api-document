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

### Request & Response
1. request或response中的comment為註解，傳遞參數時不用理會
2. 有 **\*** 號為必填欄位
3. request**未加密**格式為
```json
{
    "data":{}
}
```
4. response**未加密**格式為
```json
{
    "error_code": 0,
    "data":{}
}
```
5. Request & Response 的 data 都須作**AES**加密
6. 以下api request/response為了方便只寫出data中的內容

## Encrytion
### 規則及演算法

| Column A    | Column B              |
| ----------- | --------------------- |
| encryption  | AES CBC               |
| key         | xxxxxxxx              |
| key lengtj  | 32 bytes              |
| padding     | pkcs7                 |
| IV          | "0000000000000000"    |

### 加密方式
將data欄位加密
encrypt string 為 AES(JSON string).toString()

### Error Code

| Code                      | Description |
| ------------------------- | ----------- |
| 成功                       | 0           |
| 請求路徑錯誤                | 10001       |
| 請求方法應為POST            | 10002       |
| JSON decode failed        | 10003       |
| 請求參數不合法               | 10004       |
| token 過期                 | 10005       |
| Base64 decode failed       | 10006       |
| AES decrypt failed         | 10007       |
| 沒有權限的操作               | 10008       |
| 已從其他地方登入              | 10009       |
| 上傳圖片失敗                 | 10010       |
| JSON encode failed         | 10011       |
| 找不到使用者                 | 11001       |
| 密碼錯誤                    | 11002       |
| 註冊帳號重複                | 11003       |

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
