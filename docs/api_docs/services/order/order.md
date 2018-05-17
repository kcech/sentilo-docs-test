Order
=====

## Description

The order service allows to send or retrieve orders to sensors/actuators.

All requests for this service will have the following format:

```
http://<your_api_server.com>/order/<provider_id>/<sensor_id>
```

The sensor identifier, **<sensor_id>**, is optional and should be informed depending on the action we want to execute.

## Actions

The available actions for this service are:

* [Publish orders](./publish_order.html)
* [Retrieve orders](./get_orders.html)
