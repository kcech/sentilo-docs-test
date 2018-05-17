Retrieve Authorized Alerts
==========================

## Description

This action returns the list of alerts for which the <em>entity_id</em> could do a subscription, i.e., alerts that belongs to <em>entity_id</em> or alerts for which <em>entity_id</em> has read permission over its owner. 
In addition, the service also allows you to specify search criteria to filter alerts to be retrieved: filter by alert type and / or filter by trigger type.

```
 http://<your_api_server.com>/catalog/alert/<entity_id>?<parameter>=<value>
```

The <em>entity_id</em> is optional and can be an Application or a Provider. 

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
			<td>List of authorized alerts</td>
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
			<td>Alert's type filter</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>trigger</td>
			<td>Trigger's type filter</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

Please, note the following observations:

* The list of trigger's types available are defined by the platform: [Trigger types](../alert/alert#InternalTriggerTypes).  
* The possible values ​​for the alert type is also defined by the platform and are: <em>INTERNAL</em>, <em>EXTERNAL</em>.

## Response data

As commented before, this action, in addition to the [HTTP status code](../../general_model#reply), returns the list of alerts for which <em>entity_id</em> has at least read permission.

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>alerts</td>
			<td>Alerts list (<em>alert</em>)</td>
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
			<td>Alert ID</td>
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
			<td>entity</td>
			<td>Related entity</td>
			<td>No</td>
		</tr>
		<tr>
			<td>type</td>
			<td>Alert type</td>
			<td>No</td>
		</tr>
		<tr>
			<td>trigger</td>
			<td>Trigger type</td>
			<td>No, but only returned for internal alerts</td>
		</tr>
		<tr>
			<td>expression</td>
			<td>Expression to evaluate with the trigger</td>
			<td>No, but only returned for internal alerts</td>
		</tr>
		<tr>
			<td>component</td>
			<td>Component identifier to which the sensor belongs</td>
			<td>No, but only returned for internal alerts</td>
		</tr>
		<tr>
			<td>sensor</td>
			<td>Sensor identifier to which the alert applies</td>
			<td>No, but only returned for internal alerts</td>
		</tr>
	</tbody>
</table>


## Examples

### Request to retrieve all the authorized alerts

The following request shows an example to retrieve all the authorized alerts for <em>rec</em> entity:

```
 http://<your_api_server.com>/catalog/alert/rec
```

and the response will be:

```json
{
  "alerts" : [
    {
      "id" : "REC_ALERT_001",
      "name" : "REC_ALERT_001",
      "description" : "Custom alert to monitorize that maximum daily values for sensor REC_001 ranged from 60 and 80",
      "entity" : "SAMCLA",
      "type" : "EXTERNAL"
    },
    {
      "id" : "REC_ALERT_002",
      "name" : "REC_ALERT_002",
      "description" : "Internal alert to check if S00020114-0 value is greater than 45",
      "entity" : "SAMCLA",
      "type" : "INTERNAL",
      "trigger" : "GT",
      "expression" : "45",
      "component" : "S00020114",
      "sensor" : "S00020114-0"
    }
  ]
}
```

### Request to retrieve all the authorized alerts filtered by type and trigger

The following request shows an example to retrieve all internal alerts for <em>rec</em> entity with trigger type equal to GT.

```
 http://<your_api_server.com>/catalog/alert/rec?type=INTERNAL&trigger=GT
```

and the response will be:

```
{"alerts":[
   {
      "id" : "REC_ALERT_002",
      "name" : "REC_ALERT_002",
      "description" : "Internal alert to check if S00020114-0 value is greater than 45",
      "entity" : "SAMCLA",
      "type" : "INTERNAL",
      "trigger" : "GT",
      "expression" : "45",
      "component" : "S00020114",
      "sensor" : "S00020114-0"
    } 
]}
```
