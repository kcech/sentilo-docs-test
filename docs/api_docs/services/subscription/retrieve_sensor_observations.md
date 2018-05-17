Subscription to sensor data
===========================

## Description

This action allows to subscribe to observation data associated to sensors.

**It's important to note that we only can subscribe to the sensor data over we own read permission.**


```
http://<your_api_server.com>/subscribe/data/<provider_id>/<sensor_id>
```

<table>
	<tbody>
		<tr>
			<th>Format</th>
			<td>json</td>
		</tr>
		<tr>
			<th scope="row">Method</th>
			<td>PUT</td>
		</tr>
		<tr>
			<th scope="row">Permission</th>
			<td>Read</td>
		</tr>
		<tr>
			<th scope="row">Returns</th>
			<td>No additional data returned</td>
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
			<td>endpoint</td>
			<td>URL where the platform will send a HTTP request with the observation data</td>
			<td>No</td>
		</tr>
		<tr>
			<td>secretCallbackKey</td>
			<td>Secret key for callbacks</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>retries</td>
			<td>Maximum number of retries</td>
			<td>Yes</td>
		</tr>
		<tr>
			<td>retries_delay</td>
			<td>Delay parameter in minutes. Delays are spaced exponentially according to following equation:<br>
				<br>delay (N) = delay * 2^(N-1)<br>
				<br>Where N is the current entry turn. More detailed explanation follows.
			</td>
			<td>Yes</td>
		</tr>
	</tbody>
</table>


**Retries**

In case the remote endpoint is down or does not respond with an success HTTP 2xx code, Sentilo can try to resend the data later. In order to overcome major number of remote outages, Sentilo sends the data in delay times that are exponential according to equation:

```
delay (N) = delay * 2^(N-1)
```

For example, if we have a subscription configured with 5 retries and 10 minutes, first retry would occur at 10 minutes, the second 20 minutes after the first, the third 40 minutes after the second, etc up to the fifth retry.

The total time used for the 5 retries would occur in 10+20+40+80+160=310 minutes after the first failed intent.

## Response data

This action does not return additional data beyond the [HTTP status code](../../general_model#reply).

## Examples

### Request to subscribe to a sensor's data

If we want to susbcribe to the sensor's data with <em>RE0012</em> identifier of the provider named <em>rec</em>, the request will be:

```
http://<your_api_server.com>/subscribe/data/rec/RE0012
```

and the body message:

```
{"endpoint":"http://<your_endpoint_notification_server.com>/resource"}
```


### Request to subscribe to provider's data

If we want to subscribe to all the sensors belonging to a provider, the request will be:

```
http://<your_api_server.com>/subscribe/data/rec
```

and the body message:

```json
{"endpoint":"http://<your_endpoint_notification_server.com>"}
```
