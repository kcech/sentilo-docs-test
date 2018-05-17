Data
====

## Description

The data service allows to read, write or delete the observations of the registered sensors.

All requests for this service will have the following format:

```
 http://<your_api_server.com>/data/<provider_id>/<sensor_id>
```

where **<provider_id>** and **<sensor_id>** correspond to the sensor and provider identifiers on which we want to perform the requested action.

## Actions

The available actions for this service are:

* [Publish observations of a sensor](./publish_sensor_data.html)
* [Publish observations from sensors of a provider](./publish_provider_sensor_data.html)
* [Delete observations](./delete_sensor_data.html)
* [Read observations from a sensor](./retrieve_sensor_data.html)
* [Read observations from sensors of a provider](./retrieve_provider_sensor_data.html)

