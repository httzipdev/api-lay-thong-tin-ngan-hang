# Api lấy thông tin Số tài khoản Ngân hàng
API hỗ trợ kiểm tra tên người dùng từ Số tài khoản Ngân hàng bao gồm:
 - Tên chủ tài khoản
----
[Xem Demo tại đây](https://banklookup.net)
### Hướng dẫn sử dụng
- Chọn Ngân hàng
- Nhập Số tài khoản cần kiểm tra
- Nhấn "Tìm"
### Lưu ý

Vì đây là bản thử nghiệm dùng rộng rãi nên sẽ giới hạn một số chức năng như 

- Giới hạn `5 lượt gọi / ngày`
- Tốc độ chậm

# API Document
##### URL
> ```javascript
>  https://api.banklookup.net
> ```
<details>
 
 <summary><code>POST</code> <code><b>/api/bank/id-lookup-prod</b></code></summary>

##### Header
> | Header      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | x-api-key      |  required | string   | Mã API |
> | x-api-secret      |  required | string   | Mã Secret API |

##### Body (Json)
> | Payload      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | bank      |  required | string   | Mã code ngân hàng: Xem các Bank hỗ trợ : https://api.banklookup.net/api/bank/list
> | account      |  required | string   | Số tài khoản cần kiểm tra|
##### Example Payload (json)
````json
{
    "bank":"<bank code>",
    "account":"<account number>"
}
````

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `json`        | Found                                                         |
> | `422`         | `json`        | Not found                                                          |
> | `429`         | `json`        | Too many requests

##### 200
````json
{
    "code": 200,
    "success": true,
    "status": true,
    "data": {
        "ownerName": "<Tên tài khoản>"
    },
    "msg": "Success"
}
````
</details>

