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
