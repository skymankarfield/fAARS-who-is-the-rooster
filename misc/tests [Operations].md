# TESTS

## [Operations]
### performOperatioByObjectKey
curl -i -X PUT -H 'Content-Type: application/json' -d '{"value":"5","operation":"+"}' http://faars-rocketfuel.javakafe.com/operations/who_is_the_rooster/rooster1/ObjectKeyTest/attr1


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


### performOperationByGroupKey
curl -i -X PUT -H 'Content-Type: application/json' -d '{"value":"5","operation":"+"}' http://faars-rocketfuel.javakafe.com/operations/who_is_the_rooster/rooster1/groups/group2/attr1


* Sample Response 'On Success':
{
    "gameObjects": [
        {
            "status": 0,
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest1",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest2",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest3",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        }
    ],
    "status": 0,
    "details": {
        "action": "performOperationByGroupKey",
        "groupKey": "group2",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1",
        "attributeKey": "attr1"
    }
}


* Sample Response 'On Failure':
{
    "status": 13,
    "message": "No game object entries found in database with given object group key",
    "details": {
        "action": "getAllGameObjectsByGroupKey",
        "groupKey": "group9",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


### peformOperationByGameInstanceKey
curl -i -X PUT -H 'Content-Type: application/json' -d '{"value":"5","operation":"+"}' http://faars-rocketfuel.javakafe.com/operations/who_is_the_rooster/rooster1/attr1


* Sample Response 'On Success':
{
    "gameObjects": [
        {
            "status": 0,
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKey6",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest1",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest2",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest3",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        },
        {
            "status": 16,
            "message": "Values are not permitted for the requested operation",
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest4",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        },
        {
            "status": 16,
            "message": "Values are not permitted for the requested operation",
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest5",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        },
        {
            "status": 16,
            "message": "Values are not permitted for the requested operation",
            "details": {
                "action": "performOperationByObjectKey",
                "objectKey": "objectKeyTest6",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1",
                "attributeKey": "attr1"
            }
        }
    ],
    "status": 0,
    "details": {
        "action": "performOperationByGameInstanceKey",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1",
        "attributeKey": "attr1"
    }
}


* Sample Response 'On Failure':
{
    "status": 2,
    "message": "No game ID or game instance ID found",
    "details": {
        "action": "getGameInstanceID",
        "gameKey": "who_is_the_roost",
        "gameInstanceKey": "rooster1"
    }
}