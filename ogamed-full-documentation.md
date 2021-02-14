[`GET  /`](#details)  
[`GET  /bot/server`](#get-server)  
[`GET  /bot/server-data`](#get-server-data)  
[`POST /bot/set-user-agent`](#set-user-agent)  
[`GET  /bot/server-url`](#get-server-url)  
[`GET  /bot/language`](#get-language)  
`GET  /bot/empire/type/:typeID`  
[`POST /bot/page-content`](#get-page-content)  
[`GET  /bot/captcha`](#get-captcha)  
[`GET  /bot/captcha/icons/:challengeID`](#get-captcha-image)  
[`GET  /bot/captcha/question/:challengeID`](#get-captcha-text)  
[`POST /bot/captcha/solve`](#solve-captcha)  
[`GET  /bot/login`](#login)  
[`GET  /bot/logout`](#logout)  
[`GET  /bot/username`](#get-username)  
[`GET  /bot/universe-name`](#get-universe-name)  
[`GET  /bot/server/speed`](#get-universe-speed)  
[`GET  /bot/server/speed-fleet`](#get-universe-speed-fleet)  
[`GET  /bot/server/version`](#get-ogame-server-version)  
[`GET  /bot/server/time`](#get-ogame-server-time)  
[`GET  /bot/is-under-attack`](#is-under-attack)  
[`GET  /bot/is-vacation-mode`](#is-vacation-mode)  
[`GET  /bot/user-infos`](#get-user-infos)  
[`GET  /bot/character-class`](#get-character-class)  
[`POST /bot/send-message`](#send-message)  
[`GET  /bot/fleets`](#get-all-fleets)  
[`GET  /bot/fleets/slots`](#get-fleet-slots)  
[`POST /bot/planets/:planetID/send-fleet`](#send-a-fleet)  
[`POST /bot/fleets/:fleetID/cancel`](#cancel-a-fleet)  
[`GET  /bot/espionage-report`](#get-all-espionage-reports)  
[`GET  /bot/espionage-report/:messageID`](#get-espionage-report-by-message-id)  
[`GET  /bot/espionage-report/:galaxy/:system/:position`](#get-espionage-report-by-coordinates)  
[`POST /bot/delete-report/:messageID`](#delete-report-by-message-id)  
[`POST /bot/delete-all-espionage-reports`](#delete-all-espionage-reports)  
[`POST /bot/delete-all-reports/:tabIndex`](#delete-all-reports-by-tab)  
[`GET  /bot/attacks`](#get-attacks-infos)  
[`GET  /bot/get-auction`](#get-auction)  
[`POST /bot/do-auction`](#do-auction)  
[`GET  /bot/galaxy-infos/:galaxy/:system`](#get-galaxy-infos)  
[`GET  /bot/get-research`](#get-researches)  
`GET  /bot/buy-offer-of-the-day`  
[`GET  /bot/price/:ogameID/:nbr`](#get-price)  
[`GET  /bot/moons`](#get-moons)  
[`GET  /bot/moons/:moonID`](#get-moon-by-id)  
[`GET  /bot/moons/:galaxy/:system/:position`](#get-moon-with-coordinates)  
[`GET  /bot/celestials/:celestialID/items`](#get-items)  
[`GET  /bot/celestials/:celestialID/items/:itemRef/activate`](#use-item)  
[`GET  /bot/planets`](#get-bot-planets)  
[`GET  /bot/planets/:planetID`](#get-bot-planet-by-planet-id)  
[`GET  /bot/planets/:galaxy/:system/:position`](#get-bot-planet-with-coordinates)  
[`GET  /bot/planets/:planetID/resources-details`](#get-planet-resources-details)  
[`GET  /bot/planets/:planetID/resource-settings`](#get-planet-resource-settings)  
[`POST /bot/planets/:planetID/resource-settings`](#set-planet-resource-settings)  
[`GET  /bot/planets/:planetID/resources-buildings`](#get-planet-resources-buildings)  
[`GET  /bot/planets/:planetID/facilities`](#get-planet-facilities)  
[`GET  /bot/planets/:planetID/defence`](#get-planet-defences)  
[`GET  /bot/planets/:planetID/ships`](#get-planet-ships)  
[`POST /bot/planets/:planetID/build/:ogameID/:nbr`](#build)  
[`POST /bot/planets/:planetID/build/cancelable/:ogameID`](#build-cancelable)  
[`POST /bot/planets/:planetID/build/production/:ogameID/:nbr`](#build-military)  
[`POST /bot/planets/:planetID/build/building/:ogameID`](#build-construction)  
[`POST /bot/planets/:planetID/build/technology/:ogameID`](#build-technology)  
[`POST /bot/planets/:planetID/build/defence/:ogameID/:nbr`](#build-defences)  
[`POST /bot/planets/:planetID/build/ships/:ogameID/:nbr`](#build-ships)  
`POST /bot/planets/:planetID/teardown/:ogameID`  
[`GET  /bot/planets/:planetID/production`](#get-military-production)  
[`GET  /bot/planets/:planetID/constructions`](#get-current-constructions)  
[`POST /bot/planets/:planetID/cancel-building`](#cancel-construction)  
[`POST /bot/planets/:planetID/cancel-research`](#cancel-technology)  
[`GET  /bot/planets/:planetID/resources`](#get-planet-resources)  
[`POST /bot/planets/:planetID/send-ipm`](#send-missles)  
`GET  /bot/moons/:moonID/phalanx/:galaxy/:system/:position`  
[`GET  /bot/moons/:moonID/jump-gate`](#jump-gate)  
[`GET  /bot/celestials/:celestialID/techs`](#get-planet-info)  

Refer to [constants.go](https://github.com/alaingilbert/ogame/blob/master/constants.go) to figure out the IDs for `mission` / `speed` / `ships`...


### Get captcha

`GET  /bot/captcha`

```
curl 127.0.0.1:8080/bot/captcha
```

Result:
```html
<img style="background-color: black;" src="/bot/captcha/question/4572c357-f110-44cd-88f0-0bbe31adbd45" /><br />
<img style="background-color: black;" src="/bot/captcha/icons/4572c357-f110-44cd-88f0-0bbe31adbd45" /><br />
<form action="/bot/captcha/solve" method="POST">
	<input type="hidden" name="challenge_id" value="4572c357-f110-44cd-88f0-0bbe31adbd45" />
	Enter 0,1,2 or 3 and press Enter <input type="number" name="answer" />" +
</form>4572c357-f110-44cd-88f0-0bbe31adbd45
```

### Get captcha image

`GET  /bot/captcha/icons/:challengeID`

```
curl 127.0.0.1:8080/bot/captcha/icons/4572c357-f110-44cd-88f0-0bbe31adbd45
```

Result:
```
<captcha image>
```

### Get captcha text

`GET  /bot/captcha/question/:challengeID`

```
curl 127.0.0.1:8080/bot/captcha/question/4572c357-f110-44cd-88f0-0bbe31adbd45
```

Result:
```
<captcha question as image>
```

### Solve captcha

`POST /bot/captcha/solve`

```
curl 127.0.0.1:8080/bot/captcha/solve -d 'answer=1&challenge_id=4572c357-f110-44cd-88f0-0bbe31adbd45'
```

Result:
```
<empty>
```

### Get items

`GET  /bot/celestials/:celestialID/items`

```
curl 127.0.0.1:8080/bot/celestials/:celestialID/items
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":[
      {
         "Ref":"d9fa5f359e80ff4f4c97545d07c66dbadab1d1be",
         "Name":"Amplificador de deuterio (bronce)",
         "Image":"1467bd003a88e3b3c559a2cbebefd27651e9f7a4",
         "ImageLarge":"bdc8c4a25495b7c4381fb54063c9a9bd97ef6850",
         "Title":"Amplificador de deuterio (bronce)|10% más de producción de los sintetizadores de Deuterio en un planeta\u0026lt;br /\u0026gt;\u0026lt;br /\u0026gt;\nPlazo: 1s\u0026lt;br /\u0026gt;\u0026lt;br /\u0026gt;\nPrecio: 2.500 Materia Oscura\u0026lt;br /\u0026gt;\nEn el inventario: 0",
         "Rarity":"common",
         "Amount":0,
         "AmountFree":0,
         "AmountBought":0
      },
      {
         "Ref":"d3d541ecc23e4daa0c698e44c32f04afd2037d84",
         "Name":"DETROID (bronce)",
         "Image":"610b867a8841d4a4c949d8a59719243580456452",
         "ImageLarge":"56724c3a1dcae8036bb172f0be833a6f9a28bc27",
         "Title":"DETROID (bronce)|Reduce \u0026lt;b\u0026gt;30m\u0026lt;/b\u0026gt; el tiempo requerido por las órdenes de construcción actuales.\u0026lt;br /\u0026gt;\u0026lt;br /\u0026gt;\nPlazo: ahora\u0026lt;br /\u0026gt;\u0026lt;br /\u0026gt;\nPrecio: --- \u0026lt;br /\u0026gt;\nEn el inventario: 1",
         "Rarity":"common",
         "Amount":1,
         "AmountFree":0,
         "AmountBought":0
      },
      {
         "Ref":"3c9f85221807b8d593fa5276cdf7af9913c4a35d",
         "Name":"Amplificador de cristal (bronce)",
         "Image":"7c1dc1bf2d48d0f617e6f882a5df2ce8bfe7caef",
         "ImageLarge":"9f3d99c2f79ce94216497f3f08312a385ae5e952",
         "Title":"Amplificador de cristal (bronce)|10% más de producción en minas de cristal en un planeta\u0026lt;br /\u0026gt;\u0026lt;br /\u0026gt;\nPlazo: 1s\u0026lt;br /\u0026gt;\u0026lt;br /\u0026gt;\nPrecio: 2.500 Materia Oscura\u0026lt;br /\u0026gt;\nEn el inventario: 1",
         "Rarity":"common",
         "Amount":1,
         "AmountFree":0,
         "AmountBought":0
      
      }
   ]
}
```

### Use item

`GET  /bot/celestials/:celestialID/items/:itemRef/activate`

```
curl 127.0.0.1:8080/bot/celestials/:celestialID/items/:itemRef/activate
```

Result:
```
???
```

### Details

`GET /`

```
curl 127.0.0.1:8080/
```

Result:
```json
{"commit":"730cdab3bbfe8b29b70ced1bb4dcf8c7a65fb75f","date":"2020-01-14T08:37:07Z","version":"29.0.0"}
```

### Get server

`GET  /bot/server`

```
curl 127.0.0.1:8080/bot/server
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"Language": "en",
		"Number": 152,
		"Name": "Zibal",
		"PlayerCount": 1080,
		"PlayersOnline": 51,
		"Opened": "2018-03-22T12:18:23+0000",
		"StartDate": "2018-03-22T12:18:23+0000",
		"EndDate": null,
		"ServerClosed": 0,
		"Prefered": 1,
		"SignupClosed": 0,
		"Settings": {
			"AKS": 1,
			"FleetSpeed": 2,
			"WreckField": 1,
			"ServerLabel": "empty",
			"EconomySpeed": 7,
			"PlanetFields": 25,
			"UniverseSize": 6,
			"ServerCategory": "balanced",
			"EspionageProbeRaids": 0,
			"PremiumValidationGift": 25000,
			"DebrisFieldFactorShips": 70,
			"DebrisFieldFactorDefence": 0
		}
	}
}
```

### Get server data

`GET  /bot/server-data`

```
curl 127.0.0.1:8080/bot/server-data
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "Name":"Rhea",
      "Number":144,
      "Language":"pt",
      "Timezone":"Europe/Lisbon",
      "TimezoneOffset":"+00:00",
      "Domain":"s144-pt.ogame.gameforge.com",
      "Version":"7.6.5",
      "Speed":10,
      "SpeedFleet":3,
      "Galaxies":5,
      "Systems":499,
      "ACS":false,
      "RapidFire":true,
      "DefToTF":false,
      "DebrisFactor":0.5,
      "DebrisFactorDef":0,
      "RepairFactor":0.7,
      "NewbieProtectionLimit":500000,
      "NewbieProtectionHigh":50000,
      "TopScore":141715314,
      "BonusFields":25,
      "DonutGalaxy":true,
      "DonutSystem":true,
      "WfEnabled":true,
      "WfMinimumRessLost":150000,
      "WfMinimumLossPercentage":5,
      "WfBasicPercentageRepairable":45,
      "GlobalDeuteriumSaveFactor":0.5,
      "Bashlimit":0,
      "ProbeCargo":0,
      "ResearchDurationDivisor":2,
      "DarkMatterNewAcount":8000,
      "CargoHyperspaceTechMultiplier":5
   }
}
```

### Set user-agent

`POST /bot/set-user-agent`

```
curl 127.0.0.1:8080/bot/set-user-agent -d 'userAgent="new user agent"'
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get server URL

`GET /bot/server-url`

```
curl 127.0.0.1:8080/bot/server-url
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":"https://s152-en.ogame.gameforge.com"}
```

### Get language

`GET /bot/language`

```
curl 127.0.0.1:8080/bot/language
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":"en"}
```

### Get page content

`POST /bot/page-content`

```
curl -XPOST 127.0.0.1:8080/bot/page-content
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":"<base64 encoded HTML>"}
```

### Login

`GET /bot/login`

```
curl 127.0.0.1:8080/bot/login
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Logout

`GET /bot/logout`

```
curl 127.0.0.1:8080/bot/logout
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get username

`GET /bot/username`

```
curl 127.0.0.1:8080/bot/username
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":"your@email.com"}
```

### Get universe name

`GET /bot/universe-name`

```
curl 127.0.0.1:8080/bot/universe-name
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":"Norma"}
```

### Get universe speed

`GET /bot/server/speed`

```
curl 127.0.0.1:8080/bot/server/speed
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":7}
```

### Get universe speed fleet

`GET /bot/server/speed-fleet`

```
curl 127.0.0.1:8080/bot/server/speed-fleet
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":2}
```

### Get ogame server version

`GET /bot/server/version`

```
curl 127.0.0.1:8080/bot/server/version
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":"6.7.2-pl4"}
```

### Get ogame server time

`GET /bot/server/time`

```
curl 127.0.0.1:8080/bot/server/time
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":"2018-09-12T21:33:57+01:00"}
```

### Is under attack

`GET /bot/is-under-attack`

```
curl 127.0.0.1:8080/bot/is-under-attack
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":false}
```

### Is vacation mode

`GET  /bot/is-vacation-mode`

```
curl 127.0.0.1:8080/bot/is-vacation-mode
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":false
}
```

### Get user infos

`GET /bot/user-infos`

```
curl 127.0.0.1:8080/bot/user-infos
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"PlayerID": 107009,
		"PlayerName": "Constable Telesto",
		"Points": 33439,
		"Rank": 825,
		"Total": 1050,
		"HonourPoints": 0
	}
}
```

### Get character class

`GET  /bot/character-class`

```
curl 127.0.0.1:8080/bot/character-class
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":1
}
```

### Send message

`POST /bot/send-message`

```
curl 127.0.0.1:8080/bot/send-message -d 'playerID=123&message="How are you ?"'
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get all fleets

`GET /bot/fleets`

```
curl 127.0.0.1:8080/bot/fleets
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":[
      {
         "Mission":6,
         "ReturnFlight":false,
         "ID":1521262,
         "Resources":{
            "Metal":0,
            "Crystal":0,
            "Deuterium":0,
            "Energy":0,
            "Darkmatter":0
         },
         "Origin":{
            "Galaxy":2,
            "System":326,
            "Position":12,
            "Type":1
         },
         "Destination":{
            "Galaxy":2,
            "System":351,
            "Position":8,
            "Type":1
         },
         "Ships":{
            "LightFighter":0,
            "HeavyFighter":0,
            "Cruiser":0,
            "Battleship":0,
            "Battlecruiser":0,
            "Bomber":0,
            "Destroyer":0,
            "Deathstar":0,
            "SmallCargo":0,
            "LargeCargo":0,
            "ColonyShip":0,
            "Recycler":0,
            "EspionageProbe":1,
            "SolarSatellite":0,
            "Crawler":0,
            "Reaper":0,
            "Pathfinder":0
         },
         "ArrivalTime":"2020-02-12T23:44:19Z",
         "BackTime":"2020-02-12T23:56:01Z",
         "ArriveIn":623,
         "BackIn":1325,
         "UnionID":0,
         "TargetPlanetID":0
      },
      {
         "Mission":1,
         "ReturnFlight":false,
         "ID":1521273,
         "Resources":{
            "Metal":0,
            "Crystal":0,
            "Deuterium":0,
            "Energy":0,
            "Darkmatter":0
         },
         "Origin":{
            "Galaxy":2,
            "System":326,
            "Position":12,
            "Type":1
         },
         "Destination":{
            "Galaxy":2,
            "System":351,
            "Position":8,
            "Type":1
         },
         "Ships":{
            "LightFighter":1,
            "HeavyFighter":0,
            "Cruiser":0,
            "Battleship":0,
            "Battlecruiser":0,
            "Bomber":0,
            "Destroyer":0,
            "Deathstar":0,
            "SmallCargo":0,
            "LargeCargo":0,
            "ColonyShip":0,
            "Recycler":0,
            "EspionageProbe":0,
            "SolarSatellite":0,
            "Crawler":0,
            "Reaper":0,
            "Pathfinder":0
         },
         "ArrivalTime":"2020-02-13T16:44:01Z",
         "BackTime":"2020-02-14T09:55:04Z",
         "ArriveIn":61805,
         "BackIn":123668,
         "UnionID":0,
         "TargetPlanetID":33636849
      },
      {
         "Mission":3,
         "ReturnFlight":false,
         "ID":1521284,
         "Resources":{
            "Metal":25,
            "Crystal":15,
            "Deuterium":10,
            "Energy":0,
            "Darkmatter":0
         },
         "Origin":{
            "Galaxy":2,
            "System":326,
            "Position":12,
            "Type":1
         },
         "Destination":{
            "Galaxy":2,
            "System":351,
            "Position":8,
            "Type":1
         },
         "Ships":{
            "LightFighter":1,
            "HeavyFighter":0,
            "Cruiser":0,
            "Battleship":0,
            "Battlecruiser":0,
            "Bomber":0,
            "Destroyer":0,
            "Deathstar":0,
            "SmallCargo":0,
            "LargeCargo":0,
            "ColonyShip":0,
            "Recycler":0,
            "EspionageProbe":0,
            "SolarSatellite":0,
            "Crawler":0,
            "Reaper":0,
            "Pathfinder":0
         },
         "ArrivalTime":"2020-02-13T16:44:24Z",
         "BackTime":"2020-02-14T09:55:27Z",
         "ArriveIn":61828,
         "BackIn":123691,
         "UnionID":0,
         "TargetPlanetID":0
      }
   ]
}
```

### Get fleet slots

`GET /bot/fleets/slots`

```
curl 127.0.0.1:8080/bot/fleets/slots
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":{"InUse":0,"Total":1,"ExpInUse":0,"ExpTotal":1}}
```

### Send a fleet

`POST /bot/planets/:planetID/send-fleet`

```
curl 127.0.0.1:8080/bot/planets/123/send-fleet -d 'ships=204,1&ships=205,2&speed=10&galaxy=4&system=208&position=8&type=1&mission=3&metal=1&crystal=2&deuterium=3'
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "Mission":1,
      "ReturnFlight":false,
      "ID":73188,
      "Resources":{
         "Metal":0,
         "Crystal":0,
         "Deuterium":0,
         "Energy":0,
         "Darkmatter":0
      },
      "Origin":{
         "Galaxy":1,
         "System":20,
         "Position":8,
         "Type":1
      },
      "Destination":{
         "Galaxy":1,
         "System":19,
         "Position":12,
         "Type":1
      },
      "Ships":{
         "LightFighter":0,
         "HeavyFighter":0,
         "Cruiser":5,
         "Battleship":0,
         "Battlecruiser":0,
         "Bomber":0,
         "Destroyer":0,
         "Deathstar":0,
         "SmallCargo":50,
         "LargeCargo":0,
         "ColonyShip":0,
         "Recycler":0,
         "EspionageProbe":0,
         "SolarSatellite":0,
         "Crawler":0,
         "Reaper":0,
         "Pathfinder":0
      },
      "ArrivalTime":"2020-02-13T11:33:09Z",
      "BackTime":"2020-02-13T13:34:17Z",
      "ArriveIn":7268,
      "BackIn":14536,
      "UnionID":0,
      "TargetPlanetID":33620279
   }
}
```

### Cancel a fleet

`POST /bot/fleets/:fleetID/cancel`

```
curl -XPOST 127.0.0.1:8080/bot/fleets/5575790/cancel
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get all espionage reports

`GET /bot/espionage-report`

```
curl 127.0.0.1:8080/bot/espionage-report
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":[
      {
         "ID":3784280,
         "Type":1,
         "From":"Comando della Flotta",
         "Target":{
            "Galaxy":2,
            "System":320,
            "Position":11,
            "Type":1
         },
         "LootPercentage":0.75
      }
   ]
}
```

### Get espionage report by message ID

`GET /bot/espionage-report/:messageID`

```
curl 127.0.0.1:8080/bot/espionage-report/3784280
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "Metal":366050,
      "Crystal":131085,
      "Deuterium":55303,
      "Energy":0,
      "Darkmatter":0,
      "ID":3784280,
      "Username":"Zuu",
      "LastActivity":24,
      "CounterEspionage":0,
      "APIKey":"sr-it-162-935e81ac8d98edc858c724c79f9d47a4667a7b49",
      "HasFleet":true,
      "HasDefenses":true,
      "HasBuildings":true,
      "HasResearches":true,
      "IsBandit":false,
      "IsStarlord":true,
      "IsInactive":true,
      "IsLongInactive":false,
      "MetalMine":21,
      "CrystalMine":17,
      "DeuteriumSynthesizer":15,
      "SolarPlant":20,
      "FusionReactor":7,
      "SolarSatellite":null,
      "MetalStorage":9,
      "CrystalStorage":7,
      "DeuteriumTank":6,
      "RoboticsFactory":2,
      "Shipyard":8,
      "ResearchLab":5,
      "AllianceDepot":1,
      "MissileSilo":4,
      "NaniteFactory":null,
      "Terraformer":null,
      "SpaceDock":3,
      "LunarBase":null,
      "SensorPhalanx":null,
      "JumpGate":null,
      "EnergyTechnology":8,
      "LaserTechnology":12,
      "IonTechnology":5,
      "HyperspaceTechnology":8,
      "PlasmaTechnology":8,
      "CombustionDrive":8,
      "ImpulseDrive":8,
      "HyperspaceDrive":7,
      "EspionageTechnology":11,
      "ComputerTechnology":10,
      "Astrophysics":7,
      "IntergalacticResearchNetwork":1,
      "GravitonTechnology":null,
      "WeaponsTechnology":12,
      "ShieldingTechnology":11,
      "ArmourTechnology":11,
      "RocketLauncher":null,
      "LightLaser":null,
      "HeavyLaser":null,
      "GaussCannon":null,
      "IonCannon":null,
      "PlasmaTurret":null,
      "SmallShieldDome":null,
      "LargeShieldDome":null,
      "AntiBallisticMissiles":null,
      "InterplanetaryMissiles":19,
      "LightFighter":null,
      "HeavyFighter":null,
      "Cruiser":null,
      "Battleship":null,
      "Battlecruiser":null,
      "Bomber":null,
      "Destroyer":null,
      "Deathstar":null,
      "SmallCargo":null,
      "LargeCargo":null,
      "ColonyShip":null,
      "Recycler":null,
      "EspionageProbe":null,
      "Crawler":null,
      "Reaper":null,
      "Pathfinder":null,
      "Coordinate":{
         "Galaxy":2,
         "System":320,
         "Position":11,
         "Type":1
      },
      "Type":1,
      "Date":"2020-01-15T20:34:20Z"
   }
}
```

### Get espionage report by coordinates

`GET /bot/espionage-report/:galaxy/:system/:position`

```
curl 127.0.0.1:8080/bot/espionage-report/2/320/11
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "Metal":366050,
      "Crystal":131085,
      "Deuterium":55303,
      "Energy":0,
      "Darkmatter":0,
      "ID":3784280,
      "Username":"Zuu",
      "LastActivity":24,
      "CounterEspionage":0,
      "APIKey":"sr-it-162-935e81ac8d98edc858c724c79f9d47a4667a7b49",
      "HasFleet":true,
      "HasDefenses":true,
      "HasBuildings":true,
      "HasResearches":true,
      "IsBandit":false,
      "IsStarlord":true,
      "IsInactive":true,
      "IsLongInactive":false,
      "MetalMine":21,
      "CrystalMine":17,
      "DeuteriumSynthesizer":15,
      "SolarPlant":20,
      "FusionReactor":7,
      "SolarSatellite":null,
      "MetalStorage":9,
      "CrystalStorage":7,
      "DeuteriumTank":6,
      "RoboticsFactory":2,
      "Shipyard":8,
      "ResearchLab":5,
      "AllianceDepot":1,
      "MissileSilo":4,
      "NaniteFactory":null,
      "Terraformer":null,
      "SpaceDock":3,
      "LunarBase":null,
      "SensorPhalanx":null,
      "JumpGate":null,
      "EnergyTechnology":8,
      "LaserTechnology":12,
      "IonTechnology":5,
      "HyperspaceTechnology":8,
      "PlasmaTechnology":8,
      "CombustionDrive":8,
      "ImpulseDrive":8,
      "HyperspaceDrive":7,
      "EspionageTechnology":11,
      "ComputerTechnology":10,
      "Astrophysics":7,
      "IntergalacticResearchNetwork":1,
      "GravitonTechnology":null,
      "WeaponsTechnology":12,
      "ShieldingTechnology":11,
      "ArmourTechnology":11,
      "RocketLauncher":null,
      "LightLaser":null,
      "HeavyLaser":null,
      "GaussCannon":null,
      "IonCannon":null,
      "PlasmaTurret":null,
      "SmallShieldDome":null,
      "LargeShieldDome":null,
      "AntiBallisticMissiles":null,
      "InterplanetaryMissiles":19,
      "LightFighter":null,
      "HeavyFighter":null,
      "Cruiser":null,
      "Battleship":null,
      "Battlecruiser":null,
      "Bomber":null,
      "Destroyer":null,
      "Deathstar":null,
      "SmallCargo":null,
      "LargeCargo":null,
      "ColonyShip":null,
      "Recycler":null,
      "EspionageProbe":null,
      "Crawler":null,
      "Reaper":null,
      "Pathfinder":null,
      "Coordinate":{
         "Galaxy":2,
         "System":320,
         "Position":11,
         "Type":1
      },
      "Type":1,
      "Date":"2020-01-15T20:34:20Z"
   }
}
```

### Delete report by message ID

`POST /bot/delete-report/:messageID`

```
curl -XPOST 127.0.0.1:8080/bot/delete-report/3784280
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Delete all espionage reports

`POST /bot/delete-all-espionage-reports`

```
curl -XPOST 127.0.0.1:8080/bot/delete-all-espionage-reports
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Delete all reports by tab

`POST /bot/delete-all-reports/:tabIndex`

Tab index must be one of the following:
- 20 => Espionage
- 21 => Combat Reports
- 22 => Expeditions
- 23 => Unions/Transport
- 24 => Other

```
curl -XPOST 127.0.0.1:8080/bot/delete-all-reports/20
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get attacks infos

```
curl 127.0.0.1:8080/bot/attacks
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":[
      {
         "ID":3405759,
         "MissionType":1,
         "Origin":{
            "Galaxy":2,
            "System":351,
            "Position":8,
            "Type":1
         },
         "Destination":{
            "Galaxy":2,
            "System":326,
            "Position":12,
            "Type":1
         },
         "DestinationName":"Planeta Principal",
         "ArrivalTime":"2020-01-15T22:39:26Z",
         "ArriveIn":691,
         "AttackerName":"Lord Rocket",
         "AttackerID":104099,
         "UnionID":0,
         "Missiles":0,
         "Ships":{
            "LightFighter":10,
            "HeavyFighter":0,
            "Cruiser":0,
            "Battleship":0,
            "Battlecruiser":0,
            "Bomber":0,
            "Destroyer":0,
            "Deathstar":0,
            "SmallCargo":0,
            "LargeCargo":0,
            "ColonyShip":0,
            "Recycler":0,
            "EspionageProbe":0,
            "SolarSatellite":0,
            "Crawler":0,
            "Reaper":0,
            "Pathfinder":0              
         }
      },
      {
         "ID":3406759,
         "MissionType":6,
         "Origin":{
            "Galaxy":2,
            "System":351,
            "Position":8,
            "Type":1
         },
         "Destination":{
            "Galaxy":2,
            "System":326,
            "Position":12,
            "Type":1
         },
         "DestinationName":"Planeta Principal",
         "ArrivalTime":"2020-02-12T23:51:25Z",
         "ArriveIn":692,
         "AttackerName":"Lord Rocket",
         "AttackerID":104099,
         "UnionID":0,
         "Missiles":0,
         "Ships":{
            "LightFighter":0,
            "HeavyFighter":0,
            "Cruiser":0,
            "Battleship":0,
            "Battlecruiser":0,
            "Bomber":0,
            "Destroyer":0,
            "Deathstar":0,
            "SmallCargo":0,
            "LargeCargo":0,
            "ColonyShip":0,
            "Recycler":0,
            "EspionageProbe":10,
            "SolarSatellite":0,
            "Crawler":0,
            "Reaper":0,
            "Pathfinder":0              
         }
      }
   ]
}
```

### Get auction

`GET  /bot/get-auction`

```
curl 127.0.0.1:8080/bot/get-auction
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "HasFinished":false,
      "Endtime":1500,
      "NumBids":0,
      "CurrentBid":0,
      "AlreadyBid":0,
      "MinimumBid":1000,
      "DeficitBid":0,
      "HighestBidder":"",
      "HighestBidderUserID":0,
      "CurrentItem":"reforço de cristal bronze",
      "CurrentItemLong":"reforço de cristal bronze|+10% mais produção de cristal num planeta\u003cbr /\u003e\u003cbr /\u003e\nduração: 1s\u003cbr /\u003e\u003cbr /\u003e\npreço: --- \u003cbr /\u003e\nno inventário: 1",
      "Inventory":1,
      "Token":"4fc8697d2d784274d5bb3bd22d6449c3",
      "ResourceMultiplier":{
         "Metal":1,
         "Crystal":1.5,
         "Deuterium":3,
         "Honor":100
      },
      "Resources":{
         "33662578":{
            "imageFileName":"normal_8",
            "input":{
               "crystal":1590000,
               "deuterium":473432,
               "metal":2920000
            },
            "isMoon":false,
            "name":"Planeta Principal",
            "otherPlanetId":null,
            "output":{
               "crystal":0,
               "deuterium":0,
               "metal":0
            }
         },
         "33665192":{
            "imageFileName":"jungle_1",
            "input":{
               "crystal":470000,
               "deuterium":254999,
               "metal":1590000
            },
            "isMoon":false,
            "name":"Colonia",
            "otherPlanetId":null,
            "output":{
               "crystal":0,
               "deuterium":0,
               "metal":0
            }
         },
         "33665346":{
            "imageFileName":"jungle_5",
            "input":{
               "crystal":470000,
               "deuterium":255000,
               "metal":1590000
            },
            "isMoon":false,
            "name":"Colonia",
            "otherPlanetId":null,
            "output":{
               "crystal":0,
               "deuterium":0,
               "metal":0
            }
         }
      }
   }
}
```

### Do auction

`POST /bot/do-auction`

```
curl 127.0.0.1:8080/bot/do-auction -d '33662578=1000:0:0'
```

Request body format: `celestialID=metal:crystal:deuterium`

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":null
}
```

### Get galaxy infos

`GET  /bot/galaxy-infos/:galaxy/:system`

```
curl 127.0.0.1:8080/bot/galaxy-infos/4/205
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "Galaxy":1,
      "System":350,
      "Planets":[
         null,
         null,
         null,
         {
            "ID":33622547,
            "Activity":47,
            "Name":"Tatooine",
            "Img":"https://gf2.geo.gfsrv.net/cdndf/3e567d6f16d040326c7a0ea29a4f41.gif",
            "Coordinate":{
               "Galaxy":1,
               "System":350,
               "Position":4,
               "Type":1
            },
            "Administrator":false,
            "Inactive":false,
            "Vacation":false,
            "StrongPlayer":true,
            "Newbie":false,
            "HonorableTarget":true,
            "Banned":false,
            "Debris":{
               "Metal":0,
               "Crystal":0,
               "RecyclersNeeded":0
            },
            "Moon":null,
            "Player":{
               "ID":101755,
               "Name":"Anzuniu",
               "Rank":764,
               "IsBandit":false,
               "IsStarlord":false
            },
            "Alliance":{
               "ID":500025,
               "Name":"Aceptados",
               "Rank":6,
               "Member":48
            }
         },
         null,
         {
            "ID":33622548,
            "Activity":24,
            "Name":"Planeta Principal",
            "Img":"https://gf2.geo.gfsrv.net/cdndf/3e567d6f16d040326c7a0ea29a4f41.gif",
            "Coordinate":{
               "Galaxy":1,
               "System":350,
               "Position":6,
               "Type":1
            },
            "Administrator":false,
            "Inactive":false,
            "Vacation":false,
            "StrongPlayer":true,
            "Newbie":false,
            "HonorableTarget":true,
            "Banned":false,
            "Debris":{
               "Metal":0,
               "Crystal":0,
               "RecyclersNeeded":0
            },
            "Moon":{
               "ID":33643508,
               "Diameter":8717,
               "Activity":0
            },
            "Player":{
               "ID":101756,
               "Name":"NAVAYU",
               "Rank":366,
               "IsBandit":false,
               "IsStarlord":true
            },
            "Alliance":null
         },
         null,
         null,
         null,
         null,
         null,
         null,
         null,
         null,
         null
      ],
      "ExpeditionDebris":{
         "Metal":0,
         "Crystal":0,
         "PathfindersNeeded":0
      }
   }
}
```

### Get researches

`GET /bot/get-research`

```
curl 127.0.0.1:8080/bot/get-research
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"EnergyTechnology": 4,
		"LaserTechnology": 2,
		"IonTechnology": 0,
		"HyperspaceTechnology": 0,
		"PlasmaTechnology": 0,
		"CombustionDrive": 6,
		"ImpulseDrive": 4,
		"HyperspaceDrive": 0,
		"EspionageTechnology": 7,
		"ComputerTechnology": 8,
		"Astrophysics": 9,
		"IntergalacticResearchNetwork": 0,
		"GravitonTechnology": 0,
		"WeaponsTechnology": 0,
		"ShieldingTechnology": 0,
		"ArmourTechnology": 0
	}
}
```

### Get price

`GET /bot/price/:ogameID/:nbr`

The `:nbr` parameter must be the required level for buildings or the quantity for ships and defences.

```
curl 127.0.0.1:8080/bot/price/4/13
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":{"Metal":9730,"Crystal":3892,"Deuterium":0,"Energy":0,"Darkmatter":0}}
```

### Get moons

`GET /bot/moons`

```
curl 127.0.0.1:8080/bot/moons
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":[
      {
         "ID":33633793,
         "Img":"https://gf3.geo.gfsrv.net/cdn2f/6c86116a2c1d0fc00f3b17a2b6ff49.gif",
         "Name":"luna",
         "Diameter":8602,
         "Coordinate":{
            "Galaxy":2,
            "System":133,
            "Position":8,
            "Type":3
         },
         "Fields":{
            "Built":0,
            "Total":1
         }
      }
   ]
}
```

### Get moon by ID

`GET /bot/moons/:moonID`

```
curl 127.0.0.1:8080/bot/moons/33633793
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "ID":33633793,
      "Img":"https://gf3.geo.gfsrv.net/cdn2f/6c86116a2c1d0fc00f3b17a2b6ff49.gif",
      "Name":"luna",
      "Diameter":8602,
      "Coordinate":{
         "Galaxy":2,
         "System":133,
         "Position":8,
         "Type":3
      },
      "Fields":{
         "Built":0,
         "Total":1
      }
   }
}
```

### Get moon with coordinates

`GET /bot/moons/:galaxy/:system/:position`

```
curl 127.0.0.1:8080/bot/moons/2/133/8
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "ID":33633793,
      "Img":"https://gf3.geo.gfsrv.net/cdn2f/6c86116a2c1d0fc00f3b17a2b6ff49.gif",
      "Name":"luna",
      "Diameter":8602,
      "Coordinate":{
         "Galaxy":2,
         "System":133,
         "Position":8,
         "Type":3
      },
      "Fields":{
         "Built":0,
         "Total":1
      }
   }
}
```

### Get bot planets

`GET /bot/planets`

```
curl 127.0.0.1:8080/bot/planets
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": [{
		"Img": "https://gf1.geo.gfsrv.net/cdnc3/05f9cbd97aef057af87dc00f448bdb.png",
		"ID": 33707619,
		"Name": "Homeworld",
		"Diameter": 12800,
		"Coordinate": {
			"Galaxy": 4,
			"System": 212,
			"Position": 8
		},
		"Fields": {
			"Built": 142,
			"Total": 188
		},
		"Temperature": {
			"Min": 4,
			"Max": 44
		}
	},
	{
		"Img": "https://gf1.geo.gfsrv.net/cdn9e/27d4ab63668a5100879ee5e2d67d78.png",
		"ID": 33711028,
		"Name": "Colony",
		"Diameter": 13904,
		"Coordinate": {
			"Galaxy": 4,
			"System": 208,
			"Position": 8
		},
		"Fields": {
			"Built": 117,
			"Total": 218
		},
		"Temperature": {
			"Min": 20,
			"Max": 60
		}
	}]
}
```

### Get bot planet by planet ID

`GET  /bot/planets/:planetID`

```
curl 127.0.0.1:8080/bot/planets/33711028
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"Img": "https://gf1.geo.gfsrv.net/cdn9e/27d4ab63668a5100879ee5e2d67d78.png",
		"ID": 33711028,
		"Name": "Colony",
		"Diameter": 13904,
		"Coordinate": {
			"Galaxy": 4,
			"System": 208,
			"Position": 8
		},
		"Fields": {
			"Built": 117,
			"Total": 218
		},
		"Temperature": {
			"Min": 20,
			"Max": 60
		}
	}
}
```

### Get bot planet with coordinates

`GET  /bot/planets/:galaxy/:system/:position`

```
curl 127.0.0.1:8080/bot/planets/4/208/8
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"Img": "https://gf1.geo.gfsrv.net/cdn9e/27d4ab63668a5100879ee5e2d67d78.png",
		"ID": 33711028,
		"Name": "Colony",
		"Diameter": 13904,
		"Coordinate": {
			"Galaxy": 4,
			"System": 208,
			"Position": 8
		},
		"Fields": {
			"Built": 117,
			"Total": 218
		},
		"Temperature": {
			"Min": 20,
			"Max": 60
		}
	}
}
```

### Get planet resources details

`GET  /bot/planets/:planetID/resources-details`

```
curl 127.0.0.1:8080/bot/planets/33672579/resources-details
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "Metal":{
         "Available":647533,
         "StorageCapacity":2920000,
         "CurrentProduction":55038
      },
      "Crystal":{
         "Available":870631,
         "StorageCapacity":1590000,
         "CurrentProduction":21240
      },
      "Deuterium":{
         "Available":433575,
         "StorageCapacity":470000,
         "CurrentProduction":4264
      },
      "Energy":{
         "Available":-2525,
         "CurrentProduction":3616,
         "Consumption":-6141
      },
      "Darkmatter":{
         "Available":2048,
         "Purchased":0,
         "Found":2048
      }
   }
}
```

### Get planet resource settings

`GET /bot/planets/:planetID/resource-settings`

```
curl 127.0.0.1:8080/bot/planets/33711028/resource-settings
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "MetalMine":100,
      "CrystalMine":100,
      "DeuteriumSynthesizer":100,
      "SolarPlant":100,
      "FusionReactor":0,
      "SolarSatellite":0,
      "Crawler":0
   }
}
```

### Set planet resource settings

`POST /bot/planets/:planetID/resource-settings`

```
curl 127.0.0.1:8080/bot/planets/33711028/resource-settings -d 'metalMine=90&crystalMine=80&deuteriumSynthesizer=70&solarPlant=90&fusionReactor=90&solarSatellite=90'
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get planet resources buildings

`GET  /bot/planets/:planetID/resources-buildings`

```
curl 127.0.0.1:8080/bot/planets/33711028/resources-buildings
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"MetalMine": 22,
		"CrystalMine": 20,
		"DeuteriumSynthesizer": 17,
		"SolarPlant": 24,
		"FusionReactor": 8,
		"SolarSatellite": 0,
		"MetalStorage": 9,
		"CrystalStorage": 8,
		"DeuteriumTank": 7
	}
}
```

### Get planet facilities

`GET  /bot/planets/:planetID/facilities`

```
curl 127.0.0.1:8080/bot/planets/33711028/facilities
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"RoboticsFactory": 2,
		"Shipyard": 0,
		"ResearchLab": 0,
		"AllianceDepot": 0,
		"MissileSilo": 0,
		"NaniteFactory": 0,
		"Terraformer": 0,
		"SpaceDock": 0
	}
}
```

### Get planet defences

`GET  /bot/planets/:planetID/defence`

```
curl 127.0.0.1:8080/bot/planets/33711028/defence
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"RocketLauncher": 0,
		"LightLaser": 0,
		"HeavyLaser": 0,
		"GaussCannon": 0,
		"IonCannon": 0,
		"PlasmaTurret": 0,
		"SmallShieldDome": 0,
		"LargeShieldDome": 0,
		"AntiBallisticMissiles": 0,
		"InterplanetaryMissiles": 0
	}
}
```

### Get planet ships

`GET  /bot/planets/:planetID/ships`

```
curl 127.0.0.1:8080/bot/planets/33711028/ships
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"LightFighter": 0,
		"HeavyFighter": 0,
		"Cruiser": 0,
		"Battleship": 0,
		"Battlecruiser": 0,
		"Bomber": 0,
		"Destroyer": 0,
		"Deathstar": 0,
		"SmallCargo": 0,
		"LargeCargo": 0,
		"ColonyShip": 0,
		"Recycler": 0,
		"EspionageProbe": 0,
		"SolarSatellite": 0
	}
}
```

### Build

`POST /bot/planets/:planetID/build/:ogameID/:nbr`

```
curl -XPOST 127.0.0.1:8080/bot/planets/33711028/build/4/1
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Build cancelable

`POST /bot/planets/:planetID/build/cancelable/:ogameID`

```
curl -XPOST 127.0.0.1:8080/bot/planets/33635904/build/cancelable/4
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Build military

`POST /bot/planets/:planetID/build/production/:ogameID/:nbr`

```
curl -XPOST 127.0.0.1:8080/bot/planets/33635904/build/production/204/10
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Build construction

`POST /bot/planets/:planetID/build/building/:ogameID`

```
curl -XPOST 127.0.0.1:8080//bot/planets/33635904/build/building/4
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Build technology

`POST /bot/planets/:planetID/build/technology/:ogameID`

```
curl -XPOST 127.0.0.1:8080//bot/planets/33635904/build/technology/108
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Build defences

`POST /bot/planets/:planetID/build/defence/:ogameID/:nbr`

```
curl -XPOST 127.0.0.1:8080//bot/planets/33635904/build/defence/401/10
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Build ships

`POST /bot/planets/:planetID/build/ships/:ogameID/:nbr`

```
curl -XPOST 127.0.0.1:8080/bot/planets/33635904/build/ships/204/10
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get military production

`GET  /bot/planets/:planetID/production`

```
curl 127.0.0.1:8080/bot/planets/33635904/production
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":[
      {
         "ID":204,
         "Nbr":1
      }
   ]
}
```

### Get current constructions

`GET  /bot/planets/:planetID/constructions`

```
curl 127.0.0.1:8080/bot/planets/33635904/constructions
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "BuildingID":4,
      "BuildingCountdown":592,
      "ResearchID":0,
      "ResearchCountdown":0
   }
}
```

### Cancel construction

`POST /bot/planets/:planetID/cancel-building`

```
curl -XPOST /bot/planets/33635904/cancel-building
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Cancel technology

`POST /bot/planets/:planetID/cancel-research`

```
curl -XPOST /bot/planets/33635904/cancel-research
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get planet resources

`GET  /bot/planets/:planetID/resources`

```
curl 127.0.0.1:8080/bot/planets/33711028/resources
```

Result:
```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": {
		"Metal": 497650,
		"Crystal": 276358,
		"Deuterium": 76848,
		"Energy": 349,
		"Darkmatter": 25000
	}
}
```

### Send missles

`POST /bot/planets/:planetID/send-ipm`

```
curl 127.0.0.1:8080/bot/planets/33711028/send-ipm -d 'ipmAmount=10&galaxy=1&system=153&position=11&type=1&priority=401'
```

### Jump Gate

`GET  /bot/moons/:moonID/jump-gate`

```
curl 127.0.0.1:8080/bot/moons/123654/jump-gate -d 'moonDestination=987456&ships=207,10&ships=205,5'
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "rechargeCountdown":0,
      "success":true
   }
}
```

### Get planet info

`GET  /bot/celestials/:celestialID/techs`

```
curl 127.0.0.1:8080/bot/celestials/33672579/techs
```

Result:
```json
{
   "Status":"ok",
   "Code":200,
   "Message":"",
   "Result":{
      "defenses":{
         "RocketLauncher":0,
         "LightLaser":0,
         "HeavyLaser":0,
         "GaussCannon":0,
         "IonCannon":0,
         "PlasmaTurret":0,
         "SmallShieldDome":0,
         "LargeShieldDome":0,
         "AntiBallisticMissiles":0,
         "InterplanetaryMissiles":0
      },
      "facilities":{
         "RoboticsFactory":10,
         "Shipyard":9,
         "ResearchLab":7,
         "AllianceDepot":0,
         "MissileSilo":0,
         "NaniteFactory":0,
         "Terraformer":0,
         "SpaceDock":0,
         "LunarBase":0,
         "SensorPhalanx":0,
         "JumpGate":0
      },
      "researches":{
         "EnergyTechnology":3,
         "LaserTechnology":3,
         "IonTechnology":0,
         "HyperspaceTechnology":0,
         "PlasmaTechnology":0,
         "CombustionDrive":6,
         "ImpulseDrive":3,
         "HyperspaceDrive":0,
         "EspionageTechnology":4,
         "ComputerTechnology":3,
         "Astrophysics":3,
         "IntergalacticResearchNetwork":0,
         "GravitonTechnology":0,
         "WeaponsTechnology":0,
         "ShieldingTechnology":0,
         "ArmourTechnology":0
      },
      "ships":{
         "LightFighter":0,
         "HeavyFighter":0,
         "Cruiser":0,
         "Battleship":0,
         "Battlecruiser":0,
         "Bomber":0,
         "Destroyer":0,
         "Deathstar":0,
         "SmallCargo":0,
         "LargeCargo":10,
         "ColonyShip":0,
         "Recycler":0,
         "EspionageProbe":0,
         "SolarSatellite":70,
         "Crawler":0,
         "Reaper":0,
         "Pathfinder":0
      },
      "supplies":{
         "MetalMine":26,
         "CrystalMine":22,
         "DeuteriumSynthesizer":15,
         "SolarPlant":22,
         "FusionReactor":0,
         "SolarSatellite":70,
         "MetalStorage":9,
         "CrystalStorage":8,
         "DeuteriumTank":6
      }
   }
}
```
