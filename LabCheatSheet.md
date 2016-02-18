#IoT APIs 101 Lab Cheat Sheet

This document will have all the links, code snippets and notes that you will need to complete our "Dev Workshop | IoT APIs 101 with StrongLoop and IBM Bluemix"

## Important Links

Access Bluemix - http://bluemix.net

Get CURL - https://curl.haxx.se/

Download SOAP UI - https://www.soapui.org/

Access Cloud9 - http://c9.io

## Commands

```shell

npm install -g strongloop

slc loopback

cd <application-directory>

slc loopback:model

npm install loopback-connector-cloudant

node .

```

## Code Snippets

The following code snippets will help you in creating the final Consumer Application. 

### realtime.js change snippet

```javascript
var orgId = “<your-Organization-ID>”
var deviceType = “<your-device-Type>” 
var deviceId = “<your-device-ID>”
var deviceToken = “<your-device-Token>”
```

### Parse Fuel Event Data Function Node in NodeRed

```javascript
msg.fuel = msg.payload.d.fuel
msg.lat = msg.payload.d.lat
msg.long = msg.payload.d.long
msg.payload = {"fuel":msg.fuel,"lat":msg.lat,:long:msg.long,"loopback__model__name":"<Your Model Name>"}
return msg;
```

### datasources.json file in the Loopback Mode

```javascript
{
"db": {
  "name": "db",
  "connector": "memory" 
  },
  "cloudant": {
      "database": "vehicle-data",
      "username": "fe26cdf0-bd95-485b-aa5e-9862770eb319-bluemix", "password":
      "0cbdea29b0c41a6603ccbee9f5901d278e60ddfb25c3923f1f10103f285f11b6", "name": "cloudant",
      "connector": "cloudant"
    } 
}
```
