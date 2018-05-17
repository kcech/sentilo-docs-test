Read observations from provider’s sensors
=========================================

Description
-----------

This action allows to retrieve the latest observations of the sensors of
a provider. In addition, the service can also specify search criterias
to retrieve observations: filter by a given time period and / or to
indicate the maximum number of observations to be recovered.

::

    http://<your_api_server.com>/data/<provider_id>?<parameter>=<value>

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

Reading

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Return

.. raw:: html

   </th>

.. raw:: html

   <td>

List with the observations from provider’s sensors

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

**Because the number of sensors from a supplier can be very high, and
therefore the amount of information returned can be very large, be
careful using this operations due to performance reasons.**

Parameteres
-----------

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
retrieve the observations.

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

Indicates the end of the time period for which you want to retrieve the
observations.

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

Specifies the maximum number of observations for each sensor to recover.

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

Please note the following:

-  The maximum number of records returned will be fixed by the platform
   settings. If the parameter passed is higher, the number of records
   returned will be equalsa to the maximum value configured in the
   platform.
-  If the limit parameter is not set, only one record will be returned.
-  All dates must have the following format: dd/MM/yyyyTHH:mm:ss

Response data
-------------

In addition to the `HTTP status
code <../../general_model#reply>`__, the observation data is
returned in the body contents as a list of observations:

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

List of sensors (sensor) for the observations that have been retrieved

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

Each sensor has the following structure:

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

observations

.. raw:: html

   </td>

.. raw:: html

   <td>

List of the latest sensor observations

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

Finally, each observation (observation) has the following structure:

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

Opional

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

value

.. raw:: html

   </td>

.. raw:: html

   <td>

Observation value

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

The time at which the observation was made (dd/MM/yyyyTHH:mm:ss format)

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

   <tr>

.. raw:: html

   <td>

location

.. raw:: html

   </td>

.. raw:: html

   <td>

Geolocation coordinates in which the sensor was recorded observation

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

Request to retrieve the latest observations from a provider after a given date
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to retrieve the latest observations of the sensors associated
with the provider named rec from a given date we should make the
following request:

::

    http://<your_api_server.com>/data/rec?from=10/09/2012T10:00:00

As response we will receive:

.. code:: json

   {"sensors":[
      {
         "sensor":"RE0012",
         "observations":
         [{
            "value":"1",
            "timestamp":"10/09/2012T10:05:00",
            "time":1510561800000
         },{
            "value":"1.2",
            "timestamp":"10/09/2012T07:05:00",
            "time":1510561800000
         }]
      },{
         "sensor":"RE0013",
         "observations":
         [{
            "value":"24",
            "timestamp":"10/09/2012T10:06:10",
            "time":1510561800000
         }]
      }
   ]}

Request to retrieve the latest observations from rec provider
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you only want to retrieve the last observation of the RE0012 sensor,
the request to do is:

::

    http://<your_api_server.com>/data/rec

As response we will receive:

.. code:: json

   {"sensors":[
      {
         "sensor":"RE0012",
         "observations":
         [{
            "value":"1",
            "timestamp":"10/09/2012T10:05:00",
            "time":1510561800000
         }]
      },{
         "sensor":"RE0013",
         "observations":
         [{
            "value":"24",
            "timestamp":"10/09/2012T10:06:10",
            "time":1510561800000
         }]
      }
   ]}
