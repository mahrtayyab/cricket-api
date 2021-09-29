# CRICKET API
## Description
This is a Free API for Cricket Fans around the Globe
## Authentication
**No Authentication Required for this API**
## Limits
**This API isn't limited in any term**

## All Functions
* Get Team Overview
* Get All-Time Best Players
* Get all the Tournaments
* Get Player Rankings
* Get Team Rankings
### Coming Soon
- [ ] Getting Fixtures
- [ ] Getting Live Matches
- [ ] Getting Results
- [ ] Getting Live Match Updates

## Using API
### Get Team Overview
#### Description:
Get Overview about a Team including its:
* 3 Next Fixtures
* 3 Previous Results
* Team Ranking in all Formats
#### Required Parameters
* name : str -> Abbreviation of Team Name
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

### API Endpoint
```
https://factory-apis.herokuapp.com/api/cricket/team?name=PAK
```
Replace name parameter with your desired team [abbreviation](#team-abbreviations)

### Output 
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