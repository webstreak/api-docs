---
title: API Reference

language_tabs:
  - cURL

includes:

search: true
---

# Introduction

Welcome to the Webstreak API! You can use our API to access inventory & campaign API endpoints.

<aside class="notice">
Webstreak API access is restricted to our partner companies.
</aside>

You can view code examples in the dark area to the right.

Production inventory API is available at `http://websites.webstreak.com/api/public` .
Production campaigns API is available at `https://campaigns.webstreak.com/api` .

# Authentication

> Example call to dealers endpoint with api key:

```shell
curl http://websites.webstreak.com/api/public/dealers?api_key=6b248ea92c8fa7cf7428cbae62e1ede1
```

Authentication is accomplished by providing your api key with each request. API access is limited to our partner companies.

Note: Access to campaign resources and inventory resources are managed separately.

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

# Campaigns

## Get Campaigns

This endpoint retrieves all digital campaigns attached to your API key.

```shell
curl https://campaigns.webstreak.com/api/campaigns
```

> The above command returns JSON structured like this:

```json
[
  {
    "id":17667,
    "white_label_id": "1234ABC",
    "start_date":"2014-09-04",
    "end_date":"2014-09-30",
    "budget":"3000.0",
    "name":"NewCar",
    "product_type": "Search",
    "utm_campaign_name": "UsedCar"
  },
  {
    "id":17668,
    "white_label_id": "1235ABC",
    "start_date":"2014-10-01",
    "end_date":"2014-10-30",
    "budget":"2000.0",
    "name":"UsedCar",
    "product_type": "Search",
    "utm_campaign_name": "UsedCar"
  }
]
```

### HTTP Request

`GET /campaigns?api_key=apikey`

Parameter | Description
--------- | -----------
start_date | lower bound of date range to query (YYYYMMDD)
end_date | upper bound of date range to query (YYYYMMDD)

# Campaign Results

## Get Campaign Results

This endpoint retrieves all digital campaigns attached to your API key.

```shell
curl https://campaigns.webstreak.com/api/campaigns/campaign_id/campaign_results
```

> The above command returns JSON structured like this:

```json
[
  {
    "impressions": 1406,
    "clicks": 1,
    "date": "2016-05-08"
  }
]
```

### HTTP Request

`GET /campaigns/campaign_id/campaign_results?api_key=apikey&start_date=20160501&end_date=20160530`

Parameter | Description
--------- | -----------
campaign_id | Required may either be a webstreak campaign id or a white label ID which you have provided
start_date | lower bound of date range to query (YYYYMMDD)
end_date | upper bound of date range to query (YYYYMMDD)
