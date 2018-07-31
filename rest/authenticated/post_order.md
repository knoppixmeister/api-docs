# Place a New Order

Create a new order.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/orders"

// timestamp is in milliseconds and the authorization header is "Bearer " + token
headers = {"X-BM-TIMESTAMP": xxx, "X-BM-AUTHORIZATION": "xxx", "Content-Type": "application/json"}

data = {"symbol": "BMX_ETH","amount": 1,"price" : 1,"side" : "buy"}

data = json.dumps(data)

response = requests.post(url, data=data, headers=headers)

print(response.text)
```

### Sample Request

```js
{
   "symbol":"BMX_ETH",
   "amount":1,
   "price":1,
   "side":"buy"
}
```

### Sample Response
```js
{
   "entrust_id":1223181
}
```

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| entrust_id | string | Order id |





