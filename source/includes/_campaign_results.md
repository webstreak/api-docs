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
