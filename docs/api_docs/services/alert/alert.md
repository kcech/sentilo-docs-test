Alert
=====

## Description

The alert service provides methods to record, edit or retrieve alerts definition.

All requests for this service will have the following format: 

```
http://<your_api_server.com>/catalog/alert/<entity_id>
```

where <em>entity_id</em> is optional and should be included depending on the operation. <em>entity_id</em> can be an Application or a Provider. 

There are two alert types: **internal** and **external**. 

**The internal alerts are related to specific sensors and its logic is defined using basic math rules or configuring an inactivity time**. They should be defined through the catalog console or by the  API, but only using the catalog token.
 
The related alarms are triggered always by the Sentilo platform when the alert logic occurs.

**The external alerts are defined by third party entities**, which will be the responsibles of calculating their logic and throw the related alarms when applies.

For both cases, the Sentilo platform is responsible of publishing the alarm for all entities subscribed to the related alert.

## Actions

The available actions for this service are:
* [Adding alerts](./create_alerts)
* [Update alerts](./update_alerts)
* [Retrieve list of authorized alerts](./retrieve_authorized_alerts)
* [Remove alerts](./delete_alerts)

## <a name="InternalTriggerTypes"></a>Internal trigger types

The list of trigger types accepted by Sentilo (and their associated expressions) are:

<table>
	<tbody>
		<tr>
			<th>Id</th>
			<th>Description</th>
			<th>Expression value</th>
		</tr>
		<tr>
			<th>GT</th>
			<td>Greater than <em>&lt;expression&gt;</em></td>
			<td>Any numerical value</td>
		</tr>
		<tr>
			<th>GTE</th>
			<td>Greater than or equal <em>&lt;expression&gt;</em></td>
			<td>Any numerical value</td>
		</tr>
		<tr>
			<th>LT</th>
			<td>Less than <em>&lt;expression&gt;</em></td>
			<td>Any numerical value</td>
		</tr>
		<tr>
			<th>LTE</th>
			<td>Less than or equal <em>&lt;expression&gt;</em></td>
			<td>Any numerical value</td>
		</tr>
		<tr>
			<th>EQ</th>
			<td>Equal <em>&lt;expression&gt;</em></td>
			<td>Any value</td>
		</tr>
		<tr>
			<th>CHANGE</th>
			<td>Any change</td>
			<td>Not apply here</td>
		</tr>
		<tr>
			<th>CHANGE_DELTA</th>
			<td>Any variation greater to delta <em>&lt;expression&gt;</em></td>
			<td>Any numerical value between 0 and 100</td>
		</tr>
		<tr>
			<th>FROZEN</th>
			<td>No data received in <em>&lt;expression&gt;</em>minutes
			</td>
			<td>Any numerical value</td>
		</tr>
	</tbody>
</table>

The trigger types only apply for the internal alerts.
