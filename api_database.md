# Data Base Template

### 帳號 (admin)

```json
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
```

### 文章 - 系列介紹(series_introduction)

```json
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
```

### 文章 - 泛用卡介紹(useful_card_introduction)

```json
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
```

### 文章 - 上位卡表(meta_deck)

```json
{
  "id": 0,
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
```

### 文章 - 卡表資料(product_information))

```json
{
  "id": 0,
  "type": 0,
  "productionInformation_subtype": 0,
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
```

### 文章 - 規則相關(rules)

```json
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
```

### 文章 - 卡片故事(series_story)

```json
{
  "id": 0,
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
```

### 文章 - 戰報(battle_paper)

```json
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
```

### 卡片(cards)

```json
{
  "number": "string",
  "name": "string",
  "type": "string",
  "star": "string",
  "attribute": "string",
  "rarity": "string",
  "atk": 0,
  "def": 0,
  "packType": "string",
  "id": 0,
  "effect": "string",
  "photo": "string",
  "price_info": [
    {
      "time": "string",
      "price": 0
    }
  ]
}
```

### 牌組(decks)

```json
{
  "id": 0,
  "*author_name": "string",
  "*author_id": 0,
  "title": "string",
  "create_date": "string",
  "last_edit_date": "string",
  "main_deck": [
    {
      "number": "string",
      "name": "string",
      "type": "string",
      "star": "string",
      "attribute": "string",
      "rarity": "string",
      "atk": 0,
      "def": 0,
      "packType": "string",
      "id": 0,
      "effect": "string",
      "photo": "string",
      "price_info": [
        {
          "time": "string",
          "price": 0
        }
      ]
    }
  ],
  "extra_deck": [],
  "side_deck": []
}
```

### 行事曆(calendar)

```json
{
  "id": 0,
  "title": "string",
  "date": "string",
  "url": "string",
  "type": 0
}
```

### 卡包(packtype)

```json
{
  "packType": "string",
  "name": "string",
  "status": 0
}
```

### 橫幅(banner)

```json
{
  "id": 0,
  "title": "string",
  "subtitle": "string",
  "date": "string",
  "photo_pc": "string",
  "photo_mobile": "string",
  "url": "string"
}
```

### 產品類別表(product_information_subtype)

```json
{
  "id": 0,
  "productionInformation_subtype": "string",
  "maintype": 0
}
```

### 文章標籤(tag)

```json
{
  "id": 0,
  "tag": "string"
}
```
