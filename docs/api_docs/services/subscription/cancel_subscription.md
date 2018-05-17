Cancel subscriptions
====================

## Description

This action allows to cancel any or a set of our active subscriptions.

```
http://<your_api_server.com>/subscribe/<event_type>/<resource_id>
```

<table>
	<tbody>
		<tr>
			<th>Format</th>
			<td>json</td>
		</tr>
		<tr>
			<th>Method</th>
			<td>DELETE</td>
		</tr>
		<tr>
			<th>Permission</th>
			<td>Write</td>
		</tr>
		<tr>
			<th>Returns</th>
			<td>No additional data returned</td>
		</tr>
	</tbody>
</table>

**<event_type>** and **<resource_id>** are optional and allow to filter the subscription to cancel by event type or related resource.

## Parameters

No additional data can be sent.

## Response data

This action does not return any additional data beyond the [HTTP status code](../../general_model.html#reply).

## Examples

### Request to cancel subscriptions

If we want to cancel all our active subscriptions, the request will be:

```
http://<your_api_server.com>/subscribe
```

### Request to cancel subscriptions for a specific event type

If we want to cancel all our active subscriptions of a specific event type like <em>order</em>, the request will be:

```
http://<your_api_server.com>/subscribe/order
```

### Request to cancel subscriptions for a specific resource

If we want to cancel all our active data subscriptions of a specific sensor like <em>RE0012</em> belonging to the <em>rec</em> provider, the request will be:

```
http://<your_api_server.com>/subscribe/data/rec/RE0012
```
