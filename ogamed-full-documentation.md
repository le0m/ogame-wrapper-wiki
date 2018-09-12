### Set user-agent

`POST /bot/set-user-agent`

```
curl 127.0.0.1:8080/bot/set-user-agent -d 'userAgent="new user agent"'
```

Result:
```
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get server

`GET  /bot/server`

```
curl 127.0.0.1:8080/bot/server
```

Result:
```
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

### Get server URL

```
curl 127.0.0.1:8080/bot/server-url
```

```
{"Status":"ok","Code":200,"Message":"","Result":"https://s152-en.ogame.gameforge.com"}
```

### Get language

```
curl 127.0.0.1:8080/bot/language
```

```
{"Status":"ok","Code":200,"Message":"","Result":"en"}
```

### Login

```
curl 127.0.0.1:8080/bot/login
```

```
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Logout

```
curl 127.0.0.1:8080/bot/logout
```

```
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get universe speed

```
curl 127.0.0.1:8080/bot/server/speed
```

```
{"Status":"ok","Code":200,"Message":"","Result":7}
```

### Get universe speed fleet

```
curl 127.0.0.1:8080/bot/server/speed-fleet
```

```
{"Status":"ok","Code":200,"Message":"","Result":2}
```

### Get ogame server version

```
curl 127.0.0.1:8080/bot/server/version
```

```
{"Status":"ok","Code":200,"Message":"","Result":"6.7.2-pl4"}
```

### Get ogame server time

```
curl 127.0.0.1:8080/bot/server/time
```

```
{"Status":"ok","Code":200,"Message":"","Result":"2018-09-12T21:33:57+01:00"}
```

### Is under attack

```
curl 127.0.0.1:8080/bot/is-under-attack
```

```
{"Status":"ok","Code":200,"Message":"","Result":false}
```

### Get user infos

```
curl 127.0.0.1:8080/bot/user-infos
```

```
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

### Send message

```
curl 127.0.0.1:8080/bot/send-message -d 'playerID=123&message="How are you ?"'
```

```
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get all fleets

```
curl 127.0.0.1:8080/bot/fleets
```

```
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": [{
		"Mission": 3,
		"ReturnFlight": false,
		"ID": 5575790,
		"Resources": {
			"Metal": 1,
			"Crystal": 2,
			"Deuterium": 3,
			"Energy": 0,
			"Darkmatter": 0
		},
		"Origin": {
			"Galaxy": 4,
			"System": 212,
			"Position": 8
		},
		"Destination": {
			"Galaxy": 4,
			"System": 208,
			"Position": 8
		},
		"Ships": {
			"LightFighter": 1,
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
		},
		"ArriveIn": 2170
	}]
}
```

### Send a fleet

```
POST /bot/planets/:planetID/send-fleet
```

```
curl 127.0.0.1:8080/bot/planets/123/send-fleet -d 'ships=204,1&ships=205,2&speed=10&galaxy=4&system=208&position=8&mission=3&metal=1&crystal=2&deuterium=3'
```

```
{"Status":"ok","Code":200,"Message":"","Result":5575790}
```

### Cancel a fleet

```
GET  /bot/fleets/:fleetID/cancel
```

```
curl 127.0.0.1:8080/bot/fleets/5575790/cancel
```

```
{"Status":"ok","Code":200,"Message":"","Result":null}
```