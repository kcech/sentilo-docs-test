Retrieve sensor observations
============================

Description
-----------

This action allows you to retrieve the latest observations of a sensor.
In addition, the service can also permits to specify search criteria to
retrieve observations: filter by a given time period and / or to
indicate the maximum number of observations to be retrieved.

::

    http://<your_api_server.com>/data/<provider_id>/<sensor_id>?<parameter>=<value>

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

Returns

.. raw:: html

   </th>

.. raw:: html

   <td>

Observations list

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
retrieve observations

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

Indicates the end of the time period for which you want to retrieve
observations

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

Indicates the number of observations to retrieve

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
   returned will be equals to the maximum value configured in the
   platform.
-  If the limit parameter is not set, only one observation will be
   returned.
-  All dates must have the following format: dd/MM/yyyyTHH:mm:ssZ with Z
   as optional (and with default value UTC)

Response data
-------------

As mentioned, in addition to `HTTP status
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

observations

.. raw:: html

   </td>

.. raw:: html

   <td>

List the observations (observation)

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

Each observation has the following structure:

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

The time when the observation was made based on UTC (dd/MM/yyyyTHH:mm:ss
format)

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

Request to retrieve the latest observations of a sensor based on a date
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following request shows an example in which a call is made to
retrieve the last 20 observations of the sensor with RE0012 identifier
of the provider named rec which have been registered from 10/01/2013.

::

    http://<your_api_server.com>/data/rec/RE0012?limit=20&from=10/01/2013T10:00:00

As response we receive:

.. code:: json

   {"observations":[
      {
         "value":"28.61132406103821",
         "timestamp":"13/11/2017T09:00:00",
         "time":1510563600000

      },{
         "value":"20.795568440010314",
         "timestamp":"13/11/2017T08:30:00",
         "time":1510561800000
      },{
         "value":"91.01094902496055",
         "timestamp":"13/11/2017T08:30:00",
         "time":1510561800000
      },{
         "value":"62.22915604583776",
         "timestamp":"11/01/2013T08:16:38",
         "time":1510561800000
      },{
         "value":"99.96065618303348",
         "timestamp":"11/01/2013T07:16:38",
         "time":1510561800000
      },{
         "value":"94.95685904585568",
         "timestamp":"11/01/2013T06:16:38",
         "time":1510561800000
      },{
         "value":"51.26506022800391",
         "timestamp":"11/01/2013T05:16:38",
         "time":1510561800000
      },{
         "value":"21.43303677241535",
         "timestamp":"11/01/2013T04:16:38",
         "time":1510561800000
      },{
         "value":"55.6601921120059",
         "timestamp":"11/01/2013T03:16:38",
         "time":1510561800000
      },{
         "value":"56.692086830598996",
         "timestamp":"11/01/2013T02:16:38",
         "time":1510561800000
      }
   ]}

Request to retrieve the last observation of a sensor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you only want to retrieve the last observation of the RE0012 sensor,
the request to do is:

::

    http://<your_api_server.com>/data/rec/RE0012

As response we will receive:

.. code:: json

   {"observations":[{
      "value":"11.5",
      "timestamp":"18/09/2012T17:20:00",
      "time":1510561800000}
   ]}
