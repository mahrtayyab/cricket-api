# CRICKET API
## Description
This is a Free API for Cricket Fans around the Globe
## Authentication
**No Authentication Required for this API**
## Limits
**This API isn't limited in any term**
## Important Dictionary
#### Team Abbreviations
<details>
<pre>
<code>
    "ENG": England
    "IND": India
    "NZ": New Zealand
    "PAK": Pakistan
    "SA": South Africa
    "AUS": Australia
    "AFG": Afghanistan
    "SL": Sri Lanka
    "WI": West Indies
    "BAN": Bangladesh
    "ZIM": Zimbabwe
    "NEP": Nepal
    "IRE": Ireland
    "SCO": Scotland
    "UAE": UAE
    "PNG": Papua New Guinea
    "NED": Netherlands
    "OMA": Oman
    "NAM": Namibia
    "SIN": Singapore
    "QAT": Qatar
    "CAN": Canada
    "HK": Hong Kong
    "JSY": Jersey
    "KEN": Kenya
    "ITA": Italy
    "KUW": Kuwait
    "SDA": Saudi Arabia
    "DEN": Denmark
    "BRM": Bermuda
    "MAS": Malaysia
    "UGA": Uganda
    "GER": Germany
    "USA": United States
    "BOT": Botswana
    "NGR": Nigeria
    "GSY": Guernsey
    "NOR": Norway
    "AUT": Austria
    "ROM": Romania
    "ESP": Spain
    "BRN": Bahrain
    "BEL": Belgium
    "TAN": Tanzania
    "PHI": Philippines
    "MEX": Mexico
    "CAY": Cayman Islands
    "VAN": Vanuatu
    "BIZ": Belize
    "ARG": Argentina
    "PER": Peru
    "FIJ": Fiji
    "MAW": Malawi
    "PAN": Panama
    "SAM": Samoa
    "JPN": Japan
    "CRC": Costa Rica
    "MLT": Malta
    "LUX": Luxembourg
    "THA": Thailand
    "BUL": Bulgaria
    "POR": Portugal
    "CZE": Czech Republic
    "FIN": Finland
    "SK":  South Korea
    "MOZ": Mozambique
    "IOM": Isle of Man
    "GRE": Greece
    "BHU": Bhutan
    "MDV": Maldives
    "STH": Saint Helena
    "BRA": Brazil
    "CHI": Chile
    "GIB": Gibraltar
    "MYA": Myanmar
    "INA": Indonesia
    "LES": Lesotho
    "RWA": Rwanda
    "SWZ": Eswatini
    "TUR": Turkey
    "CHN": China
    "SER": Serbia
</code>
</pre>
</details>

#### Roles
<details>
<pre>
<code>
    "bowl" : Bowler
    "bat" : Batsmen
    "allround" : All-Rounder
</code>
</pre>
</details>

#### Match Formats
<details>
<pre>
<code>
    "test": Test
    "odi" : One Day Internationals
    "t20i" : Twenty 20 Internationals 
    "all" : All Three Formats
</code>
</pre>
</details>

