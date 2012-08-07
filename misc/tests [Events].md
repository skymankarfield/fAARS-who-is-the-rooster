# TESTS

## [Events]
### catchEvent
curl -i -X PUT -H 'Content-Type: application/json' -d '{"eventKey":"unlock","eventGeneratorKey":"game_instance_1","eventRecipientKey":"plot_point_1"}' http://faars-rocketfuel.javakafe.com/who_is_the_rooster/rooster1/events


* Receives a JSON file via PUT method:
{
	"eventKey":"unlock",
	"eventGeneratorKey":"game_instance_1",
	"eventRecipientKey":"plot_point_1"
}


* Sample Response 'On Success':
{
    "status": 0,
    "details": {
        "action": "performOperationByObjectKey",
        "objectKey": "objectKey6",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1",
        "attributeKey": "attr1"
    }
}


* Sample Response 'On Failure':
{
    "status": 8,
    "message": "No game object ID found",
    "details": {
        "action": "getGameObjectID",
        "objectKey": "ObjectKeyTest"
    }
}