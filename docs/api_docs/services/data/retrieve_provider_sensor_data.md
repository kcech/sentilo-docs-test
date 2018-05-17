Read observations from provider's sensors
=========================================

## Description

This action allows to retrieve the latest observations of the sensors of a provider. In addition, the service can also specify search criterias to retrieve observations: filter by a given time period and / or to indicate the maximum number of observations to be recovered.

```
 http://<your_api_server.com>/data/<provider_id>?<parameter>=<value>
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
			<td>Reading</td>
		</tr>
		<tr>
			<th>Return</th>
			<td>List with the observations from provider's sensors</td>
		</tr>
	</tbody>
</table>

**Because the number of sensors from a supplier can be very high, and therefore the amount of information returned can be very large, be careful using this operations due to performance reasons.**

## Parameteres

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>from</td>
			<td>Indicates the beginning of the time period for which you want to retrieve the observations.</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>to</td>
			<td>Indicates the end of the time period for which you want to retrieve the observations.</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>limit</td>
			<td>Specifies the maximum number of observations for each sensor to recover.</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

Please note the following:

* The maximum number of records returned will be fixed by the platform settings. If the parameter passed is higher, the number of records returned will be equalsa to the maximum value configured in the platform.
* If the limit parameter is not set, only one record will be returned.
* All dates must have the following format: dd/MM/yyyyTHH:mm:ss

## Response data

In addition to the [HTTP status code](../../general_model.html#reply), the observation data is returned in the body contents as a list of observations:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>sensor</td>
			<td>List of sensors (sensor) for the observations that have been retrieved</td>
			<td>No</td>
		</tr>
	</tbody>
</table>

Each sensor has the following structure:

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
			<td>List of the latest sensor observations</td>
			<td>No</td>
		</tr>
	</tbody>
</table>

Finally, each observation (observation) has the following structure:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Opional</th>
		</tr>
		<tr>
			<td>value</td>
			<td>Observation value</td>
			<td>No</td>
		</tr>
		<tr>
			<td>timestamp</td>
			<td>The time at which the observation was made (dd/MM/yyyyTHH:mm:ss format)</td>
			<td>No</td>
		</tr>
		<tr>
			<td>time</td>
			<td>The time when the observation was made in milliseconds</td>
			<td>No</td>
		</tr>
		<tr>
			<td>location</td>
			<td>Geolocation coordinates in which the sensor was recorded observation</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

## Examples

### Request to retrieve the latest observations from a provider after a given date

If we want to retrieve the latest observations of the sensors associated with the provider named rec from a given date we should make the following request:

```
 http://<your_api_server.com>/data/rec?from=10/09/2012T10:00:00
```

As response we will receive:

```json
{"sensors":[
   {
      "sensor":"RE0012",
      "observations":
      [{
         "value":"1",
         "timestamp":"10/09/2012T10:05:00",
         "time":1510561800000
      },{
         "value":"1.2",
         "timestamp":"10/09/2012T07:05:00",
         "time":1510561800000
      }]
   },{
      "sensor":"RE0013",
      "observations":
      [{
         "value":"24",
         "timestamp":"10/09/2012T10:06:10",
         "time":1510561800000
      }]
   }
]}
```

### Request to retrieve the latest observations from rec provider

If you only want to retrieve the last observation of the RE0012 sensor, the request to do is:

```
 http://<your_api_server.com>/data/rec
```

As response we will receive:

```json
{"sensors":[
   {
      "sensor":"RE0012",
      "observations":
      [{
         "value":"1",
         "timestamp":"10/09/2012T10:05:00",
         "time":1510561800000
      }]
   },{
      "sensor":"RE0013",
      "observations":
      [{
         "value":"24",
         "timestamp":"10/09/2012T10:06:10",
         "time":1510561800000
      }]
   }
]}
```
