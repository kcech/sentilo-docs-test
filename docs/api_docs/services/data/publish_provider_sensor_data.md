Publishing observations from different sensors
==============================================

## Description

This action allows a provider to publish details of the observations made ​​by more than one sensor in a single message.


```
 http://<your_api_server.com>/data/<provider_id>
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

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>sensors</td>
			<td>List of sensors (sensor) for which we publish at least one observation</td>
			<td>No</td>
		</tr>
	</tbody>
</table>

Each sensor will have the following structure:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>sensor</td>
			<td>Sensor identifier</td>
			<td>No</td>
		</tr>
		<tr>
			<td>observations</td>
			<td>Observations list (<em>observation</em>) to publish
			</td>
			<td>No</td>
		</tr>
		<tr>
			<td>location</td>
			<td>Geolocation coordinates in which the sensor observations are obtained (latitude longitude format)</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

Each observation will have the structure described on page [Publish observations of a sensor](./publish_sensor_data.html):

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>value</td>
			<td>Observation value&nbsp;</td>
			<td>No</td>
		</tr>
		<tr>
			<td>timestamp</td>
			<td>Date and time at which the observation was made (dd/MM/yyyyTHH:mm:ssZ format)</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>location</td>
			<td>Geolocation coordinates in which the sensor has achieved this observation (latitude longitude format).</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

## Response Data

This action does not return additional data beyond the [HTTP status code](../../general_model.html#reply).

## Examples

### Request to send multiple observations of several sensors setting a LTC TimeZone

If we want to send the observations of a set of sensors for the provider named <em>rec</em>, setting timeZone to CET, the request to do is:

```
 http://<your_api_server.com>/data/rec
```

and in the body message:

```json
{"sensors":[
   {
    "sensor":"RE0012",
    "observations":[
      {"value":"1.1"},
      {"value":"1.2",
       "timestamp":"17/09/2012T12:34:45CET"},
      {"value":"1.3",
       "timestamp":"17/09/2012T10:34:45CET"}
    ]
   },{
    "sensor":"RE0013",
    "location":"41.12345 2.12354",
    "observations":[
      {"value":"2.1"},
      {"value":"2.2",
       "timestamp":"16/09/2012T15:43:21CET"},
      {"value":"2.3",
       "timestamp":"16/09/2012T10:43:21CET"}
    ]
   }
]}
```
