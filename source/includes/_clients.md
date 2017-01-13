# Clients

## Get Clients

This endpoint retrieves all digital campaign clients attached to your API key.

```shell
curl https://campaigns.webstreak.com/api/clients
```

> The above command returns JSON structured like this:

```json
[
 {
   "id": 1123,
   "name": "Car Dealer Name",
   "city":"Raleigh",
   "state":"NC",
   "street":"1 Fayetteville Rd.",
   "zip":"27510",
   "phone":"919-123-1212",
   "created_at":"2016-05-06T15:19:28.741-04:00",
   "site_url":"example.com"
 }
]
```

### HTTP Request

`GET /clients?api_key=apikey`
