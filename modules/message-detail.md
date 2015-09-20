<!--
{
"name": "message-deatil",
"version" : "0.1",
"title" : "Neo Message Detail",
"description" : "This module cointain details of NEO Messages",
"homepage" : "https://intralinks.com",
"freshnessDate" : 2015-09-19
}
-->



<!-- @section -->

##NEO base message structure


NEO's messages have a basic structure. so lets start with an example


```code

{
    "message": {
        "header": {
            "messageVersion": "1.1",
            "messageTimestamp": "2015-09-15T05:24:24.620Z",
            "accessToken": "b52be51f95dbfb3537ee51b8e2cad570ec8903bb242b1f3a37303464cccebd36",
            "accessTokenKeyId": "cf980c77-28e0-4d4a-906d-b8305b06c862",
            "expiration": "2015-09-15T05:34:24.620Z",
            "accessTokenTimestamp": "2015-09-15T05:24:24.620Z",
            "signedFields": [
                "message.context",
                "message.header.accessTokenTimestamp",
                "message.header.expiration",
                "message.header.signedFields",
                "message.control.operation",
                "message.metadata.system.assetType",
                "message.metadata.system.parentCollection"
            ],
            "messageType": "createAssetLocationRequest"
        },
        "context": {
            "appId": "f5a0c9c3-56e0-49c5-8db5-856d5bd7e61e",
            "businessTransactionId": "ec214f41-0c64-48cf-b0ae-9120a4b02bc9",
            "sessionId": "97fa65ba-b3aa-4644-89f5-3ec8138eafce",
            "userId": "2f95b6f9-43a9-4fd5-d2a1-e0055e8b7f88",
            "businessAction": "createNewDocument"
        },
        "control": {
            "operation": "createAsset",
            "xDatanodeCollectionId": "ddbf838b-9a17-454f-9cc3-a4bf38a13d64"
        },
        "metadata": {
            "system": {
                "assetType": "app.via.asset.workspace",
                "parentCollection": "be292468-e159-48af-b823-cc91363b131f"
            }
        }
    }
}

```


now on the above message you can see that all the json is wrapped on a 'message' object. and that it contains 4 sections header, context, control, metadata.


<!-- @section -->

###Header


An example of the header is



```code
{
    "header": {
        "messageVersion": "1.1",
        "messageTimestamp": "2015-09-15T05:24:24.620Z",
        "accessToken": "b52be51f95dbfb3537ee51b8e2cad570ec8903bb242b1f3a37303464cccebd36",
        "accessTokenKeyId": "cf980c77-28e0-4d4a-906d-b8305b06c862",
        "expiration": "2015-09-15T05:34:24.620Z",
        "accessTokenTimestamp": "2015-09-15T05:24:24.620Z",
        "signedFields": [
            "message.context",
            "message.header.accessTokenTimestamp",
            "message.header.expiration",
            "message.header.signedFields",
            "message.control.operation",
            "message.metadata.system.assetType",
            "message.metadata.system.parentCollection"
        ],
        "messageType": "createAssetLocationRequest"
    }
}

```


This section contains 4 main parts

* The message Version: this will define the structure of the message in this case we are using and explaining version 1.1 of the NEO messages.

* The information to authenticate the message: this are the accessToken (signature of the message) the accessTokenKeyId and the signed fields

* The expiration and timestamp: this is defined by the messageTimestamp, and the expiration.

* The message type: this is the messageType. examples of this can be createAssetLocationRequest, createEntitlementAssertionsRequest, getAssetLocationRequest, etc. (we will go into detail of this later)



<!-- @section -->

###Context


An example of the context is



```code

{
    "context": {
        "appId": "f5a0c9c3-56e0-49c5-8db5-856d5bd7e61e",
        "businessTransactionId": "ec214f41-0c64-48cf-b0ae-9120a4b02bc9",
        "sessionId": "97fa65ba-b3aa-4644-89f5-3ec8138eafce",
        "userId": "2f95b6f9-43a9-4fd5-d2a1-e0055e8b7f88",
        "businessAction": "createNewDocument"
    }

}

```


This section contains.

* Application Id: the identification of your application when you register with IL

* App information passed and return unchanged. like the bussinessTransactionId, sessionId and businessAction

* The User Id: this is the uuid of the user trying to execute the message



<!-- @section -->

###Control


An example of Context is:

```code
{
    "control": {
        "operation": "createAsset",
        "xDatanodeCollectionId": "ddbf838b-9a17-454f-9cc3-a4bf38a13d64"
    }

}

```

this section contains

* Operation to be executed by the message type.

* a definition of where the content is going to be hosted (this will be deprecated in the future.)

<!-- @section -->

###Metadata

this section contains system information and anything extra required. in the example we are only sending system information like asset type that we are creating and what is the parent id that we are going to be creating the asset under.

```code

{
    "metadata": {
        "system": {
            "assetType": "app.via.asset.workspace",
            "parentCollection": "be292468-e159-48af-b823-cc91363b131f"
        }
    }
}

```

