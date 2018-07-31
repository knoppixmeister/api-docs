# Cancel an Order

Cancel a specific order.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/orders/1223181"

// timestamp is in milliseconds and the authorization header is "Bearer " + token
headers = {"X-BM-TIMESTAMP": xxx, "X-BM-AUTHORIZATION": "xxx"}

response = requests.delete(url, headers=headers)

print(response.text)
```

### Sample Response

```js
{}
```

#### Request Parameter

| Parameter | Type | Description |
| :--- | :--- | :--- |
| entrust_id | path | Order id |







