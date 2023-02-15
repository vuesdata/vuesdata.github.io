---
title: VuesData API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='https://rapidapi.com/developer/'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the VuesData API
---

# Introductions

Welcome to the VuesData API! You can use our API to access VuesData API endpoints, we provide different sets of APIs for Data Extraction from different set of websites and brands (Such as: SteamGames, US Stock Price, Indian Stock Price, BestBuy etc.) You can find different APIs here: .

We currently provide our services through RapidAPI only. You have to register an account on the <a href='https://rapidapi.com/auth/sign-up/'>RapidAPI Sign-Up</a> platform as developer or customer to start using our VuesData APIs. Please check the Quick Start guide on RapidAPI for signup and setting project: <a href='https://docs.rapidapi.com/docs/consumer-quick-start-guide'>RapidAPI Quick Start Guide</a>.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
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
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://steamgames-special-offers.p.rapidapi.com/games_list/?start=0&count=10&region=US")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["X-RapidAPI-Key"] = 'meowmeowmeow'
request["X-RapidAPI-Host"] = 'steamgames-special-offers.p.rapidapi.com'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://steamgames-special-offers.p.rapidapi.com/games_list/"

querystring = {"start":"0","count":"10","region":"US"}

headers = {
  "X-RapidAPI-Key": "meowmeowmeow",
  "X-RapidAPI-Host": "steamgames-special-offers.p.rapidapi.com"
}

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```

```shell
curl --request GET \
  --url 'https://steamgames-special-offers.p.rapidapi.com/games_list/?start=0&count=10&region=US' \
  --header 'X-RapidAPI-Host: steamgames-special-offers.p.rapidapi.com' \
  --header 'X-RapidAPI-Key: meowmeowmeow'
```

```javascript
import axios from "axios";

const options = {
  method: 'GET',
  url: 'https://steamgames-special-offers.p.rapidapi.com/games_list/',
  params: {start: '0', count: '10', region: 'US'},
  headers: {
    'X-RapidAPI-Key': 'meowmeowmeow',
    'X-RapidAPI-Host': 'steamgames-special-offers.p.rapidapi.com'
  }
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

> The above command returns JSON structured like this:

```json
{
  "games_list": [
    1351080,
    1203220,
    489830,
    924970,
    1894430,
    239140,
    1817070,
    976310,
    518790,
    1498570
  ],
  "possible_has_more": true,
  "total_games": 6294
}
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
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://steamgames-special-offers.p.rapidapi.com/games_data/?app_id=1581770")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["X-RapidAPI-Key"] = 'meowmeowmeow'
request["X-RapidAPI-Host"] = 'steamgames-special-offers.p.rapidapi.com'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://steamgames-special-offers.p.rapidapi.com/games_data/"

querystring = {"app_id":"1581770"}

headers = {
  "X-RapidAPI-Key": "meowmeowmeow",
  "X-RapidAPI-Host": "steamgames-special-offers.p.rapidapi.com"
}

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```

```shell
curl --request GET \
  --url 'https://steamgames-special-offers.p.rapidapi.com/games_data/?app_id=1581770' \
  --header 'X-RapidAPI-Host: steamgames-special-offers.p.rapidapi.com' \
  --header 'X-RapidAPI-Key: meowmeowmeow'
```

```javascript
import axios from "axios";

const options = {
  method: 'GET',
  url: 'https://steamgames-special-offers.p.rapidapi.com/games_data/',
  params: {app_id: '1581770'},
  headers: {
    'X-RapidAPI-Key': 'meowmeowmeow',
    'X-RapidAPI-Host': 'steamgames-special-offers.p.rapidapi.com'
  }
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

> The above command returns JSON structured like this:

```json
{
  "discount": "-80%",
  "original_price": "$49.99",
  "price": "$9.99",
  "title": "Mortal Kombat 11",
  "url": "https://store.steampowered.com/app/976310/"
}
```

This endpoint retrieves a specific Game Data with Game Name, Price, Discount Percent and Discount Price.


### HTTP Request

`GET https://steamgames-special-offers.p.rapidapi.com/games_data/?app_id=1581770`

### URL Parameters

Parameter | Description
--------- | -----------
app_id | The app_id of the game that you have retrieved from the GamesList API above.
