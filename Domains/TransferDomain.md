**Transfer a Domain API**
The "Transfer a Domain" API enables you to transfer a domain from another registrar into your NameSilo account.

**Important Considerations**
- **Payment Method**: Payment can be made via a verified credit card or using NameSilo account funds.
- **Domain Requirements**: Ensure the domain is eligible for transfer from the current registrar.
- **Authorization Code**: A valid transfer authorization code is required.

*Note: A verified credit card or adequate account funds are required to utilize this API.*

**API Overview**
- **Endpoint: https://www.namesilo.com/api/transferDomain**
- **Method**: GET
- **Required Parameters**:
  - **domain**: The domain you want to transfer.
  - **auth**: Transfer authorization code (encoded with htmlencode() or base64).
- **Optional Parameters**:
  - **payment_id**: ID for the verified credit card to use. If not specified, account funds will be used.
  - **private**: "1" for private registration, "0" for public.
  - **auto_renew**: "1" for auto-renewal, "0" to disable.
  - **portfolio**: Encoded name of the portfolio to assign the domain upon transfer.
  - **coupon**: Coupon code for the order.
Contact Information Fields: If not using the default account contact profile, you can pass the following fields:
fn: First Name (32 characters max)
ln: Last Name (32 characters max)
ad: Mailing Address (128 characters max)
cy: Mailing City (64 characters max)
st: Mailing State/Province/Territory (64 characters max; use the correct [abbreviation](https://www.namesilo.com/popups/states.php) for US/CA)
zp: Mailing Zip/Postal Code (16 characters max)
ct: Mailing Country (4-character correct [abbreviation](https://www.namesilo.com/popups/countries.php))
em: Email Address (128 characters max)
ph: Phone Number (10 digits for US/CA; country dialing code not needed)
Optional Fields:
nn: Nickname (24 characters max)
cp: Company (64 characters max)
ad2: Mailing Address 2 (128 characters max)
fx: Fax (32 characters max; format as phone number)
.US Required Fields:
usnc: .US Nexus Category (must use correct [abbreviation](https://www.namesilo.com/popups/us_abbreviations.php))
usap: .US Application Purpose (must use correct [abbreviation](https://www.namesilo.com/popups/us_abbreviations.php))
.CA Domains:
Specify a contact ID with requisite .ca information, or use the default profile.If you do not pass a contact ID, you must have a "Default .ca Profile" in place to transfer .ca domains via the API. 
You can create your Default .ca Profile on the [Profile Manager](https://www.namesilo.com/account_profiles.php) page in your account.
.EU Domains:
Specify a contact ID with requisite .eu information.
Passing Contact ID:
contact_id: The contact profile ID to be assigned after the transfer.
