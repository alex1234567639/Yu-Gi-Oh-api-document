### API Admin

| API                              | Action                                | Date       |
| -------------------------------- | ------------------------------------- | ---------- |
| /example/api                     | 新增範例api                                | 2021/07/03 |

***

# admin-server
* url: https://xxxxxxx.com.tw/api/[path]
* method: POST

| Path                                                 | Description              |
| ---------------------------------------------------- | ------------------------ |
| [/example/api](#exampleApi)                          | 範例api                   |

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