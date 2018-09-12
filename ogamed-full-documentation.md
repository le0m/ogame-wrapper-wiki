### Set user-agent

`POST /bot/set-user-agent`

```
curl 127.0.0.1:8080/bot/set-user-agent -d 'userAgent="new user agent"'
```

Result:
```json
{"Status":"ok","Code":200,"Message":"","Result":null}
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

### Get server URL

```
curl 127.0.0.1:8080/bot/server-url
```

```json
{"Status":"ok","Code":200,"Message":"","Result":"https://s152-en.ogame.gameforge.com"}
```

### Get language

```
curl 127.0.0.1:8080/bot/language
```

```json
{"Status":"ok","Code":200,"Message":"","Result":"en"}
```

### Login

```
curl 127.0.0.1:8080/bot/login
```

```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Logout

```
curl 127.0.0.1:8080/bot/logout
```

```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get universe speed

```
curl 127.0.0.1:8080/bot/server/speed
```

```json
{"Status":"ok","Code":200,"Message":"","Result":7}
```

### Get universe speed fleet

```
curl 127.0.0.1:8080/bot/server/speed-fleet
```

```json
{"Status":"ok","Code":200,"Message":"","Result":2}
```

### Get ogame server version

```
curl 127.0.0.1:8080/bot/server/version
```

```json
{"Status":"ok","Code":200,"Message":"","Result":"6.7.2-pl4"}
```

### Get ogame server time

```
curl 127.0.0.1:8080/bot/server/time
```

```json
{"Status":"ok","Code":200,"Message":"","Result":"2018-09-12T21:33:57+01:00"}
```

### Is under attack

```
curl 127.0.0.1:8080/bot/is-under-attack
```

```json
{"Status":"ok","Code":200,"Message":"","Result":false}
```

### Get user infos

```
curl 127.0.0.1:8080/bot/user-infos
```

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

### Send message

```
curl 127.0.0.1:8080/bot/send-message -d 'playerID=123&message="How are you ?"'
```

```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get all fleets

```
curl 127.0.0.1:8080/bot/fleets
```

```json
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
			"HeavyFighter": 2,
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

`POST /bot/planets/:planetID/send-fleet`

Refer to [constants.go](https://github.com/alaingilbert/ogame/blob/master/constants.go) to figure out the IDs for `mission` / `speed` / `ships`...

```
curl 127.0.0.1:8080/bot/planets/123/send-fleet -d 'ships=204,1&ships=205,2&speed=10&galaxy=4&system=208&position=8&mission=3&metal=1&crystal=2&deuterium=3'
```

```json
{"Status":"ok","Code":200,"Message":"","Result":5575790}
```

### Cancel a fleet

`GET  /bot/fleets/:fleetID/cancel`

```
curl 127.0.0.1:8080/bot/fleets/5575790/cancel
```

```json
{"Status":"ok","Code":200,"Message":"","Result":null}
```

### Get attacks infos

```
curl 127.0.0.1:8080/bot/attacks
```

```json
{"Status":"ok","Code":200,"Message":"","Result":[]}
```

### Get galaxy infos

`GET  /bot/galaxy-infos/:galaxy/:system`

```
curl 127.0.0.1:8080/bot/galaxy-infos/4/205
```

```json
{
	"Status": "ok",
	"Code": 200,
	"Message": "",
	"Result": [{
		"ID": 33659802,
		"Activity": 37,
		"Name": "Colony",
		"Img": "https://gf2.geo.gfsrv.net/cdndf/3e567d6f16d040326c7a0ea29a4f41.gif",
		"Coordinate": {
			"Galaxy": 4,
			"System": 205,
			"Position": 8
		},
		"Administrator": false,
		"Inactive": false,
		"Vacation": false,
		"StrongPlayer": true,
		"HonorableTarget": true,
		"Debris": {
			"Metal": 0,
			"Crystal": 0,
			"RecyclersNeeded": 0
		},
		"Moon": null,
		"Player": {
			"ID": 100606,
			"Name": "Ozon",
			"Rank": 30
		},
		"Alliance": {
			"ID": 8,
			"Name": "POLSKA",
			"Rank": 26,
			"Member": 3
		}
	}]
}
```


### Get researches

```
curl 127.0.0.1:8080/bot/get-research
```

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

### Get bot planets

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