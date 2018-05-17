Alarm
=====

## Description

The alarm service allows you to record and retrieve alarms associated with an alert stored in the system catalog.

All requests for this service will have the following format:

```
 http://<your_api_server.com>/alarm/<id_alert> 
```

where <em>id_alert</em> identifies the alert for which you want to perform the action. 
The alert always should be defined before throwing the alarm using the Catalog or the through the [Alert](./services/alert/alert) service.


## Actions

The available actions for this service are:

* [Publish a new alarm associated with an alert](./publish_alarm)
* [Retrieve the latest alarms associated with an alert](./retrieve_alarms)
