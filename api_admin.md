### API Admin

| API                              | Action                                | Date       |
| -------------------------------- | ------------------------------------- | ---------- |
| /admin/login                     | 新增登入api                             | 2021/07/03 |

***

# admin-server
* url: https://xxxxxxx.com.tw/api/[path]
* method: POST

| Path                                                 | Description              |
| ---------------------------------------------------- | ------------------------ |
| [/admin/login](#adminLogin)                          | 登入api                   |

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
| JSON decode failed        | 10003       |
| 請求參數不合法              | 10004       |

***

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
