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

### 文章 - 戰報(battle_paper)

### 文章 - 泛用卡介紹(useful_card_introduction)

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
