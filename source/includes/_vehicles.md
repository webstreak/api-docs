# Vehicles

## Get All Vehicles

This endpoint retrieves all vehicles.

<aside class="warning">
Requests for all vehicles with no query parameters may be extremely slow.
</aside>

```ruby

```

```shell

```

> The above command returns JSON structured like this:

```json

```

### HTTP Request

`GET http://api.webstreak.com/vehicles`

### URL Parameters

Parameter | Description
--------- | -----------
dealer_id | query vehicles for a specific dealer
vin | query by vin number
stock | query by stock number
updated_since | all vehicles updated/created after specified time

