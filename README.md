
## StockApp
> This project focuses on building endpoints.

## Main features


- `/api/user/register`

    **Purpose:** Register user  
    **Method:** Post  
    **Request body:**  
    ```json
    {
      "username": "string123",
      "email": "user@example123.com",
      "password": "string",
      "phone": "+99718305820",
      "fullName": "string123",
      "country": "string"
    }

- `/api/user/login`

    **Purpose:** Login user  
    **Method:** Post  
    **Request body:**  
    ```json
    {
      "username": "string",
      "email": "user@example.com",
      "password": "string"
    }
    ```
  *You will receive a token called **your_access_token** after login successfully.*

- `/api/watchlist`

    **Authorization Header:**
    ~~~ 
    Type: Bearer Token
    Token: your_access_token
    ~~~

    **Purpose:** Users view their Watchlist  
    **Method:** Get  
    **Response body:**  
    ```json
    [
      {
        "watchId": 2,
        "userId": 1,
        "stockId": 10
      },
      {
        "watchId": 3,
        "userId": 1,
        "stockId": 11
      },
      {
        "watchId": 4,
        "userId": 1,
        "stockId": 12
      }
    ]
    ```
- `/api/watchlist/AddStockToWatchlist`

    **Authorization Header:**
    ~~~ 
    Type: Bearer Token
    Token: your_access_token
    ~~~

    **Purpose:** Add stock to Watchlist of User  
    **Method:** Post  
    **Request body:**  
    ```json
    {
      "stockId": 11
    }
    ```
- `/api/Order`  

    **Authorization Header:**
    ~~~ 
    Type: Bearer Token
    Token: your_access_token
    ~~~

    **Purpose:** History of User's ordering  
    **Method:** Get  
    **Response body:**  
    ```json
    {
      "orders": [
        {
          "stockId": 1,
          "orderType": "Buy",
          "direction": "String",
          "quantity": 50,
          "price": 500,
          "status": "String",
          "orderDate": "2024-01-09T11:47:02.567"
        },
        {
          "stockId": 2,
          "orderType": "Sell",
          "direction": "String",
          "quantity": 100,
          "price": 100,
          "status": "String",
          "orderDate": "2024-01-09T12:34:34.91"
        },
        {
          "stockId": 3,
          "orderType": "Buy",
          "direction": "String",
          "quantity": 500,
          "price": 50.0000,
          "status": "String",
          "orderDate": "2024-01-09T13:46:47.243"
        }
      ],
      "userId": 3
      }
    ```
- `/api/Order/place_order`  

    **Authorization Header:**
    ~~~ 
    Type: Bearer Token
    Token: your_access_token
    ~~~

    **Purpose:** Place a new order  
    **Method:** Post  
    **Request body:**  
    ```json
    {
      "userId": 1,
      "stockId": 3,
      "orderType": "buy",
      "direction": "string",
      "quantity": 100,
      "price": 100,
      "status": "string"
    }
    ```
- `/api/Stock/sectors`  

    **Purpose:** Return all sectors available  
    **Method:** Get  
    **Response body:**  
    ```json
    [
      "Bán lẻ",
      "Bất động sản",
      "Chứng khoán",
      "Cơ khí",
      "Công nghệ",
      "Hàng không",
      "Năng lượng",
      "Ngân hàng",
      "Quỹ đầu tư",
      "Thực phẩm"
    ]
    ```
