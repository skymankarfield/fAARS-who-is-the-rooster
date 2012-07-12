# TESTS

## [Game Manager]
### createObject
curl -i -X POST -H 'Content-Type: application/json' -d '{"fullObjectName":"fullName","objectKey":"objectKeyTest","allowLogin":"1","loginInfo":[{"username":"email@mail.com","password":"passwordObject"}],"currentStateKey":"initialState","active":"0","transient":"1","attributes":[{"attributeKey":"attr1","value":"val","active":"1"},{"attributeKey":"attr2","value":"val","active":"0"},{"attributeKey":"attr3","value":"val","active":"1"}],"groups":[{"groupKey":"group4","active":"1"},{"groupKey":"group5","active":"0"},{"groupKey":"group6","active":"0"}],"currentGPSLocation":[{"currentLat":"1000000","currentLon":"1000000"}],"currentZone":"initialZone"}' http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1

### getObjectByKey
curl -i -X GET http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/objectKey21

### getAllGameObjectsByGameInstanceKey
curl -i -X GET http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1

### getAllGameObjectsByGroupKey
curl -i -X GET http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/groups/group2

### deleteObjectByKey
curl -i -X DELETE http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/objectKey2

### deleteAllGameObjectsByGroupKey
curl -i -X DELETE http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/groups/group2

### deleteAllGameObjectsByGameInstanceKey
curl -i -X DELETE http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1

### updateObjectByKey
curl -i -X PUT -H 'Content-Type: application/json' -d '{"fullObjectName":"a full new name","objectKey":"objectKey6","allowLogin":"1","loginInfo":[{"username":"email@mail.com","password":"passwordObject"}],"currentStateKey":"initialState","active":"0","transient":"1","attributes":[{"attributeKey":"attr1","value":"val","active":"1"},{"attributeKey":"attr2","value":"val","active":"0"},{"attributeKey":"attr3","value":"val","active":"1"}],"groups":[{"groupKey":"group4","active":"1"},{"groupKey":"group5","active":"0"},{"groupKey":"group6","active":"0"}],"currentGPSLocation":[{"currentLat":"1000000","currentLon":"1000000"}],"currentZone":"initialZone"}' http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/objectKey6
