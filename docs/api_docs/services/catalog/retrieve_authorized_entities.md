Retrieve providers / sensors list
=================================

## Description

This resource returns a list of providers and sensors for which you have at least read permission. Sensors that are in the offline state won't be listed. In addition, the service provides optional filtering by sensor type, component type and component name.

```
 http://<your_api_server.com>/catalog
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
			<td>List of providers, with their sensors, on which we has at least read permission</td>
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
			<td>type</td>
			<td>Sensor's type filter</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>component</td>
			<td>Component name filter</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentType</td>
			<td>Component's type filter</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

## Response data

As mentioned, this action, in addition to the [HTTP status code](../../general_model#reply), returns the list of providers for wich we have at least read permission.

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>providers</td>
			<td>Providers list <em>(provider)</em> with at least read permission</td>
			<td>Not</td>
		</tr>
	</tbody>
</table>

Each provider will have the following structure:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>provider</td>
			<td>Provider ID</td>
			<td>No</td>
		</tr>
		<tr>
			<td>permission</td>
			<td>Indicates whether it readable (R) or write (W) on the provider</td>
			<td>No</td>
		</tr>
		<tr>
			<td>sensors</td>
			<td>Provider list of sensors (sensor)</td>
			<td>No</td>
		</tr>
	</tbody>
</table>

Each list element **(sensor)** will have the following structure.

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
			<td>description</td>
			<td>sensor description</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>dataType</td>
			<td>Data sensor type (NUMBER, BOOLEAN or TEXT)</td>
			<td>No</td>
		</tr>
		<tr>
			<td>location</td>
			<td>Location where de sensor is</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>type</td>
			<td>Sensor type</td>
			<td>No</td>
		</tr>
		<tr>
			<td>unit</td>
			<td>Unities in the sensor data coming</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>timeZone</td>
			<td>Sensor's timezone</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>publicAccess</td>
			<td>Visualization check for the public area</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>component</td>
			<td>Component is associated the sensor</td>
			<td>No</td>
		</tr>
		<tr>
			<td>componentType</td>
			<td>Component type</td>
			<td>No</td>
		</tr>
		<tr>
			<td>componentDesc</td>
			<td>Component description</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentPublicAccess</td>
			<td>Visualization check for the public area</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>additionalInfo</td>
			<td>Additional params related to the sensor</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>technicalDetails</td>
			<td>Technical params related to the sensor</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentTechnicalDetails</td>
			<td>Technical params related to the component</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

## Examples

### Request to retrieve all Providers / Sensors

```
 http://<your_api_server.com>/catalog
```

in the response we will receive

```json
{
	"providers": [{
		"provider": "A",
		"permission": "WRITE",
		"sensors": [{
			"sensor": "MAR_01_00_SN001_1010",
			"description": "Sound Sensor MODI 001",
			"dataType": "NUMBER",
			"type": "noise",
			"unit": "dBa",
			"component": "MAR_01_00_SN001_1010",
			"componentType": "generic",
			"timeZone": "CET"
		}]
	}, {
		"provider": "C",
		"permission": "READ",
		"sensors": [{
			"sensor": "MAR_02_20_PM001_1010",
			"description": "PM10 Sensor IMI 001",
			"dataType": "NUMBER",
			"type": "air_quality_pm10",
			"unit": "ug/m3",
			"component": "air_quality",
			"componentType": "generic"
		}, {
			"sensor": "MAR_02_20_PM001_1012",
			"description": "PM10 Sensor IMI 002",
			"dataType": "NUMBER",
			"type": "air_quality_pm10",
			"unit": "ug/m3",
			"component": "air_quality",
			"componentType": "generic",
			"additionalInfo": {
				"supportMail": "support@imi.com"
			},
			"technicalDetails": {
				"producer": "xxxx",
				"model": "x-1",
				"serialNumber": "9999",
				"energy": "220VAC"
			},
			"componentTechnicalDetails": {
				"producer": "XXXX",
				"model": "X-1",
				"serialNumber": "9999",
				"macAddress": "00:17:4F:08:5F:61",
				"energy": "12_24_VDC",
				"connectivity": "WIFI"
			}
		}]
	}]
}
```

### Request to recover all the sensors in the catalog filtered by type

The request in this case is very similar to the previous one adding the type parameter:

```
 http://<your_api_server.com>/catalog?type=air_quality_pm10
```

In this case as a response we will receive:

```json
{"providers":[
    {
     "provider":"C","permission":"READ",
     "sensors":
     [{
       "sensor":"MAR_02_20_PM001_1010",
       "description":"PM10 Sensor IMI 001",
       "dataType":"NUMBER",
       "type":"air_quality_pm10",
       "unit":"ug/m3",
       "component":"air_quality",
       "componentType":"generic"
      },{
       "sensor":"MAR_02_20_PM001_1012",
       "description":"PM10 Sensor IMI 002",
       "dataType":"NUMBER",
       "type":"air_quality_pm10",
       "unit":"ug/m3",
       "component":"air_quality",
       "componentType":"generic",
       "additionalInfo":{"field1":"value1","field2":"value2"}
      }
     ]
    }
]}
```

### Other examples

```
http://<your_api_server.com>/catalog?component=comp_demo&type=air_quality_pm10
```

```
http://<your_api_server.com>/catalog?componentType=air_quality&type=air_quality_pm10
```
