Create Alerts
=============

## Description

This action allows to register one or more new alerts in the  catalog.

```
http://<your_api_server.com>/catalog/alert/<entity_id>
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

The internal alerts should be defined through the catalog console or by the API, but only using the catalog token.

## Parameters

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>alerts</td>
			<td>Alerts list (<em>alert</em>) to register</td>
			<td>Not</td>
		</tr>
	</tbody>
</table>

Every alert element has the following structure:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>id</td>
			<td>Alert ID to register</td>
			<td>No</td>
		</tr>
		<tr>
			<td>name</td>
			<td>Alert name</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>description</td>
			<td>Alert description</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>type</td>
			<td>Alert type</td>
			<td>No</td>
		</tr>
		<tr>
			<td>trigger</td>
			<td>Trigger type</td>
			<td>Mandatory for internal, not applies for externals</td>
		</tr>
		<tr>
			<td>expression</td>
			<td>Expression to evaluate with the trigger</td>
			<td>Mandatory for internal, not applies for externals</td>
		</tr>
		<tr>
			<td>component</td>
			<td>ID of the component to which the sensor belongs</td>
			<td>Mandatory for internal, not applies for externals</td>
		</tr>
		<tr>
			<td>sensor</td>
			<td>ID of the sensor to which the alert applies</td>
			<td>Mandatory for internal, not applies for externals</td>
		</tr>
		<tr>
			<td>entity</td>
			<td>Related entity identifier associated with the alert</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

Please, note the following observations:

* The ID must identify an univocal alert, e.g., 2 alerts may not have the same ID.
* The ID must have only alphanumeric (i.e. letters and numbers) and dashes characters, with no embedded spaces.
* The list of trigger's types and expressions are defined by the platform: [Trigger types](../alert/alert.html).  
* The possible values ​​for the alert types are: <em>INTERNAL</em> or <em>EXTERNAL</em>.
* Entity parameter is not mandatory, if empty the alert will be associated with the entity specified in the URL

## Response data

This action doesn't return additional data beyond the [HTTP status code](../../general_model.html#reply). 

## Examples

### Adding one external alert

If <em>rec</em> entity wants to register a new custom external alert with <em>REC_ALERT_001</em> identifier, to monitorize that maximum daily values for sensor REC_001 ranged from 60 and 80, the request will be:

```
http://<your_api_server.com>/catalog/alert/rec
```

and in the body message:

```json
{"alerts":[
   {"id":"REC_ALERT_001",
    "name":"REC_ALERT_001",
    "description":"Custom alert to monitorize that maximum daily values for sensor REC_001 ranged from 60 and 80",
    "type":"EXTERNAL"
   }
]}
```

This request will register a new external alert with <em>ID REC_ALERT_001</em> and associated to <em>rec</em> entity (i.e. <em>rec</em> entity is who will publish alarms associated to this alert).

Remember, the external alerts are defined by third party entities(providers or applications), which will be the responsibles of calculating their logic and throw the related alarms when applies.

### Adding one internal alert

If we want to register a new internal alert with <em>ID REC_GT_45_ALERT_001</em>, to monitorize that values for sensor's rec REC_001 are greater than 45, the request to do is the following:

```
http://<your_api_server.com>/catalog/alert/rec
```

and in the body message:

```json
{"alerts":[
   {"id":"REC_GT_45_ALERT_001",
    "name":"REC_GT_45_ALERT_001",
    "description":"Internal alert to monitorize that values for sensor's rec REC_001 are greater than 45",
    "type":"INTERNAL",
    "trigger":"GT",
    "expression":"45",
    "component":"REC_COMP_001",
    "sensor":"REC_001"    
   }
]}
```

This request will register a new internal alert with <em>REC_GT_45_ALERT_001</em> identifier and associated to <em>REC_001</em> sensor which will publish an alarm when sensor value will be greater than 45.

**This operation must be done using the catalog token.**

