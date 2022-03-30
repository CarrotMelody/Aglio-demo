## 報表資料 [/report]

### 取得報表 [GET /report/{id}]
- 可通過報表 id 獲取報表資料。
- **非工程師以上權限無法獲取報表資料**。
- 報表資料可能會有 `null`。

- Response 200 (application/json)
  ```json
  {
    "date": "2022-03-30 22:59:00",
    "status": 0,
    "price": 23891,
    "address": "奇幻山莊210巷",
    "employee": [1, 2, 3],
    "note": "閒人勿進"
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
  - id: `1` (Integer, Required) - 報表編號

### 新增報表 [POST]
- **非工程師以上權限無法新增報表資料**。
- 報表資料可以傳 `null`。

- Request (application/json)
  ```json
  {
    "date": "2022-03-30 22:59:00",
    "status": 0,
    "price": 23891,
    "address": "奇幻山莊210巷",
    "employee": [1, 2, 3],
    "note": "閒人勿進"
  }
  ```
- Response 200 (application/json)
  ```json
  {
    "success": true,
    "message": "新增報表成功"
  }
  ```
- Response 403(application/json)
  ```json
  {
    "success": true,
    "message": "無權執行此操作"
  }
  ```

### 修改報表 [PATCH /report/{id}]
- **非工程師以上權限無法修改報表資料**。
- 報表資料可以傳 `null`。

- Request (application/json)
  ```json
  {
    "date": "2022-03-30 22:59:00",
    "status": 0,
    "price": 23891,
    "address": "奇幻山莊210巷",
    "employee": [1, 2, 3],
    "note": "閒人勿進"
  }
  ```
- Response 200 (application/json)
  ```json
  {
    "success": true,
    "message": "修改報表成功"
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
  - id: `1` (Integer, Required) - 報表編號

### 刪除報表 [DELETE /report/{id}]
- **非系統管理權限無法刪除報表**。

- Response 200 (application/json)
  ```json
  {
    "success": true,
    "message": "刪除報表成功"
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
  - id: `1` (Integer, Required) - 報表編號
