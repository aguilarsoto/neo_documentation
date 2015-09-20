<!--
{
"name": "message-response-detail",
"version" : "0.1",
"title" : "Neo Message Response Detail",
"description" : "This module cointain details of NEO Messages Location response",
"homepage" : "https://intralinks.com",
"freshnessDate" : 2015-09-19
}
-->



<!-- @section -->

#NEO base 'Location Response' message structure


In case your Asset request is successful you will receive a response that looks a bit like this.


```code

{
    "message": {
        "context": {
            "appId": "f5a0c9c3-56e0-49c5-8db5-856d5bd7e61e",
            "assetId": "c02df6b4-0920-4f84-a5fb-88fd80cd0458",
            "businessAction": "getDocument",
            "businessTransactionId": "4311b02d-51f9-4afd-a0e8-40846ef0d8e0",
            "sessionId": "ccbe6d0d-3baf-4a25-b144-317209956a83",
            "systemTransactionId": "90860d0d-6730-4418-afb1-2c76841fd883",
            "userId": "2f95b6f9-43a9-4fd5-d2a1-e0055e8b7f88"
        },
        "header": {
            "messageVersion": "1.1",
            "messageType": "getAssetLocationResponse",
            "messageTimestamp": "2015-09-20T05:25:15.197Z"
        },
        "response": {
            "data": {
                "message": {
                    "context": {
                        "appId": "f5a0c9c3-56e0-49c5-8db5-856d5bd7e61e",
                        "assetId": "c02df6b4-0920-4f84-a5fb-88fd80cd0458",
                        "businessAction": "getDocument",
                        "businessTransactionId": "4311b02d-51f9-4afd-a0e8-40846ef0d8e0",
                        "sessionId": "ccbe6d0d-3baf-4a25-b144-317209956a83",
                        "systemTransactionId": "90860d0d-6730-4418-afb1-2c76841fd883",
                        "userId": "2f95b6f9-43a9-4fd5-d2a1-e0055e8b7f88"
                    },
                    "control": {
                        "locationMethod": "POST",
                        "locationURL": "https://c01-il-bos-service-vianeodev1.neo.intralinks.com:443/asset",
                        "operation": "getAsset"
                    },
                    "header": {
                        "accessToken": "854eb2360a12ea4b95c4995e8c249674672d80b4f89c0600fafcf30b160a5fc2",
                        "accessTokenKeyId": "8e5f5203-cf89-4fb5-9449-7b62e507f713",
                        "accessTokenTimestamp": "2015-09-20T05:25:15.197Z",
                        "expiration": "2015-09-20T05:35:15.197Z",
                        "messageVersion": "1.1",
                        "messageType": "getAssetRequest",
                        "oneTimeUse": false,
                        "signedFields": [
                            "message.context",
                            "message.header.accessTokenTimestamp",
                            "message.header.expiration",
                            "message.header.oneTimeUse",
                            "message.header.signedFields",
                            "message.control.operation",
                            "message.control.locationURL"
                        ]
                    }
                }
            },
            "status": {
                "result": "OK",
                "code": 200
            }
        }
    }
}

```


this response is also wrapped in a message object and consists in 4 parts: Header, Context, Status, Response.


<!-- @section -->

##Header

The header section of the message it gets cut into just containing the message Version, the type and the timestamp, more use for validation.

```code

{
    "header": {
        "messageVersion": "1.1",
        "messageType": "getAssetLocationResponse",
        "messageTimestamp": "2015-09-20T05:25:15.197Z"
    }

}

```


<!-- @section -->
##Context
The context section is returned exactly as it was sent as a way to maintain status.

```code
{
    "context": {
        "appId": "f5a0c9c3-56e0-49c5-8db5-856d5bd7e61e",
        "assetId": "c02df6b4-0920-4f84-a5fb-88fd80cd0458",
        "businessAction": "getDocument",
        "businessTransactionId": "4311b02d-51f9-4afd-a0e8-40846ef0d8e0",
        "sessionId": "ccbe6d0d-3baf-4a25-b144-317209956a83",
        "systemTransactionId": "90860d0d-6730-4418-afb1-2c76841fd883",
        "userId": "2f95b6f9-43a9-4fd5-d2a1-e0055e8b7f88"
    }
}
```


<!-- @section -->

##Response

The response section consists in two different sections, the status and the data.

```code

{
    "response": {
        "data": {
            "message": {
                "context": {
                    "appId": "f5a0c9c3-56e0-49c5-8db5-856d5bd7e61e",
                    "assetId": "c02df6b4-0920-4f84-a5fb-88fd80cd0458",
                    "businessAction": "getDocument",
                    "businessTransactionId": "4311b02d-51f9-4afd-a0e8-40846ef0d8e0",
                    "sessionId": "ccbe6d0d-3baf-4a25-b144-317209956a83",
                    "systemTransactionId": "90860d0d-6730-4418-afb1-2c76841fd883",
                    "userId": "2f95b6f9-43a9-4fd5-d2a1-e0055e8b7f88"
                },
                "control": {
                    "locationMethod": "POST",
                    "locationURL": "https://c01-il-bos-service-vianeodev1.neo.intralinks.com:443/asset",
                    "operation": "getAsset"
                },
                "header": {
                    "accessToken": "854eb2360a12ea4b95c4995e8c249674672d80b4f89c0600fafcf30b160a5fc2",
                    "accessTokenKeyId": "8e5f5203-cf89-4fb5-9449-7b62e507f713",
                    "accessTokenTimestamp": "2015-09-20T05:25:15.197Z",
                    "expiration": "2015-09-20T05:35:15.197Z",
                    "messageVersion": "1.1",
                    "messageType": "getAssetRequest",
                    "oneTimeUse": false,
                    "signedFields": [
                        "message.context",
                        "message.header.accessTokenTimestamp",
                        "message.header.expiration",
                        "message.header.oneTimeUse",
                        "message.header.signedFields",
                        "message.control.operation",
                        "message.control.locationURL"
                    ]
                }
            }
        },
        "status": {
            "result": "OK",
            "code": 200
        }
    }
}

```

The status basically contains the http code and description of the status of the response since the actual status is always 200.

and the data section basically contains the request message that needs to be sent to the Content node already signed and ready to be sent. it only needs to add some extra information before sending the request (this will be explained in a later moment.)

