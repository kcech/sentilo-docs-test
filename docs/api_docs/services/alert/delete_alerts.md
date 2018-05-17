Remove alerts
=============

## Description

This action allows to delete alerts from the catalog. 
The internal alerts can only be deleted using the Catalog's token or through the Catalog console.
The external alerts can only be removed using the entity's owner token.

```
http://<your_api_server.com>/catalog/alert/<entity_id>
```

Remember, the <em>entity_id</em> can be also an Application or a Provider too.

<table>
	<tbody>
		<tr>
			<th>Format</th>
			<td>json</td>
		</tr>
		<tr>
			<th>Method</th>
			<td>DELETE, PUT</td>
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

Note that this action can be invoked using two HTTP methods: <em>PUT</em> and <em>DELETE</em>.

* DELETE will be used if we want to delete all of our alerts. It cannot contain any body content.
* PUT will be used when we want to delete a group of alerts. We should add the parameter <em>method</em> with <em>delete</em> value to the request . In this case, the alerts to delete should be specified in the body message.

## Parameters

The structure of input message if we want to delete a group is:

<table>
	<tbody>
		<tr>
			<th>Key</th>
			<th>Description</th>
			<th>Optional</th>
		</tr>
		<tr>
			<td>alertsIds</td>
			<td>Array of the alerts identifiers to delete</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>

Each element of the list corresponds to an identifier to an alert to delete.

## Response data

This action does not return additional data beyond the [HTTP status code](../../general_model#reply).

## Examples

### Request to delete all alerts

If the entity <em>rec</em> wants to delete all its alerts, the request will be:

```
DELETE http://<your_api_server.com>/catalog/alert/rec
```

This action will delete all the external alerts belonging to entity <em>rec</em>. 
Be careful, if this request is done using the catalog token, it will remove all the internal alerts!.

### Request to delete a set of alerts

If the entity <em>rec</em> only wants to delete a set of alerts, the request will be:

```
PUT http://<your_api_server.com>/catalog/alert/rec?method=delete
```

and in the body message:

```
{"alertsIds":["REC-ALERT-01","REC-ALERT-02"]}
```
