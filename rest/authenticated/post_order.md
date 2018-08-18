# Place a New Order

Create a new order.

### HMAC SHA256 signature

HMAC SHA256 signature will be used as the value of _**X-BM-SIGNATURE**_ header. We highly recommend to sign the payload in case the request body is hacked.

Here is a sample request using ```echo```, ```openssl``` and ```curl```.

| Key | Value |
| :--- | :--- |
| symbol | BMX_ETH |
| side | buy |
| amount | 1 |
| price | 1 |

```sh
echo -n "symbol=BMX_ETH&side=buy&amount=1&price=1" | openssl dgst -sha256 -hmac "8c08d9d5c3d15b105dbddaf96e427ac6"
(stdin)= 3277b4e642743e2218297397c94b80007575d521f92770e3795e38fd6fa71ef6
```

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/orders"

// timestamp is in milliseconds and the authorization header is "Bearer " + token
headers = {"X-BM-TIMESTAMP": xxx, "X-BM-AUTHORIZATION": "xxx", "X-BM-SIGNATURE": "3277b4e642743e2218297397c94b80007575d521f92770e3795e38fd6fa71ef6", "Content-Type": "application/json"}

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





