Adding sensors or components to the catalog
===========================================

## Description

This action allows the provider to register one or more sensors / components in the  catalog.

```
 http://<your_api_server.com>/catalog/<provider_id>
```

<table>
	<tbody>
		<tr>
			<th>Formats</th>
			<td>json</td>
		</tr>
		<tr>
			<th>Method</th>
			<td>POST</td>
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

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>sensors</td>
			<td>Sensors list (<em>sensor</em>) to register</td>
			<td>Not</td>
		</tr>
	</tbody>
</table>

Every sensor element has the following structure:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>sensor</td>
			<td>Sensor ID to register</td>
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
			<td>No</td>
		</tr>
		<tr>
			<td>dataType</td>
			<td>Sensor data types</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>unit</td>
			<td>Unit of measure</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>component</td>
			<td>Component identifier to which the sensor belongs</td>
			<td>Yes</td>
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
			<td>Location/s of the component to which the sensor is</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>timeZone</td>
			<td>TimeZone used by sensor observations when it is different to UTC</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>publicAccess</td>
			<td>Visualization check for the sensor in the public zone</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentPublicAccess</td>
			<td>Visualization check for the component in the public zone</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>additionalInfo</td>
			<td>Additional params related to the sensor</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>componentAdditionalInfo</td>
			<td>Additional params related to the component</td>
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

Please, note the following observations:

* The state and substate of a sensor cannot be changed via te API, only from the catalog. The default value for state is 'online', default value for substate is empty.
* The identifier must identify an univocal sensor provider, e.g., 2 sensors of the same provider may not have the same ID.
* The identifier must have only alphanumeric (i.e. letters and numbers), undescores and hyphens characters, with no embedded spaces.
* The list of sensor's types are configured in the platform through the catalog web app. If you need a new one, it must be added using the administration. 
* The possible values ​​for the data type of the sensor is also defined in the platform configuration. The possible values ​​are: number, text or boolean. The default value is number.
* If the attribute component is not passed as a parameter, the platform itself will create a catalog component with the same name as the sensor (if it does not already exist).
* If the attribute componentType is not reported and the component does not already exists in the system, the component will be defined as a generic component type.
* If the location attribute is not reported, the component is defined as a mobile type (with no fixed location). Otherwise it will be defined as static and set its location with the coordinates provided. If the element has several locations they should be informed separated by comma character.
* If the attribute type and / or componentType values are ​​not configured in the catalog, the system will return a 400 error indicating that the parameters received are invalid .
* publicAccess param refers to the sensor's visibility in the sensor's public page. Default value is false.
* componentPublicAccess param refers to the components's visibility in the public map. Default value is false.
* additionalInfo param is a <key,value> map that allows to store additional sensor information not mapped to any specific parameter. The information of this data map must not follow any internal rule.
* componentAdditionalInfo param is a <key,value> map that allows to store additional component not mapped to any specific parameter. The information of this data map must not follow any internal rule.
* technicalDetails parameter is a <key,value> map that allows to store additional sensor information. The available keys and their possible values are:

<table>
	<tbody>
		<tr>
			<th>Description</th>
			<th>Key</th>
			<th>Values</th>
		</tr>
		<tr>
			<td>Producer</td>
			<td>producer</td>
			<td>not restricted</td>
		</tr>
		<tr>
			<td>Model</td>
			<td>model</td>
			<td>not restricted</td>
		</tr>
		<tr>
			<td>Serial number</td>
			<td>serialNumber</td>
			<td>not restricted</td>
		</tr>
		<tr>
			<td>Energy</td>
			<td>energy</td>
			<td>220VAC (electric network), 12_24_VDC (PoE), 185_230_V (lighting network), AUT_BAT (battery), SOLAR_BAT (solar battery)</td>
		</tr>
	</tbody>
</table>

* componentTechnicalDetails parameter is a <key,value> map that allows to store additional component information. The available keys and their possible values are:

