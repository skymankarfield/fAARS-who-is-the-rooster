# TESTS

## [Game Manager]
### createObject
curl -i -X POST -H 'Content-Type: application/json' -d '{"fullObjectName":"fullName","objectKey":"objectKeyTest","allowLogin":"1","loginInfo":[{"username":"email@mail.com","password":"passwordObject"}],"currentStateKey":"initialState","active":"0","transient":"1","attributes":[{"attributeKey":"attr1","value":"val","active":"1"},{"attributeKey":"attr2","value":"val","active":"0"},{"attributeKey":"attr3","value":"val","active":"1"}],"groups":[{"groupKey":"group4","active":"1"},{"groupKey":"group5","active":"0"},{"groupKey":"group6","active":"0"}],"currentGPSLocation":[{"currentLat":"1000000","currentLon":"1000000"}],"currentZone":"initialZone"}' http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1


* Receives a JSON file via POST method:
{
    "fullObjectName": "fullName",
    "objectKey": "objectKeyTest",
    "allowLogin": "1",
    "loginInfo": [
        {
            "username": "email@mail.com",
            "password": "passwordObject"
        }
    ],
    "currentStateKey": "initialState",
    "active": "0",
    "transient": "1",
    "attributes": [
        {
            "attributeKey": "attr1",
            "value": "val",
            "active": "1"
        },
        {
            "attributeKey": "attr2",
            "value": "val",
            "active": "0"
        },
        {
            "attributeKey": "attr3",
            "value": "val",
            "active": "1"
        }
    ],
    "groups": [
        {
            "groupKey": "group4",
            "active": "1"
        },
        {
            "groupKey": "group5",
            "active": "0"
        },
        {
            "groupKey": "group6",
            "active": "0"
        }
    ],
    "currentGPSLocation": [
        {
            "currentLat": "1000000",
            "currentLon": "1000000"
        }
    ],
    "currentZone": "initialZone"
}


