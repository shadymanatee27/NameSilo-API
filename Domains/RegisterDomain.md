Register a Domain API
The "Register a Domain" API allows users to register a new domain name for a specified duration with customizable attributes. This API is designed to facilitate seamless domain registration processes.

API Overview
- Endpoint: https://www.namesilo.com/api/registerDomain
- Method: GET
- Required Parameters:
  - domain: Domain you wish to register (e.g., example.com).
  - years: Number of years for registration (1-10).
- Optional Parameters:
  - payment_id: Verified credit card's ID for the transaction. If not specified, account funds will be used.
  - private: "1" for private registration (utilizing WHOIS privacy service), "0" for public. Defaults to public if not specified.
  - auto_renew: "1" to enable auto-renewal, "0" to disable. Defaults to auto-renewal if not specified.
  - portfolio: Encoded name of the portfolio to assign the domain upon registration. Created automatically if it doesn't exist.
  - ns1 to ns13: Up to 13 nameservers for the domain. Defaults to the registrar's nameservers if not provided or if any provided nameserver doesn't exist.
  - coupon: Coupon code for the order.
  - Contact Information Fields: For WHOIS (if not using default account contact profile):
    - fn: First Name (max 32 characters)
    - ln: Last Name (max 32 characters)
    - ad: Mailing Address (max 128 characters)
    - cy: City (max 64 characters)
    - st: State/Province/Territory (max 64 characters; use abbreviation for US/CA)
    - zp: Zip/Postal Code (max 16 characters)
    - ct: Country (4-character abbreviation)
    - em: Email Address (max 128 characters)
    - ph: Phone Number (10 digits for US/CA, country dialing code not needed)
    - Optional Fields:
     - nn: Nickname (max 24 characters)
     - cp: Company (max 64 characters)
     - ad2: Mailing Address 2 (max 128 characters)
     - fx: Fax (max 32 characters)
    - .US Required Fields:
     - usnc: .US Nexus Category (must use correct abbreviation)
     - usap: .US Application Purpose (must use correct abbreviation)
    - .CA Domains:
     - Specify a contact ID with requisite .ca information, or use the default .ca profile.
    - .EU Domains:
     - Specify a contact ID with requisite .eu information.
    - Passing Contact ID:
     - contact_id: The contact profile ID to assign to this domain.
     - 
Obtain the contact profile ID via the ContactList.md command.

Note: A verified credit card or adequate account funds are required to utilize this API.

PHP Example
```
<?php
$apiKey = "your_api_key";
$domain = "example.com";
$years = 2;
$private = 1;
$autoRenew = 1;

// Construct the URL with required and optional parameters
$url = "https://www.namesilo.com/api/registerDomain?version=1&type=xml&key=$apiKey&domain=$domain&years=$years&private=$private&auto_renew=$autoRenew";

// Make the GET request and output the response
$response = file_get_contents($url);
echo $response;
?>
```

Python Example
```
import requests

api_key = "your_api_key";
domain = "example.com";
years = 2;
private = 1;
auto_renew = 1;

// Construct the URL with required and optional parameters
url = f"https://www.namesilo.com/api/registerDomain?version=1&type=xml&key={api_key}&domain={domain}&years={years}&private={private}&auto_renew={auto_renew}";

// Make the GET request and print the response
response = requests.get(url);
print(response.text);
```

Response Structure
On successful registration, the API returns an XML response:
```
<namesilo>
  <request>
    <operation>registerDomain</operation>
    <ip>55.555.55.55</ip>
  </request>
```
