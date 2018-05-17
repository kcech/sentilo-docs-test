Publishing observations from different sensors
==============================================

Description
-----------

This action allows a provider to publish details of the observations
made ​​by more than one sensor in a single message.

::

    http://<your_api_server.com>/data/<provider_id>

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

PUT

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

Writing

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

No output data

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

sensors

.. raw:: html

   </td>

.. raw:: html

   <td>

List of sensors (sensor) for which we publish at least one observation

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

Each sensor will have the following structure:

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

Observations list (observation) to publish

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

Geolocation coordinates in which the sensor observations are obtained
(latitude longitude format)

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

Each observation will have the structure described on page `Publish
observations of a sensor <./publish_sensor_data.html>`__:

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

Date and time at which the observation was made (dd/MM/yyyyTHH:mm:ssZ
format)

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

location

.. raw:: html

   </td>

.. raw:: html

   <td>

Geolocation coordinates in which the sensor has achieved this
observation (latitude longitude format).

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

Response Data
-------------

This action does not return additional data beyond the `HTTP status
code <../../general_model.html#reply>`__.

Examples
--------

Request to send multiple observations of several sensors setting a LTC TimeZone
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to send the observations of a set of sensors for the provider
named rec, setting timeZone to CET, the request to do is:

::

    http://<your_api_server.com>/data/rec

and in the body message:

.. code:: json

   {"sensors":[
      {
       "sensor":"RE0012",
       "observations":[
         {"value":"1.1"},
         {"value":"1.2",
          "timestamp":"17/09/2012T12:34:45CET"},
         {"value":"1.3",
          "timestamp":"17/09/2012T10:34:45CET"}
       ]
      },{
       "sensor":"RE0013",
       "location":"41.12345 2.12354",
       "observations":[
         {"value":"2.1"},
         {"value":"2.2",
          "timestamp":"16/09/2012T15:43:21CET"},
         {"value":"2.3",
          "timestamp":"16/09/2012T10:43:21CET"}
       ]
      }
   ]}
