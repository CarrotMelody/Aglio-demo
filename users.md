## 使用者資料 [/user/info/{id}]

### 查詢使用者資料 [GET]

可通過使用者 id 獲取使用者資料。

- Response 200 (application/json)
  ```json
  {
    "username": "admin",
    "roleName": "工程師",
    "role": 1
  }
  ```
- Response 403(application/json)
  ```json
  {
    "success": true,
    "message": "無權執行此操作"
  }
  ```
- Parameters
  - id: `1` (Integer, Required) - 使用者編號

### 新增使用者資料 [POST]

以 form-data 新增使用者資料。
::: note

- 圖片上傳 `<input type="file" name="img">`
  :::

- Request (multipart/form-data)
  ```
  account=admin&username=admin&password=admin&role=2
  ```
- Response 200 (application/json)
  ```json
  {
    "success": true,
    "message": "新增使用者資料成功"
  }
  ```
- Response 403(application/json)
  ```json
  {
    "success": false,
    "message": "無權執行此操作"
  }
  ```
- Response 409(application/json)
  ```json
  {
    "success": false,
    "message": "帳號已存在"
  }
  ```

### 修改使用者資料 [PATCH]

可通過使用者 id 修改使用者資料。

- Request (application/json)
  ```json
  {
    "username": "admin",
    "role": 2
  }
  ```
- Response 200 (application/json)
  ```json
  {
    "success": true,
    "message": "修改使用者資料成功!"
  }
  ```
- Response 403(application/json)
  ```json
  {
    "success": false,
    "message": "無權執行此操作"
  }
  ```
- Parameters
  - id: `1` (Integer, Required) - 使用者編號

### 刪除使用者資料 [DELETE]

可通過使用者 id 刪除使用者資料。

- Response 200 (application/json)
  ```json
  {
    "success": true,
    "message": "刪除使用者成功"
  }
  ```
- Response 403(application/json)
  ```json
  {
    "success": true,
    "message": "無權執行此操作"
  }
  ```
- Parameters
  - id: `1` (Integer, Required) - 使用者編號

## 登入與登出 [/user]

### 使用者登入 [POST /user/login]

- Request (application/json)
  ```json
  {
    "account": "admin",
    "password": "admin"
  }
  ```
- Response 200 (application/json)
  ```json
  {
    "success": true,
    "message": "登入成功"
  }
  ```

### 使用者登出 [POST /user/logout]

- Response 200 (application/json)
  ```json
  {
    "success": true,
    "message": "登出成功"
  }
  ```
