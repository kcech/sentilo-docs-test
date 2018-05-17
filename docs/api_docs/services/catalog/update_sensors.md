Update data of a component / sensor
===================================

## Description

This action permits to update the catalog information related to components and/or sensors of a provider.

```
 http://<your_api_server.com>/catalog/<provider_id> 
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

The structure of the input parameters depends on what we want to modify, sensor or component data.

The following describes the structure of the input parameters in each case:

### Update components

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>components</td>
			<td>Components list (<em>component</em>) to update</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

Each element **component** has the following structure:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>component</td>
			<td>Component ID to update</td>
			<td>No</td>
		</tr>
		<tr>
			<td>componentType</td>
			<td>Component type</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentDesc</td>
			<td>Component description</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>location</td>
			<td>Component location/s</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentPublicAccess</td>
			<td>Visualization check for the public area</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentAdditionalInfo</td>
			<td>Additional params</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentTechnicalDetails</td>
			<td>Technical params</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

The constraints and validation for the parameters are the same as described in [Adding sensors or components](./create_sensors).

### Update sensors

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>sensors</td>
			<td>Sensors list (<em>sensor</em>) to update</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

Each **sensor** element has the following structure:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>sensor</td>
			<td>Sensor ID to update</td>
			<td>No</td>
		</tr>
		<tr>
			<td>description</td>
			<td>Sensor description</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>type</td>
			<td>Sensor type</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>dataType</td>
			<td>Data type of the sensor</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>unit</td>
			<td>Measurement unit</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>publicAccess</td>
			<td>Visualization check for the public area</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>additionalInfo</td>
			<td>Additional params</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>technicalDetails</td>
			<td>Technical params</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

The constraints and validation for the parameters are the same as described in [Adding sensors or components](./create_sensors).

## Response data

This action doesn't return additional data beyond the [HTTP status code](../../general_model#reply).

## Examples

### Request to update the sensor data

If you want to modify the sensor's description fot the identifiers <em>RE0012</em> and <em>RE0013</em>, from <em>rec</em> provider, the request will be:

```
 http://<your_api_server.com>/catalog/rec
```

in the body message:

```json
{"sensors":[
   {"sensor":"REC012","description":"sensor 12"},
   {"sensor":"REC013","description":"sensor 13"}
]}
```

This request will update the description of the sensors <em>RE0012</em> and <em>RE0013</em>.

Note: If you need to move a sensor to another component, it should be done by deleting the sensor and creating it again in the other component.

### Request to update the component data

If we want to update component data of a provider, like update its location and additional info, the request will be:

```
 http://<your_api_server.com>/catalog/rec
```

in the message body:

```json
{"components":[
   {"component":"COMP-2","location":"41.4051143 2.1320120","componentAdditionalInfo":{"altitude":"530 m."}}
]}
```
