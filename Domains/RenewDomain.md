
**Renew a Domain API**

The "Renew a Domain" API facilitates the renewal of a domain in your account for a specified number of years.

**Important Considerations**
- **Restoration Behavior**: If the domain is in the restoration period, renewDomain will perform a restoration. This behavior can be overridden in the API Manager page in your account.
- **Payment Method**: Payment can be made via a verified credit card or using NameSilo account funds.

*Note: A verified credit card or adequate account funds are required to utilize this API.*

**API Overview**
- **Endpoint**: https://www.namesilo.com/api/renewDomain
- **Method**: GET
- **Required Parameters**:
  - **domain**: Domain intended for renewal.
  - **years**: Duration of renewal (1-10 years).
- **Optional Parameters**:
  - **payment_id**: Verified credit card's ID for the transaction. If not specified, account funds will be used.
  - **coupon**: Coupon code for the order.

**Sample Request**

**bash**
```
https://www.namesilo.com/api/renewDomain?version=1&type=xml&key=your_api_key&domain=example.com&years=2
```

**php**
```
import requests

api_key = "your_api_key";
domain = "example.com";
years = 2;

// Construct the URL with required and optional parameters
url = f"https://www.namesilo.com/api/renewDomain?version=1&type=xml&key={api_key}&domain={domain}&years={years}";

// Make the GET request and print the response
response = requests.get(url);
print(response.text);
```

**python**
```
import requests

api_key = "your_api_key";
domain = "example.com";
years = 2;

// Construct the URL with required and optional parameters
url = f"https://www.namesilo.com/api/renewDomain?version=1&type=xml&key={api_key}&domain={domain}&years={years}";

// Make the GET request and print the response
response = requests.get(url);
print(response.text);
```

**Response Structure**

The API returns an XML response upon successful renewal:

```
<namesilo>
  <request>
    <operation>renewDomain</operation>
    <ip>55.555.55.55</ip>
  </request>
  <reply>
    <code>300</code>
    <detail>success</detail>
    <message>Your domain renewal was successfully processed.</message>
    <domain>example.com</domain>
    <order_amount>7.77</order_amount>
  </reply>
</namesilo>

```
