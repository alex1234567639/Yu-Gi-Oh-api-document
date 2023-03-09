### API Admin

| API                         | Action                             | Date       |
| --------------------------- | ---------------------------------- | ---------- |
| /admin/login                | 新增登入 api                       | 2021/07/03 |
| /admin/                     | 新增登出、重設密碼 api             | 2021/07/10 |
| /seriesIntroduction/        | 新增系列介紹相關 api               | 2021/07/10 |
| /usefulCardIntroduction/    | 新增泛用卡介紹相關 api             | 2021/07/15 |
| /metaDeck/                  | 新增上位卡表相關 api               | 2021/07/15 |
| /productInformation/        | 新增卡表資料相關 api               | 2021/07/15 |
| /rules/                     | 新增規則相關 api                   | 2021/07/15 |
| /seriesStory/               | 新增卡片故事相關 api               | 2021/07/15 |
| /calendar/                  | 新增日曆表相關 api                 | 2021/07/15 |
| /productionInformationType/ | 新增 productionInformationType api | 2021/08/04 |
| /tag/                       | 新增 tag api                       | 2021/08/04 |
| /admin/                     | 新增 admin list/add/edit api       | 2021/08/04 |
| /banner/                    | 新增 banner api                    | 2021/08/14 |
| /battlePaper/               | 新增戰報 api                       | 2022/10/30 |
| /cardPrice/                 | 新增卡價 api                       | 2022/10/30 |
| /cards/                     | 新增 cards 相關 api                | 2022/10/30 |
| /packType/                  | 新增卡包類別相關 api               | 2022/10/31 |

---

# admin-server

- url: https://xxxxxxx.com.tw/api/[path]
- method: POST

