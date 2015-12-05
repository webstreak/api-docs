# Dealers

## Get All Dealers

```shell
curl http://websites.webstreak.com/api/public/dealers
```

> The above command returns JSON structured like this:

```json
[{
"id": 15,
"name": "Acme Cars",
"street": "1151 West 104th St.",
"city": "Motor City",
"zip": "34114",
"state": "MO",
"latitude": 34.9389458,
"longitude": -94.6054878,
"phone_number": "(222)-333-4444"
}, 
{
"id": 16,
"name": "Acme Cars East",
"street": "1151 East 104th St.",
"city": "Motor City",
"zip": "34114",
"state": "MO",
"latitude": 34.9389458,
"longitude": -94.6054878,
"phone_number": "(222)-333-5555"
}]
```

This endpoint retrieves all dealers.

### HTTP Request

`GET http://websites.webstreak.com/api/public/dealers`


## Get a Specific Dealer

```shell
curl http://websites.webstreak.com/api/public/dealers/15
```

> The above command returns JSON structured like this:

```json
{
"id": 15,
"name": "Acme Cars",
"street": "1151 West 104th St.",
"city": "Motor City",
"zip": "34114",
"state": "MO",
"latitude": 34.9389458,
"longitude": -94.6054878,
"phone_number": "(222)-333-4444"
}
```

This endpoint retrieves a specific dealer.


### HTTP Request

`GET http://websites.webstreak.com/api/public/dealers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the dealer to retrieve