* Sample Response 'On Success':
{
    "status": 0,
    "details": {
        "action": "createObject",
        "objectKey": "objectKeyTest",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Response 'On Failure':
{
    "status": 1,
    "message": "SQLSTATE[23000]: Integrity constraint violation: 1062 Duplicate entry 'objectKeyTest-1' for key 'objectKey'",
    "details": {
        "action": "createObject",
        "objectKey": "objectKeyTest",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


### getObjectByKey
curl -i -X GET http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/objectKey21


* Sample Response 'On Success':
{
    "fullObjectName": "fullName",
    "objectKey": "objectKeyTest",
    "currentStateKey": "initialState",
    "currentZone": "initialZone",
    "allowLogin": "1",
    "transient": "1",
    "active": "0",
    "currentGPSLocation": {
        "currentLat": "1000000",
        "currentLon": "1000000"
    },
    "loginInfo": {
        "username": "email@mail.com",
        "password": "passwordObject"
    },
    "attributes": [
        {
            "attributeKey": "attr1",
            "value": "val",
            "active": "1"
        },
        {
            "attributeKey": "attr2",
            "value": "val",
            "active": "0"
        },
        {
            "attributeKey": "attr3",
            "value": "val",
            "active": "1"
        }
    ],
    "groups": [
        {
            "groupKey": "group4",
            "active": "1"
        },
        {
            "groupKey": "group5",
            "active": "0"
        },
        {
            "groupKey": "group6",
            "active": "0"
        }
    ],
    "status": 0,
    "details": {
        "action": "getObjectByKey",
        "objectKey": "objectKeyTest",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Response 'On Failure':
{
    "status": 8,
    "message": "No game object ID found",
    "details": {
        "action": "getGameObjectID",
        "objectKey": "objectKey21"
    }
}


### getAllGameObjectsByGameInstanceKey
curl -i -X GET http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1


* Sample Response 'On Success':
{
    "gameObjects": [
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group4",
                    "active": "1"
                },
                {
                    "groupKey": "group5",
                    "active": "0"
                },
                {
                    "groupKey": "group6",
                    "active": "0"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest1",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group2",
                    "active": "0"
                },
                {
                    "groupKey": "group3",
                    "active": "0"
                },
                {
                    "groupKey": "group1",
                    "active": "1"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest1",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest2",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group1",
                    "active": "1"
                },
                {
                    "groupKey": "group2",
                    "active": "0"
                },
                {
                    "groupKey": "group3",
                    "active": "0"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest2",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest3",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group1",
                    "active": "1"
                },
                {
                    "groupKey": "group2",
                    "active": "0"
                },
                {
                    "groupKey": "group3",
                    "active": "0"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest3",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest4",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group4",
                    "active": "1"
                },
                {
                    "groupKey": "group5",
                    "active": "0"
                },
                {
                    "groupKey": "group6",
                    "active": "0"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest4",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest5",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group4",
                    "active": "1"
                },
                {
                    "groupKey": "group5",
                    "active": "0"
                },
                {
                    "groupKey": "group6",
                    "active": "0"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest5",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest6",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group4",
                    "active": "1"
                },
                {
                    "groupKey": "group5",
                    "active": "0"
                },
                {
                    "groupKey": "group6",
                    "active": "0"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest6",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        }
    ],
    "status": 0,
    "details": {
        "action": "getAllGameObjectsByGameInstanceKey",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Response 'On Failure':
{
    "status": 2,
    "message": "No game ID or game instance ID found",
    "details": {
        "action": "getGameInstanceID",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster"
    }
}


### getAllGameObjectsByGroupKey
curl -i -X GET http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/groups/group2


* Sample Response 'On Success':
{
    "gameObjects": [
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest1",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group2",
                    "active": "0"
                },
                {
                    "groupKey": "group3",
                    "active": "0"
                },
                {
                    "groupKey": "group1",
                    "active": "1"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest1",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest2",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group1",
                    "active": "1"
                },
                {
                    "groupKey": "group2",
                    "active": "0"
                },
                {
                    "groupKey": "group3",
                    "active": "0"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest2",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "fullObjectName": "fullName",
            "objectKey": "objectKeyTest3",
            "currentStateKey": "initialState",
            "currentZone": "initialZone",
            "allowLogin": "1",
            "transient": "1",
            "active": "0",
            "currentGPSLocation": {
                "currentLat": "1000000",
                "currentLon": "1000000"
            },
            "loginInfo": {
                "username": "email@mail.com",
                "password": "passwordObject"
            },
            "attributes": [
                {
                    "attributeKey": "attr1",
                    "value": "val",
                    "active": "1"
                },
                {
                    "attributeKey": "attr2",
                    "value": "val",
                    "active": "0"
                },
                {
                    "attributeKey": "attr3",
                    "value": "val",
                    "active": "1"
                }
            ],
            "groups": [
                {
                    "groupKey": "group1",
                    "active": "1"
                },
                {
                    "groupKey": "group2",
                    "active": "0"
                },
                {
                    "groupKey": "group3",
                    "active": "0"
                }
            ],
            "status": 0,
            "details": {
                "action": "getObjectByKey",
                "objectKey": "objectKeyTest3",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        }
    ],
    "status": 0,
    "details": {
        "action": "getAllGameObjectsByGroupKey",
        "groupKey": "group2",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Response 'On Failure':
{
    "status": 13,
    "message": "No game object entries found in database with given object group key",
    "details": {
        "action": "getAllGameObjectsByGroupKey",
        "groupKey": "group",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


### deleteObjectByKey
curl -i -X DELETE http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/objectKey2


* Sample Response 'On Success':
{
    "status": 0,
    "details": {
        "action": "deleteObjectByKey",
        "objectKey": "objectKeyTest",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Response 'On Failure':
{
    "status": 8,
    "message": "No game object ID found",
    "details": {
        "action": "getGameObjectID",
        "objectKey": "objectKey2"
    }
}


### deleteAllGameObjectsByGroupKey
curl -i -X DELETE http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/groups/group2


* Sample Response 'On Success':
{
    "gameObjects": [
        {
            "status": 0,
            "details": {
                "action": "deleteObjectByKey",
                "objectKey": "objectKeyTest1",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "deleteObjectByKey",
                "objectKey": "objectKeyTest2",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "deleteObjectByKey",
                "objectKey": "objectKeyTest3",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        }
    ],
    "status": 0,
    "details": {
        "action": "deleteAllGameObjectsByGroupKey",
        "groupKey": "group2",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Response 'On Failure':
{
    "status": 13,
    "message": "No game object entries found in database with given object group key",
    "details": {
        "action": "getAllGameObjectsByGroupKey",
        "groupKey": "group2",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


### deleteAllGameObjectsByGameInstanceKey
curl -i -X DELETE http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1


* Sample Response 'On Success':
{
    "gameObjects": [
        {
            "status": 0,
            "details": {
                "action": "deleteObjectByKey",
                "objectKey": "objectKeyTest4",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "deleteObjectByKey",
                "objectKey": "objectKeyTest5",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        },
        {
            "status": 0,
            "details": {
                "action": "deleteObjectByKey",
                "objectKey": "objectKeyTest6",
                "gameKey": "who_is_the_rooster",
                "gameInstanceKey": "rooster1"
            }
        }
    ],
    "status": 0,
    "details": {
        "action": "deleteAllGameObjectsByGameInstanceKey",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Response 'On Failure':
{
    "status": 12,
    "message": "No game object entries found in database with given game instance key",
    "details": {
        "action": "getAllGameObjectsByGameInstanceKey",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


### updateObjectByKey
curl -i -X PUT -H 'Content-Type: application/json' -d '{"fullObjectName":"a full new name","objectKey":"objectKey6","allowLogin":"1","loginInfo":[{"username":"email@mail.com","password":"passwordObject"}],"currentStateKey":"initialState","active":"0","transient":"1","attributes":[{"attributeKey":"attr1","value":"val","active":"1"},{"attributeKey":"attr2","value":"val","active":"0"},{"attributeKey":"attr3","value":"val","active":"1"}],"groups":[{"groupKey":"group4","active":"1"},{"groupKey":"group5","active":"0"},{"groupKey":"group6","active":"0"}],"currentGPSLocation":[{"currentLat":"1000000","currentLon":"1000000"}],"currentZone":"initialZone"}' http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/objectKey6


* Receives a JSON file via PUT method:
{
    "fullObjectName": "fullName",
    "objectKey": "objectKeyTest",
    "allowLogin": "1",
    "loginInfo": [
        {
            "username": "email@mail.com",
            "password": "passwordObject"
        }
    ],
    "currentStateKey": "initialState",
    "active": "0",
    "transient": "1",
    "attributes": [
        {
            "attributeKey": "attr1",
            "value": "val",
            "active": "1"
        },
        {
            "attributeKey": "attr2",
            "value": "val",
            "active": "0"
        },
        {
            "attributeKey": "attr3",
            "value": "val",
            "active": "1"
        }
    ],
    "groups": [
        {
            "groupKey": "group4",
            "active": "1"
        },
        {
            "groupKey": "group5",
            "active": "0"
        },
        {
            "groupKey": "group6",
            "active": "0"
        }
    ],
    "currentGPSLocation": [
        {
            "currentLat": "1000000",
            "currentLon": "1000000"
        }
    ],
    "currentZone": "initialZone"
}


* Sample Response 'On Success':
{
    "status": 0,
    "details": {
        "action": "updateObjectByKey",
        "objectKey": "objectKeyTest",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Response 'On Failure':
{
    "status": 8,
    "message": "No game object ID found",
    "details": {
        "action": "getGameObjectID",
        "objectKey": "objectKey6"
    }
}


### VerifyObjectLogin
curl -i -X GET http://faars-rocketfuel.javakafe.com/gameObjects/who_is_the_rooster/rooster1/verifyObjectLogin/email2@mail.com/passwordObject2


* Sample Response 'On Success':
{
    "objectKey": "objectKeyTest2",
    "active": "0",
    "allowLogin": "1",
    "status": 0,
    "details": {
        "action": "verifyObjectLogin",
        "username": "email2@mail.com",
        "password": "passwordObject2",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooster1"
    }
}


* Sample Reponse 'On Failure':
{
    "status": 2,
    "message": "No game ID or game instance ID found",
    "details": {
        "action": "getGameInstanceID",
        "gameKey": "who_is_the_rooster",
        "gameInstanceKey": "rooter1"
    }
}