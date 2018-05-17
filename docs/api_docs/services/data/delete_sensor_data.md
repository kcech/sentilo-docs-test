Delete Observations
===================

## Description

This action allows to delete observations made by one or several sensors of a provider.

```
 http://<your_api_server.com>/data/<provider_id>/<sensor_id>
```

<table>
	<tbody>
		<tr>
			<th>Formats</th>
			<td>json</td>
		</tr>
		<tr>
			<th>Method</th>
			<td>DELETE</td>
		</tr>
		<tr>
			<th>Permission</th>
			<td>Writing</td>
		</tr>
		<tr>
			<th>Returns</th>
			<td>No output data</td>
		</tr>
	</tbody>
</table>

## Parameters

No additional data is sent.

## Response data

This action does not return additional data beyond the [HTTP status code](../../general_model.html#reply).

## Examples

### Request to delete the last observation of a sensor

If we want delete the last observation received by the plataform of the sensor with id <em>REC1102</em> of the provider named <em>rec</em>, the request to do is:

```
 http://<your_api_server.com>/data/rec/RE0012
```

### Request to delete the last observations of a provider´s sensors

If we want to delete the last observation of each sensor ot the provider named <em>rec</em>, the request to do is:

```
 http://<your_api_server.com>/data/rec
```