| Path                                                                      | Description        |
| ------------------------------------------------------------------------- | ------------------ |
| [/admin/login](#adminlogin)                                               | 登入               |
| [/admin/logout](#adminlogout)                                             | 登出               |
| [/admin/resetPassword](#adminresetpassword)                               | 重設密碼           |
| [/admin/list](#adminlist)                                                 | 取得帳號           |
| [/admin/add](#adminadd)                                                   | 新增帳號           |
| [/admin/edit](#adminedit)                                                 | 編輯帳號           |
| [/seriesIntroduction/articleList](#seriesintroductionarticlelist)         | 取得系列介紹文章   |
| [/seriesIntroduction/addArticle](#seriesintroductionaddarticle)           | 新增系列介紹文章   |
| [/seriesIntroduction/editArticle](#seriesintroductioneditarticle)         | 編輯系列介紹文章   |
| [/usefulCardIntroduction/articleList](#usefulcardintroductionarticlelist) | 取得泛用卡介紹文章 |
| [/usefulCardIntroduction/addArticle](#usefulcardintroductionaddarticle)   | 新增泛用卡介紹文章 |
| [/usefulCardIntroduction/editArticle](#usefulcardintroductioneditarticle) | 編輯泛用卡介紹文章 |
| [/metaDeck/articleList](#metadeckarticlelist)                             | 取得上位卡表文章   |
| [/metaDeck/addArticle](#metadeckaddarticle)                               | 新增上位卡表文章   |
| [/metaDeck/editArticle](#metadeckeditarticle)                             | 編輯上位卡表文章   |
| [/productInformation/articleList](#productinformationarticlelist)         | 取得卡表資料文章   |
| [/productInformation/addArticle](#productinformationaddarticle)           | 新增卡表資料文章   |
| [/productInformation/editArticle](#productinformationeditarticle)         | 編輯卡表資料文章   |
| [/rules/articleList](#rulesarticlelist)                                   | 取得規則相關文章   |
| [/rules/addArticle](#rulesaddarticle)                                     | 新增規則相關文章   |
| [/rules/editArticle](#ruleseditarticle)                                   | 編輯規則相關文章   |
| [/seriesStory/articleList](#seriesstoryarticlelist)                       | 取得卡片故事文章   |
| [/seriesStory/addArticle](#seriesstoryaddarticle)                         | 新增卡片故事文章   |
| [/seriesStory/editArticle](#seriesstoryeditarticle)                       | 編輯卡片故事文章   |
| [/calendar/articleList](#calendararticlelist)                             | 取得日曆表         |
| [/calendar/addArticle](#calendaraddarticle)                               | 新增日曆表         |
| [/calendar/editArticle](#calendareditarticle)                             | 編輯日曆表         |
| [/productionInformationType/list](#productioninformationtypelist)         | 取得 subtype       |
| [/tag/articleList](#tagarticlelist)                                       | tag                |
| [/tag/editArticle](#tageditarticle)                                       | tag                |
| [/banner/articleList](#bannerarticlelist)                                 | 取得 subtype       |
| [/banner/addArticle](#banneraddarticle)                                   | 新增 subtype       |
| [/banner/editArticle](#bannereditarticle)                                 | 編輯 subtype       |
| [/battlePaper/articleList](#battlepaperarticlelist)                       | 取得戰報相關文章   |
| [/battlePaper/addArticle](#battlepaperaddarticle)                         | 新增戰報相關文章   |
| [/battlePaper/editArticle](#battlepapereditarticle)                       | 編輯戰報相關文章   |
| [/cards/cardsList](#cardscardslist)                                       | 取得卡片資料       |
| [/cards/add](#cardsadd)                                                   | 新增卡片           |
| [/cards/edit](#cardsedit)                                                 | 編輯卡片           |
| [/packType/packTypeList](#packtypepacktypelist)                           | 取得包裝分類       |
| [/packType/add](#packtypeadd)                                             | 新增包裝分類       |
| [/packType/edit](#packtypeedit)                                           | 編輯包裝分類       |

---

### Admin

#### /admin/login

request:

```json
{
  "*account": "string",
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
  "*ip": "string"
}
```

response:

```json
{}
```

#### /admin/resetPassword

request:

```json
{
  "*token": "string",
  "*old_password": "string",
  "*new_password": "string"
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
  "page": 0,
  "limit": 0,
  "*filter": {
    "type": 0,
    "status": 0,
    "name": "string",
    "account": "string"
  },

  "_comment_type": "0=管理者, 1=前後台用戶, 2=前台用戶",
  "_comment_status": "0=正常, 1=停用中"
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "type": 0,
      "name": "string",
      "create_date": "string",
      "photo": "string",
      "status": 0,
      "account": "string",
      "password": "sting"
    }
  ],

  "_comment_id": "自動生成的數字",
  "_comment_type": "0=管理者, 1=前後台用戶, 2=前台用戶",
  "_comment_status": "0=正常, 1=停用中",
  "_comment_name": "length = 20",
  "_comment_account": "max length = 16, min length = 8",
  "_comment_password": "max length = 16, min length = 8"
}
```

#### /admin/add

request:

```json
{
  "*type": 0,
  "*name": "string",
  "*create_date": "string",
  "*account": "string",
  "*password": "sting",

  "_comment_type": "0=管理者, 1=前後台用戶, 2=前台用戶",
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

#### /admin/edit

request:

```json
{
  "*token": "string",
  "*id": 0,
  "*type": 0,
  "*name": "string",
  "*photo": "string",
  "*status": 0,

  "_comment_type": "0=管理者, 1=前後台用戶, 2=前台用戶",
  "_comment_photo": "btoa()編碼的Base64字串",
  "_comment_status": "0=正常, 1=停用中"
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
  "page": 0,
  "limit": 0,
  "*filter": {
    "type": 0,
    "status": 0,
    "begin_date": "string",
    "end_date": "string"
  },

  "_comment_type": "0=主題牌組, 1=外掛系列",
  "_comment_begin_date": "搜尋publish_date range"
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "type": 0,
      "title": "string",
      "publish_date": "string",
      "last_edit_date": "string",
      "photo": "string",
      "content": "string",
      "status": 0,
      "to_top": true,
      "author_name": "string",
      "author_id": 0,
      "tag": []
    }
  ],

  "_comment_id": "自動生成的數字",
  "_comment_type": "0=主題牌組, 1=外掛系列",
  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
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
  "*token": "string",
  "*type": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "*token": "string",
  "*id": 0,
  "*type": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*status": 0,
  "*to_top": true,
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "page": 0,
  "limit": 0,
  "*filter": {
    "type": 0,
    "status": 0,
    "begin_date": "string",
    "end_date": "string"
  },

  "_comment_type": "0=單卡介紹, 1=戰術分析",
  "_comment_begin_date": "搜尋publish_date range"
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "type": 0,
      "title": "string",
      "publish_date": "string",
      "last_edit_date": "string",
      "photo": "string",
      "content": "string",
      "status": 0,
      "to_top": true,
      "*author_name": "string",
      "*author_id": 0,
      "*tag": []
    }
  ],

  "_comment_id": "自動生成的數字",
  "_comment_type": "0=單卡介紹, 1=戰術分析",
  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
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
  "*token": "string",
  "*type": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "*token": "string",
  "id": 0,
  "*type": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*status": 0,
  "*to_top": true,
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "page": 0,
  "limit": 0,
  "*filter": {
    "status": 0,
    "begin_date": "string",
    "end_date": "string"
  }
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "title": "string",
      "publish_date": "string",
      "last_edit_date": "string",
      "photo": "string",
      "content": "string",
      "status": 0,
      "to_top": true,
      "*author_name": "string",
      "*author_id": 0,
      "*tag": []
    }
  ],

  "_comment_id": "自動生成的數字",
  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
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
  "*token": "string",
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "*token": "string",
  "*id": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*status": 0,
  "*to_top": true,
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "page": 0,
  "limit": 0,
  "*filter": {
    "status": 0,
    "begin_date": "string",
    "end_date": "string",
    "packType": "string",
    "subtype": "string",
    "maintype": 0
  }
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "packType": "string",
      "subtype": "string",
      "maintype": 0,
      "name": "string",
      "title": "string",
      "publish_date": "string",
      "last_edit_date": "string",
      "photo": "string",
      "content": "string",
      "status": 0,
      "to_top": true,
      "*author_name": "string",
      "*author_id": 0,
      "*tag": []
    }
  ],
  "_comment_id": "自動生成的數字",
  "_comment_type": "0=RD, 1=補充包, 2=預組套牌, 3=禮盒, 4=活動商品",
  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_photo": "btoa()編碼的Base64字串",
  "_comment_content": "副文本編輯產出的html字串",
  "_comment_status": "0=上架中, 1=下架中",
  "_comment_to_top": "true=置頂, false=非置頂",
  "_comment_packType": "產品代號",
  "_comment_maintype": "產品分類 0=補充包 1=Rush Duel 2=活動贈品 3=預組套牌",
  "_comment_subtype": "產品系列名稱(PP大會包...)",
  "_comment_name": "產品名稱"
}
```

#### /productInformation/addArticle

request:

```json
{
  "*token": "string",
  "*productInformationTypeId": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_photo": "btoa()編碼的Base64字串",
  "_comment_content": "副文本編輯產出的html字串",
  "_comment_productInformationTypeId": "product_information_type id"
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
  "*token": "string",
  "*id": 0,
  "*productInformationTypeId": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*status": 0,
  "*to_top": true,
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_photo": "btoa()編碼的Base64字串",
  "_comment_content": "副文本編輯產出的html字串",
  "_comment_status": "0=上架中, 1=下架中",
  "_comment_to_top": "true=置頂, false=非置頂",
  "_comment_productInformationTypeId": "product_information_type id"
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
  "page": 0,
  "limit": 0,
  "*filter": {
    "type": 0,
    "status": 0,
    "begin_date": "string",
    "end_date": "string"
  },

  "_comment_type": "0=禁限卡表, 1=判例說明"
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "type": 0,
      "title": "string",
      "publish_date": "string",
      "last_edit_date": "string",
      "photo": "string",
      "content": "string",
      "status": 0,
      "to_top": true,
      "*author_name": "string",
      "*author_id": 0,
      "*tag": []
    }
  ],

  "_comment_id": "自動生成的數字",
  "_comment_type": "0=禁限卡表, 1=判例說明",
  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
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
  "*token": "string",
  "*type": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "*token": "string",
  "*id": 0,
  "*type": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*status": 0,
  "*to_top": true,
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "page": 0,
  "limit": 0,
  "*filter": {
    "status": 0,
    "begin_date": "string",
    "end_date": "string"
  }
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "title": "string",
      "publish_date": "string",
      "last_edit_date": "string",
      "photo": "string",
      "content": "string",
      "status": 0,
      "to_top": true,
      "*author_name": "string",
      "*author_id": 0,
      "*tag": []
    }
  ],

  "_comment_id": "自動生成的數字",
  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
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
  "*token": "string",
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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
  "*token": "string",
  "*id": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*status": 0,
  "*to_top": true,
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

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

### Calendar

#### /calendar/articleList

request:

```json
{
  "*token": "string",
  "page": 0,
  "limit": 0,
  "title": "string",
  "url": "string",
  "*filter": {
    "date": "string",
    "type": 0
  }
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "title": "string",
      "date": "string",
      "url": "string",
      "type": 0
    }
  ],

  "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_type": "0=賽事, 1=發售日期, 2=其他相關活動"
}
```

#### /calendar/addArticle

request:

```json
{
  "*token": "string",
  "*title": "string",
  "*date": "string",
  "*url": "string",
  "*content": "string",
  "＊type": 0,

  "_comment_type": "0=賽事, 1=發售日期, 2=其他相關活動",
  "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_content": "副文本編輯產出的html字串"
}
```

response:

```json
{}
```

#### /calendar/editArticle

request:

```json
{
  "*token": "string",
  "id": 0,
  "*title": "string",
  "*date": "string",
  "*url": "string",
  "*content": "string",
  "＊type": 0,
  "*photo": "string",

  "_comment_type": "0=賽事, 1=發售日期, 2=其他相關活動",
  "_comment_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_content": "副文本編輯產出的html字串"
}
```

response:

```json
{}
```

### productionInformationType

#### /productionInformationType/list

request:

```json
{
  "*token": "string"
}
```

response:

```json
{
  "*list": [
    {
      "maintype": 0,
      "subtypeList": [
        {
          "productionInformation_subtype": "string"
        }
      ]
    }
  ]
}
```

### tag

#### /tag/articleList

request:

```json
{
  "*token": "string",
  "page": 0,
  "limit": 0,
  "*filter": {
    "tag": "string"
  }
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "tag": "string"
    }
  ]
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
  "id": 0,
  "*tag": "string"
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
  "page": 0,
  "limit": 0,
  "*filter": {
    "begin_date": 0,
    "end_date": 0
  }
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "title": "string",
      "subtitle": "string",
      "date": "string",
      "photo_pc": "string",
      "photo_mobile": "string",
      "url": "string"
    }
  ]
}
```

#### /banner/addArticle

request:

```json
{
  "*token": "string",
  "*title": "string",
  "*subtitle": "string",
  "*date": "string",
  "*photo_pc": "string",
  "*photo_mobile": "string",
  "*url": "string"
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
  "*token": "string",
  "*title": "string",
  "*subtitle": "string",
  "*date": "string",
  "*photo_pc": "string",
  "*photo_mobile": "string",
  "*url": "string"
}
```

response:

```json
{}
```

### Cards

#### /cards/cardsList

request:

```json
{
  "*token": "string",
  "page": 0,
  "limit": 0,
  "*filter": {
    "number": "string",
    "name": "string",
    "type": "string",
    "star": "string",
    "attribute": "string",
    "rarity": "string",
    "atk_t": 0,
    "atk_l": 0,
    "def_t": 0,
    "def_l": 0,
    "packType": "string",
    "id": 0
  },

  "_comment_number": "卡號",
  "_comment_name": "卡名",
  "_comment_type": "種類",
  "_comment_star": "星數",
  "_comment_attribute": "屬性",
  "_comment_rarity": "稀有度、版本",
  "_comment_packType": "包裝分類id",
  "_comment_id": "卡片密碼"
}
```

response:

```json
{
  "*total": 0,
  "*list": [
    {
      "number": "string",
      "name": "string",
      "type": "string",
      "star": "string",
      "attribute": "string",
      "rarity": [],
      "atk": 0,
      "def": 0,
      "packType": "string",
      "id": 0,
      "effect": "string",
      "photo": "string",
      "price_info": [
        {
          "time": "string",
          "price_lowest": 0,
          "price_avg": 0,
          "price_yuyu": 0,
          "rarity": "string"
        }
      ]
    }
  ],

  "_comment_effect": "卡片效果",
  "_comment_photo": "卡圖"
}
```

#### /cards/add

request:

```json
{
  "*token": "string",
  "number": "string",
  "name": "string",
  "type": "string",
  "star": "string",
  "attribute": "string",
  "rarity": [],
  "atk": 0,
  "def": 0,
  "packType": "string",
  "id": 0,
  "effect": "string",
  "photo": "string",
  "price_info":[]
}
```

response:

```json
{}
```

#### /cards/edit

request:

```json
{
  "*token": "string",
  "number": "string",
  "name": "string",
  "type": "string",
  "star": "string",
  "attribute": "string",
  "rarity": [],
  "atk": 0,
  "def": 0,
  "packType": "string",
  "id": 0,
  "effect": "string",
  "photo": "string",
  "time": "string",
  "price_info":[]
}
```

response:

```json
{}
```

### Battle Paper

#### /battlePaper/articleList

request:

```json
{
  "*token": "string",
  "page": 0,
  "limit": 0,
  "*filter": {
    "type": 0,
    "status": 0,
    "begin_date": "string",
    "end_date": "string"
  },

  "_comment_type": "0=週報"
}
```

response:

```json
{
  "*list": [
    {
      "id": 0,
      "type": 0,
      "title": "string",
      "publish_date": "string",
      "last_edit_date": "string",
      "photo": "string",
      "content": "string",
      "status": 0,
      "to_top": true,
      "*author_name": "string",
      "*author_id": 0,
      "*tag": []
    }
  ],

  "_comment_id": "自動生成的數字",
  "_comment_type": "0=週報",
  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_last_edit_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_photo": "btoa()編碼的Base64字串",
  "_comment_content": "副文本編輯產出的html字串",
  "_comment_status": "0=上架中, 1=下架中",
  "_comment_to_top": "true=置頂, false=非置頂"
}
```

#### /battlePaper/addArticle

request:

```json
{
  "*token": "string",
  "*type": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

  "_comment_type": "0=週報",
  "_comment_publish_date": "格式為YYYY-MM-DD HH:mm:ss",
  "_comment_photo": "btoa()編碼的Base64字串",
  "_comment_content": "副文本編輯產出的html字串"
}
```

response:

```json
{}
```

#### /battlePaper/editArticle

request:

```json
{
  "*token": "string",
  "*id": 0,
  "*type": 0,
  "*title": "string",
  "*publish_date": "string",
  "*photo": "string",
  "*content": "string",
  "*status": 0,
  "*to_top": true,
  "*author_name": "string",
  "*author_id": 0,
  "*tag": [],

  "_comment_type": "0=週報",
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

### Pack Type

#### /packType/packTypeList

request:

```json
{
  "*token": "string",
  "page": 0,
  "limit": 0,
  "*filter": {
    "status": 0
  },

  "_comment_status": "0=上架中, 1=下架中"
}
```

response:

```json
{
  "*total": 0,
  "*list": [
    {
      "id": 0,
      "packType": "string",
      "subtype": "string",
      "maintype": 0,
      "status": 0,
      "name": "string"
    }
  ],

  "_comment_packType": "產品代號",
  "_comment_maintype": "產品分類 0=補充包 1=Rush Duel 2=活動贈品 3=預組套牌",
  "_comment_subtype": "產品系列名稱(PP大會包...)",
  "_comment_status": "0=上架中, 1=下架中",
  "_comment_name": "產品名稱"
}
```

#### /packType/add

request:

```json
{
  "*token": "string",
  "*packType": "string",
  "*subtype": "string",
  "*maintype": 0,
  "*name": "string"
}
```

response:

```json
{}
```

#### /packType/edit

request:

```json
{
  "*token": "string",
  "*packType": "string",
  "*subtype": "string",
  "*maintype": 0,
  "*name": "string"
}
```

response:

```json
{}
```
