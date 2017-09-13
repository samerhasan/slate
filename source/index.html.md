---
title: Maverick  API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - python


toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

    MAVERICK is a rugged 4G standalone phone with no display, the size of a car key fob It relies on voice commands, and communicates with your smartphone App through the cell network.
    MAVERICK accesses your smartphone contacts to make calls and texts for you. The smartphone forwards calls and texts to MAVERICK phone based on rules you set on Maverick's essential app.

* No display
* No sensors
* No GPS tracking

Smartphones put a desktop in your pocket. Maverick only takes what's essential. for more [Maverick](https://www.maverickai.com/)

# Authentication



<aside class="notice">
Maverick command recognizer regonitzer is free for use in the Beta stage. 
</aside>

# API

## Get Command Slots


```java
	String url = "https://hlep.herokuapp.com/parse/";
	String jsonStr = sh.makeServiceCall(url + inputCommand.replace(" ", "%20"));
```

```python
	import requests
	request = requests.get(url + inputCommand)
```


> The above command returns JSON structured like this:

```json
  {
    "Intent": "message",
    "Receivier": "John",
    "Time": "Sunday 5 PM",
    "Frequency": "weekly",
    "Content": "Meet you soon",
    "Additional": ""
  }
```

Maverick web service retrieve Slots from commands based on AI and MLtechnologies. 

### HTTP Request

`https://hlep.herokuapp.com/parse/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
Intent | null | the intent of the command.  send message, make a call, set an alarm.
Receivier | null | contact name to be used to execute the command.
Time | null | command execution time. 
Frequency | null | command execution frequency. Daily, weekly monthly.
Content | null | the command content for message or alarm.
Additional | null | any additionalcommad from the user. 




<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Parsing JSON Object

```java
JSONObject jsonObj = new JSONObject(jsonStr);
Initial = jsonObj.getString("Initial");
commandIntent = jsonObj.getString("Intent");
Receiver = jsonObj.getString("Receiver");
Time = jsonObj.getString("Time");
Frequency = jsonObj.getString("Frequency");
AdditionalSound = jsonObj.getString("AdditionalSound");
Content = jsonObj.getString("Content");
                  
```

```python
import json

josnObj =  json.loads(request)

commandIntent = jsonObj["Intent"]
Receiver = jsonObj["Receiver"];
Time = jsonObj["Time"];
Frequency = jsonObj["Frequency"]
AdditionalSound = jsonObj["Additional"]
Content = jsonObj.["Content"] 


```


This endpoint retrieves a slots.


