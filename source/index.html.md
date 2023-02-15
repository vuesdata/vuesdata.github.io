---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# Introductions

Welcome to the VuesData API! You can use our API to access VuesData API endpoints, we provide different sets of APIs for Data Extraction from different set of websites and brands (Such as: SteamGames, US Stock Price, Indian Stock Price, BestBuy etc.) You can find different APIs here: .

We currently provide our services through RapidAPI only. You have to register an account on the <a href='https://rapidapi.com/auth/sign-up/'>RapidAPI Sign-Up</a> platform as developer or customer to start using our VuesData APIs. Please check the Quick Start guide on RapidAPI for signup and setting project: <a href='https://docs.rapidapi.com/docs/consumer-quick-start-guide'>RapidAPI Quick Start Guide</a>.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key from RapidAPI.

To authenticate, you have to use the RapidAPI API token/API. Once you subscribe to the plan of API trail/paid, RapidAPI provides you with a API Key/Token to access all the API on our platform. You can generate a API/token key for a new app from your Developer Control Panel of RapidAPI <a href='https://rapidapi.com/developer/'>https://rapidapi.com/developer/</a>.

RapidAPI expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# SteamGames Special Offers API

## Get All Games.

### /games_list/?start=0&count=10&region=US


```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all games that are on Special Offers here: <a href='https://store.steampowered.com/search/?specials=1'>https://store.steampowered.com/search/?specials=1</a>

### HTTP Request

`GET https://steamgames-special-offers.p.rapidapi.com/games_list/?start=0&count=10&region=US`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
start | 0 | Min Value should be 0 as it is starting of the list.
count | 10 | Max Value should not be more than 100 as it is max number of games you can retrieve at a time, limit set by Steam.
region | US | For now, we are only extracting the games list from US. However it does not affect the games that are on offer. It only affects the pricing conversion as per the country.


## Get a Specific Game Data.

### /games_data/?app_id=<app_id>

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific Game Data with Game Name, Price, Discount Percent and Discount Price.


### HTTP Request

`GET https://steamgames-special-offers.p.rapidapi.com/games_data/?app_id=1581770`

### URL Parameters

Parameter | Description
--------- | -----------
app_id | The app_id of the game that you have retrieved from the GamesList API above.
