Retrieve active subscriptions
=============================

Description
-----------

This action allows to retrieve the list of all our active subcriptions.
Additionally, we can retrieve only subscriptions from a specific type.

::

   http://<your_api_server.com>/subscribe/<event_type>

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Format

.. raw:: html

   </th>

.. raw:: html

   <td>

json

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Method

.. raw:: html

   </th>

.. raw:: html

   <td>

GET

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Permission

.. raw:: html

   </th>

.. raw:: html

   <td>

Read

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Returns

.. raw:: html

   </th>

.. raw:: html

   <td>

Active subscriptions

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

**** is optional and allows to filter the subscription by type.

Parameters
----------

No additional parameters can be used.

Response data
-------------

This action, additionally to the `HTTP status
code <../../general_model#reply>`__, will return a list of our
active subscriptions:

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Key

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   <th>

Optional

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

subscriptions

.. raw:: html

   </td>

.. raw:: html

   <td>

List with all our active subscriptions

.. raw:: html

   </td>

.. raw:: html

   <td>

No

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Each **subscription** element contains this set of attributes:

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Key

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   <th>

Optional

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

endpoint

.. raw:: html

   </td>

.. raw:: html

   <td>

URL defined in the subscription

.. raw:: html

   </td>

.. raw:: html

   <td>

No

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

type

.. raw:: html

   </td>

.. raw:: html

   <td>

Event type related to the subscription(data, order o alarm)

.. raw:: html

   </td>

.. raw:: html

   <td>

No

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

provider

.. raw:: html

   </td>

.. raw:: html

   <td>

In case the type is data or order this attribute contains the provider
identifier

.. raw:: html

   </td>

.. raw:: html

   <td>

Yes

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

sensor

.. raw:: html

   </td>

.. raw:: html

   <td>

In case the type is data or order this attribute contains the sensor
identifier

.. raw:: html

   </td>

.. raw:: html

   <td>

Yes

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

alarm

.. raw:: html

   </td>

.. raw:: html

   <td>

In case the type is alarm this attribute contains the alert identifier

.. raw:: html

   </td>

.. raw:: html

   <td>

Yes

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Examples
--------

Request to retrieve all active subscriptions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

   http://<your_api_server.com>/subscribe

As response we will obtain:

.. code:: json

   {
      "subscriptions":
      [{
         "endpoint":"http://<your_endpoint_notification_server.com>",
         "type":"ALARM",
         "alert":"alerta1"
      },{
         "endpoint":"http://<your_endpoint_notification_server.com>",
         "type":"DATA",
         "provider":"app_demo_provider",
         "sensor":"appdemo_sensor5_test"
      },{
         "endpoint":"http://<your_endpoint_notification_server.com>",
         "type":"DATA",
         "provider":"app_demo_provider",
         "sensor":"appdemo_sensor_test"
      },{
         "endpoint":"http://<your_endpoint_notification_server.com>",
         "type":"ALARM","alert":"11"
      }]
   }

Request to retrieve active subscriptions for a specific type
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to retrieve only the subscriptions to a specific event type:

::

   http://<your_api_server.com>/subscribe/alarm

As response we will obtain:

.. code:: json

   {
      "subscriptions":
      [{
         "endpoint":"http://<your_endpoint_notification_server.com>",
         "type":"ALARM",
         "alert":"alert1"
      },{
         "endpoint":"http://<your_endpoint_notification_server.com>",
         "type":"ALARM",
         "alert":"alert11"
      }]
   }
