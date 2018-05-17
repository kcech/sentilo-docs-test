Retrieve active subscriptions
=============================

## Description

This action allows to retrieve the list of all our active subcriptions. Additionally, we can retrieve only subscriptions from a specific type.

```
http://<your_api_server.com>/subscribe/<event_type>
```

<table>
	<tbody>
		<tr>
			<th>Format</th>
			<td>json</td>
		</tr>
		<tr>
			<th>Method</th>
			<td>GET</td>
		</tr>
		<tr>
			<th>Permission</th>
			<td>Read</td>
		</tr>
		<tr>
			<th>Returns</th>
			<td>Active subscriptions</td>
		</tr>
	</tbody>
</table>

**<event_type>** is optional and allows to filter the subscription by type.

## Parameters

No additional parameters can be used.

## Response data

This action, additionally to the [HTTP status code](../../general_model#reply), will return a list of our active subscriptions:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>subscriptions</td>
			<td>List with all our active subscriptions</td>
			<td>No</td>
		</tr>
	</tbody>
</table>

Each **subscription** element contains this set of attributes:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>endpoint</td>
			<td>URL defined in the subscription</td>
			<td>No</td>
		</tr>
		<tr>
			<td>type</td>
			<td>Event type related to the subscription(data, order o alarm)</td>
			<td>No</td>
		</tr>
		<tr>
			<td>provider</td>
			<td>In case the type is <em>data</em> or <em>order</em> this attribute contains the provider identifier
			</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>sensor</td>
			<td>In case the type is <em>data</em> or <em>order</em> this attribute contains the sensor identifier
			</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>alarm</td>
			<td>In case the type is <em>alarm</em> this attribute contains the alert identifier</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

## Examples

### Request to retrieve all active subscriptions

```
http://<your_api_server.com>/subscribe
```

As response we will obtain:

```json
{
   "subscriptions":
   [{
      "endpoint":"http://<your_endpoint_notification_server.com>",
      "type":"ALARM",
      "alert":"alerta1"
   },{
      "endpoint":"http://<your_endpoint_notification_server.com>",
      "type":"DATA",
      "provider":"app_demo_provider",
      "sensor":"appdemo_sensor5_test"
   },{
      "endpoint":"http://<your_endpoint_notification_server.com>",
      "type":"DATA",
      "provider":"app_demo_provider",
      "sensor":"appdemo_sensor_test"
   },{
      "endpoint":"http://<your_endpoint_notification_server.com>",
      "type":"ALARM","alert":"11"
   }]
}
```

### Request to retrieve active subscriptions for a specific type

If we want to retrieve only the subscriptions to a specific event type:


```
http://<your_api_server.com>/subscribe/alarm
```

As response we will obtain:

```json
{
   "subscriptions":
   [{
      "endpoint":"http://<your_endpoint_notification_server.com>",
      "type":"ALARM",
      "alert":"alert1"
   },{
      "endpoint":"http://<your_endpoint_notification_server.com>",
      "type":"ALARM",
      "alert":"alert11"
   }]
}
```
