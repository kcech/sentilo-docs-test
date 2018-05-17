Retrieve orders
===============

Description
-----------

This action allows you to retrieve the last orders associated with a
sensor or provider. In addition,we can also specify search criteria to
retrieve the orders: filter by a given time period and/or indicate the
maximum number of orders that you want to retrieve.

::

   http://<your_api_server.com>/order/<provider_id>/<sensor_id>?<parameter>=<value>

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

Retorns

.. raw:: html

   </th>

.. raw:: html

   <td>

List of orders destined to sensor or provider listed

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Parameters
----------

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

from

.. raw:: html

   </td>

.. raw:: html

   <td>

Indicates the beginning of the time period for which you want to
retrieve orders.

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

to

.. raw:: html

   </td>

.. raw:: html

   <td>

Indicates the ending of the time period for which you want to retrieve
orders.

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

limit

.. raw:: html

   </td>

.. raw:: html

   <td>

Specifies the maximum number of orders to retrieve.

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

Please, note the following:

-  The maximum number of records returned will be fixed by the platform
   settings. If the parameter passed is higher, the number of records
   returned will be the configured in the platform.
-  If the limit parameter is not set, only one record will be returned.
-  All dates must have the following format: dd/MM/yyyyTHH:mm:ss

Response data
-------------

As mentioned, in addition to `HTTP status
code <../../general_model.html#reply>`__, the requested data is returned
in the body contents as a list of orders.

**The response structure depends on what we are retrieving, orders from
a sensor or a provider.**

Last orders for a sensor
~~~~~~~~~~~~~~~~~~~~~~~~

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

orders

.. raw:: html

   </td>

.. raw:: html

   <td>

List with the last sensor’s order

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

Each order will have the following structure:

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

order

.. raw:: html

   </td>

.. raw:: html

   <td>

Order message recorded at the time the order was published

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

timestamp

.. raw:: html

   </td>

.. raw:: html

   <td>

The time when the order was made (dd/MM/yyyyTHH:mm:ss format)

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

sender

.. raw:: html

   </td>

.. raw:: html

   <td>

Entity identifier that issued the order.

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

time

.. raw:: html

   </td>

.. raw:: html

   <td>

The time when the observation was made in milliseconds

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

Last orders for provider
~~~~~~~~~~~~~~~~~~~~~~~~

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

sensors

.. raw:: html

   </td>

.. raw:: html

   <td>

List with sensors (sensor)

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

Each **(sensor)** will have the following structure:

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

sensor

.. raw:: html

   </td>

.. raw:: html

   <td>

Sensor identifier

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

orders

.. raw:: html

   </td>

.. raw:: html

   <td>

List with the last orders for the sensor

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

Finally, each command **(order)** will have the structure that we have
defined previously.

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

order

.. raw:: html

   </td>

.. raw:: html

   <td>

Order message recorded at the time the order was published

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

timestamp

.. raw:: html

   </td>

.. raw:: html

   <td>

The time when the order was made (dd/MM/yyyyTHH:mm:ss format)

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

sender

.. raw:: html

   </td>

.. raw:: html

   <td>

Entity identifier that issued the order.

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

Examples
--------

Retrieve the last order for a sensor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To retrieve the last order for the sensor with RE0012 identifier
belonging to the provider named rec, we do the following request:

::

   http://<your_api_server.com>/order/rec/RE0012

As response we will get:

.. code:: json

   {"orders":[{
      "order":"Shutdown",
      "timestamp":"21/03/2013T14:25:39",
      "sender":"app_demo_provider"}]
   }

Retrieve the last N orders for a sensor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to retreive more than one order, we can specify the number of
records to retrieve with the following request:

::

   http://<your_api_server.com>/order/rec/RE0012?limit=3

As response we will get:

.. code:: json

   {"orders":
      [{
         "order":"Shutdown",
         "timestamp":"21/03/2013T14:25:39",
         "sender":"app_demo_provider",
         "time":1510570798597
      },{
         "order":"Start",
         "timestamp":"20/03/2013T23:59:59",
         "sender":"app_demo_provider",
         "time":1510570798597
      },{
         "order":"Shutdown",
         "timestamp":"20/03/2013T14:25:39",
         "sender":"app_demo_provider",
         "time":1510570798597
      }
   ]}

Retrieve the last N orders for a sensor between dates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to retrieve orders for a sensor between two dates, we should
do the following request:

::

   http://<your_api_server.com>/order/rec/RE0012?limit=3&from=19/03/2013T00:00:00&to=20/03/2013T23:59:59

As response we will get:

.. code:: json

   {"orders":
      [{
         "order":"Start",
         "timestamp":"20/03/2013T23:59:59",
         "sender":"app_demo_provider",
         "time":1510570798597
      },{
         "order":"Shutdown",
         "timestamp":"20/03/2013T14:25:39",
         "sender":"app_demo_provider",
         "time":1510570798597
      }
   ]}

Retrieve the last orders for a provider
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

All the previous examples are focused on recovering the last command of
a sensor, but the service also allows you to search the latest orders
destined for all the sensors of provider.

In this case, we only specify the provider, and the request will be:

::

   http://<your_api_server.com>/order/rec2

As response we get a list of sensor elements, and each one will contain
its last orders.

.. code:: json

   {"sensors":
      [{
         "sensor":"RE0012",
         "orders":
         [{
            "order":"Shutdown",
            "timestamp":"21/03/2013T14:25:39",
            "sender":"app_demo_provider",
            "time":1510570798597
         }]
      },{
         "sensor":"RE0013",
         "orders":
         [{
            "order":"Shutdown",
            "timestamp":"21/03/2013T14:25:39",
            "sender":"app_demo_provider",
            "time":1510570798597
         }]
      },{
         "sensor":"RE0014",
         "orders":
         [{
            "order":"Shutdown",
            "timestamp":"21/03/2013T14:25:39",
            "sender":"app_demo_provider",
            "time":1510570798597
         }]
      }]
   }
