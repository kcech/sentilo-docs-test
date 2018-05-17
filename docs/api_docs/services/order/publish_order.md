Publish an order
================

## Description

This operation allows to send an order to single sensor or to all sensors of a provider. Once the system receives the order, it sends a notification to all its subscribers.

```
http://<your_api_server.com>/order/<provider_id>/<sensor_id>
```

<table>
	<tbody>
		<tr>
			<th>Format</th>
			<td>json</td>
		</tr>
		<tr>
			<th>Method</th>
			<td>PUT</td>
		</tr>
		<tr>
			<th>Permission</th>
			<td>Writing</td>
		</tr>
		<tr>
			<th>Return</th>
			<td>No output data</td>
		</tr>
	</tbody>
</table>

## Parameters

Each order will have its specific structure with its associated information in the defined format (JSON).

The platform will only transfer the information to the subscribers, without checking its contents nor reading into it.

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>order</td>
			<td>Orden content</td>
			<td>Not</td>
		</tr>
	</tbody>
</table>

## Response data

This action does not return additional data beyond the [HTTP status code](../../general_model.html#reply).

## Examples

### Publish an order to a sensor/actuator

The following example shows how to send a request to the platform to publish a new order destined to the sensor with <em>RE0012</em> identifier belonging to the provider with ID <em>rec</em>:

```
http://<your_api_server.com>/order/rec/RE0012
```

in the body message:

```json
{"order":"Stop"}
```

### Publish an order to all the provider's sensors/actuators

The following example shows how to send a request to the platform to publish a new order to all the sensors belonging to the provider with <em>rec</em> identifier:

```
http://<your_api_server.com>/order/rec
```

in the body message

```json
{"order":"Start RE0012, RE0013"}
```
