# Bearer Token

Get bearer token issued by the authorization server.

### Sample Request \(Python\)

```py
import time
import requests
import json

def get_access_token(apiKey, client_secret):
    url = "https://openapi.bitmart.com/v2/authentication"
    data = {"grant_type": "client_credentials","client_id": apiKey, "client_secret": client_secret}
    response = requests.post(url, data = data)
    print(response.content)
    accessToken = response.json()['access_token']
    return accessToken

if __name__ == '__main__':
    access_token = get_access_token(api_key, client_secret)
    print access_token

```


### Sample Response
```js
{
   "access_token":"m261aeb5bfa471c67c6ac41243959ae0dd408838cdc1a47e945305dd558e2fa78",
   "expires_in":900
}
```

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| access_token | string | Bearer token |
| expires_in | numeric | Token expiration time (in seconds) |





