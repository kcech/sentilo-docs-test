Update Alerts
=============

## Description

This action allows to update one or more alerts in the  catalog.

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
			<td>PUT</td>
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

The internal alerts should be updated through the catalog console or by the API, but only using the catalog token.

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
			<td>Alerts list (<em>alert</em>) to update</td>
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
			<td>Alert identifier to update</td>
			<td>No</td>
		</tr>
		<tr>
			<td>name</td>
			<td>New alert name</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>description</td>
			<td>New alert description</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>type</td>
			<td>Alert type</td>
			<td>No</td>
		</tr>
		<tr>
			<td>trigger</td>
			<td>New trigger type</td>
			<td>Mandatory for internal, not applies for externals</td>
		</tr>
		<tr>
			<td>expression</td>
			<td>New expression to evaluate with the trigger</td>
			<td>Mandatory for internal, not applies for externals</td>
		</tr>
	</tbody>
</table>

Please, note the following observations:

* The list of trigger's types and expressions are defined in: [Trigger types](../alert/alert#InternalTriggerTypes).  
* The possible values ​​for the alert type are: <em>INTERNAL</em> or <em>EXTERNAL</em>.

## Response data

This action doesn't return additional data beyond the [HTTP status code](../../general_model#reply).

## Examples

### Update one external alert

If <em>rec</em> entity wants to update the external alert with <em>REC_ALERT_001</em> identifier to modify its name, the request to do will be:

```
http://<your_api_server.com>/catalog/alert/rec
```

and in the body message:

```json
{"alerts":[
   {"id":"REC_ALERT_001",
    "name":"REC_EXTERNAL_ALERT_001",
    "type":"EXTERNAL"
   }
]}
```

This request will update the external alert with REC_ALERT_001 identifier updating its name to REC_EXTERNAL_ALERT_001.

Remember, the external alerts are defined by third party entities(providers or applications), which will be the responsibles of calculating their logic and throw the related alarms when applies.

### Update one internal alert

If we want to update the internal alert with <em>REC_GT_45_ALERT_001</em> identifier to change its description, the request will be:

```
http://<your_api_server.com>/catalog/alert/rec
```

and in the body message:

```json
{"alerts":[
   {"id":"REC_GT_45_ALERT_001",    
    "type":"INTERNAL",
    "description":"New description"
   }
]}
```

This request will update the description of the internal alert with <em>REC_GT_45_ALERT_001</em> identifier changing its value to "New description".

**This operation must be done using the catalog token.**

