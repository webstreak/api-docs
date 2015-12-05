# Vehicles

## Get Vehicles

This endpoint retrieves all vehicles matching the specified query parameters.

<aside class="warning">
In order to limit the number of results returned, requests to the vehicles endpoint must always include a valid dealer.
</aside>

```shell
curl http://websites.webstreak.com/api/public/vehicles?dealer_id=15
```

> The above command returns JSON structured like this:

```json
[{
"dealer_id": 15,
"vin": "1FTFW1EV0AKA83079",
"stock_number": "53782-1",
"year": "2010",
"make": "F-150",
"sub_model": null,
"is_new": false,
"trim": "Lariat",
"trim_description": null,
"color_ext": "Tuxedo Black",
"color_int": "Other",
"engine": "5.4L 8 Cylinder",
"engine_displacement": null,
"fuel": "Flex Fuel",
"prices": {
"price_internet": "26988"
},
"updated_at": "2015-12-05 09:33:12 UTC",
"created_at": "2015-12-01 21:33:32 UTC",
"photos": [
"http://photos.ebizautos.com/5241/14450162/14450162_1.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_2.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_3.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_4.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_5.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_6.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_7.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_8.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_9.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_10.jpg",
"http://photos.ebizautos.com/5241/14450162/14450162_11.jpg"
],
"certification": "Manufacturer"
}]
```

### HTTP Request

`GET http://websites.webstreak.com/api/public/vehicles?dealer_id=<DEALER_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
dealer_id | query vehicles for a specific dealer
vin | query by vin number
stock_number | query by stock number
created_since | all vehicles created after specified time
updated_since | all vehicles updated after specified time