<table>
	<tbody>
		<tr>
			<th>Description</th>
			<th>Key</th>
			<th>Values</th>
		</tr>
		<tr>
			<td>Producer</td>
			<td>producer</td>
			<td>not restricted</td>
		</tr>
		<tr>
			<td>Model</td>
			<td>model</td>
			<td>not restricted</td>
		</tr>
		<tr>
			<td>Serial number</td>
			<td>serialNumber</td>
			<td>not restricted</td>
		</tr>
		<tr>
			<td>MAC Address</td>
			<td>macAddress</td>
			<td>not restricted</td>
		</tr>
		<tr>
			<td>Energy</td>
			<td>energy</td>
			<td>220VAC (electric network), 12_24_VDC (PoE), 185_230_V (lighting network), AUT_BAT (battery), SOLAR_BAT (solar battery)</td>
		</tr>
		<tr>
			<td>Connection type</td>
			<td>connectivity</td>
			<td>ET_RJ45 (Ethernet RJ45), ET_POE (Ethernet PoE), 3G, WIFI</td>
		</tr>
	</tbody>
</table>

## Response data

This action doesn't return additional data beyond the [HTTP status code](../../general_model.html#reply) associated with each request to the platform.

## Examples

### Adding one sensor

If you want to register a new humidity sensor with RE0025 identifier associated with the component whose identifier is METEO-1 of rec provider, the request to do will be the following:

```
 http://<your_api_server.com>/catalog/rec
```

and in the body message:

```json
{"sensors":[
   {"sensor":"RE0025",
    "description":"sensor 25 of moisture",
    "type":"humidity", 
    "dataType":"number",
    "unit":"%",
    "component":"METEO-1", 
    "componentType":"meteo",
    "componentDesc":"Test componente",
    "location":"41.39479 2.148768",
    "timeZone":"CET" 
   }
]}
```

This request will register a new sensor with name METEO_HUM-1 in the system of humidity type . Additionally, this sensor will be associated with the component METEO-1. If the component does not exist in the system yet , will be registered with the properties defined in the request (componentType, componentDesc and location).

### Adding several sensors

In case it is necessary to add a serie of sensors, the request will be very similar to the previous one, modifying the message body:

```
 http://<your_api_server.com>/catalog/rec
```

in the body message

```json
{"sensors":[
   {"sensor":"tt01_REC013",
    "description":"sensor12",
    "type":"humidity",
    "dataType":"number",
    "unit":"grams",
    "component":"METEO-1",
    "componentType":"meteo",
    "location":"41.39479 2.148768"
   },
   {"sensor":"tt01_REC014",
    "description":"sensor12",
    "type":"humidity",
    "dataType":"number",
    "unit":"grams",
    "component":"METEO-1",
    "componentType":"estaciometeo",
    "location":"41.39479 2.148768"
   }
]}
```

In this case, instead of registering a single sensor, there will be added two new sensors associated with the component named METEO-1. If the component does not yet exist in the system, will be registered with the properties especified in the request (type and localtzació).

### Adding one sensor with additional info

If you want to register a new humidity sensor, as in the first example, but also need additional information for the sensor and its component, the request to do is the following:

```
 http://<your_api_server.com>/catalog/rec
```

and in the body message:

```json
{"sensors":[
   {"sensor":"RE0025",
    "description":"sensor 25 of moisture",
    "type":"humidity", 
    "dataType":"number",
    "unit":"%",
    "component":"METEO-1", 
    "componentType":"meteo",
    "componentDesc":"Test componente",
    "publicAccess":"true",
    "componentPublicAccess":"true",
    "location":"41.39479 2.148768",
    "additionalInfo":{"accuracy":"4.5%","voltage":"2.1-3.6"},
    "componentAdditionalInfo":{"altitude":"525 m."}
   }
]}
```

This request will register a new sensor with name METEO_HUM-1 in the system of humidity type, as in the first example, and stores with the sensor two new attributes: accuracy and voltage.