## All Functions
* Get Team Overview
* Get All-Time Best Players
* Get all the Tournaments
* Get Player Rankings
* Get Team Rankings
### Coming Soon
- [X] Getting Fixtures
- [X] Getting Live Matches
- [X] Getting Results
- [X] Getting Live Match Updates
- [ ] Stats
## Using API
### Get Team Overview
#### Description:
Get Overview about a Team including its:
* 3 Next Fixtures
* 3 Previous Results
* Team Ranking in all Formats
#### Required Parameters
* name : str -> [Abbreviation of Team Name](#team-abbreviations)

#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/team?name=PAK
```
Replace name parameter with your desired team [abbreviation](#team-abbreviations)

### Output 
* Type -> JSON
* Structure
```json
{
  "fixtures": {
    "content": [
      {},
      {},
      {}
    ],
    "pageInfo": {}
  },
  "ranking": [
    {
      "t20i": {}
    },
    {
      "odi": {}
    },
    {
      "test": {}
    }
  ],
  "results": {
    "content": [
      {},
      {},
      {}
    ],
    "pageInfo": {}
  }
}

```

### Get All-Time Best
#### Description:
Get All-Times Best Player in the history of Cricket
#### Required Parameters
* role : str -> [Role of Player](#roles) in the Team
* format : str -> [Format of Match](#match-formats)

#### Optional Parameters
* page : int -> number of page being queried
* pageSize : int (max is 100) -> total number of result in a page


#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/beasts?role=bat&format=odi
```

### Output 
* Type -> JSON
* Structure
```json
{
  "content": [
    {},
    {}
  ],
  "pageInfo": {}
}
```

### Get All the Tournaments
#### Description:
Get All the Tournaments recognized by International Cricket Council (ICC)

#### Optional Parameters
* page : int -> number of page being queried
* pageSize : int (max is 100) -> total number of result in a page
* startDate : date (yyyy-mm-dd) -> startDate from which you want to get the Tournaments

#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/tournament
```

### Output 
* Type -> JSON
* Structure
```json
{
  "content": [
    {},
    {}
  ],
  "pageInfo": {}
}
```


### Get Players Ranking
#### Description:
Get Current Players Ranking

#### Required Parameters
* role : str -> [Role of Player](#roles) in the Team
* format : str -> [Format of Match](#match-formats)
#### Optional Parameters
* page : int -> number of page being queried
* pageSize : int (max is 100) -> total number of result in a page
* at : date (yyyy-mm-dd) -> ranking at the specific date

#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/player_ranking?role=bat&format=odi
```

### Output 
* Type -> JSON
* Structure
```json
{
  "content": [
    {"best":{
      "match": {
        "id":9303,
        "startDate":"2021-07-13",
        "teamA":{
          "abbreviation":"ENG",
          "fullName":"England",
          "id":1
        },
        "teamB":{
          "abbreviation":"PAK",
          "fullName":"Pakistan",
          "id":5
        },
        "venue":{
          "fullName":"Edgbaston, Birmingham",
          "id":1003,
          "shortName":"Edgbaston"}
      },
      "rating":873
    },
      "player":{
        "fullName":"Babar Azam",
        "id":7480,
        "nationality":"PAK",
        "rightArmedBowl":false,
        "rightHandedBat":false
      },
      "previousRanking":1,
      "rating":873
    },
    {},
    {}
  ],
  "metadata": {},
  "pageInfo": {}
}
```


### Get Team Ranking
#### Description:
Get Current Teams Ranking

#### Required Parameters
* format : str -> [Format of Match](#match-formats)

#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/team_ranking?format=test
```

### Output 
* Type -> JSON
* Structure
```json
[
  {
    "currentlyRanked":true,
    "date":"2021-09-20",
    "played":34,
    "points":8883,
    "position":3,
    "qfyMatches":46,
    "rating":261,
    "scope":"t20i",
    "team":{
      "abbreviation":"PAK",
      "altIds":{
        "pulse":"20"
      },
      "id":5,
      "name":"Pakistan"
    }
  },
  {}
]
```

### Get Fixtures
#### Description:
Get All Upcoming Matches Detail

#### Optional Parameters
* page : int -> number of page being queried
* pageSize : int (max is 100) -> total number of result in a page
* startDate : date (yyyy-mm-dd) -> startDate of the fixtures
* endDate : date (yyyy-mm-dd) -> endDate of the fixtures
* name : str -> [Abbreviation of Team Name](#team-abbreviations)

#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/fixtures
```
> **_NOTE:_** Please use proper Start Date and End Date for more accurate fixtures
### Output 
* Type -> JSON
* Structure
```json
{
  "content": [
    {},
    {}
  ],
  "pageInfo": {}
}
```

### Get Results
#### Description:
Get All the Results

#### Optional Parameters
* page : int -> number of page being queried
* pageSize : int (max is 100) -> total number of result in a page
* endDate : date (yyyy-mm-dd) -> endDate of the match
* name : str -> [Abbreviation of Team Name](#team-abbreviations)

#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/results
```
> **_NOTE:_** Please use proper Start Date for more accurate results
### Output 
* Type -> JSON
* Structure
```json
{
  "content": [
    {},
    {}
  ],
  "pageInfo": {}
}
```

### Get Lives
#### Description:
Get All the Live Matches

#### Optional Parameters
* page : int -> number of page being queried
* pageSize : int (max is 100) -> total number of result in a page
* startDate : date (yyyy-mm-dd) -> startDate of the match
* endDate : date (yyyy-mm-dd) -> endDate of the match

#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/live
```
> **_NOTE:_** Please use proper Start Date and End Date for more accurate results
### Output 
* Type -> JSON
* Structure
```json
{
  "content": [
    {},
    {}
  ],
  "pageInfo": {}
}
```

### Get Live Updates
#### Description:
Get Live Update for a specific already started match

#### Required Parameters
* matchId : int -> ID of the match which is live right now.
* commentary : boolean -> Get live commentary too 

#### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/live_update?matchId=4262&commentary=false
```
### Output 
* Type -> JSON
* Structure
```json
{
  "currentState": {},
  "innings": [],
  "matchId": {},
  "matchInfo": {}
}
```

# Updates
## Update 0.2:
* [Get all Fixtures](#get-fixtures)
* [Get all Results](#get-results)
* [Get all Live Matches](#get-lives)
* [Get all Live Matches Update](#get-live-updates)