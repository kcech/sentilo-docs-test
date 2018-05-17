Retrieve providers / sensors list
=================================

Description
-----------

This resource returns a list of providers and sensors for which you have
at least read permission. Sensors that are in the offline state won’t be
listed. In addition, the service provides optional filtering by sensor
type, component type and component name.

::

    http://<your_api_server.com>/catalog

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

List of providers, with their sensors, on which we has at least read
permission

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

type

.. raw:: html

   </td>

.. raw:: html

   <td>

Sensor’s type filter

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

component

.. raw:: html

   </td>

.. raw:: html

   <td>

Component name filter

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

componentType

.. raw:: html

   </td>

.. raw:: html

   <td>

Component’s type filter

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

Response data
-------------

As mentioned, this action, in addition to the `HTTP status
code <../../general_model.html#reply>`__, returns the list of providers
for wich we have at least read permission.

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

providers

.. raw:: html

   </td>

.. raw:: html

   <td>

Providers list (provider) with at least read permission

.. raw:: html

   </td>

.. raw:: html

   <td>

Not

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Each provider will have the following structure:

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

provider

.. raw:: html

   </td>

.. raw:: html

   <td>

Provider ID

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

permission

.. raw:: html

   </td>

.. raw:: html

   <td>

Indicates whether it readable (R) or write (W) on the provider

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

sensors

.. raw:: html

   </td>

.. raw:: html

   <td>

Provider list of sensors (sensor)

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

Each list element **(sensor)** will have the following structure.

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

description

.. raw:: html

   </td>

.. raw:: html

   <td>

sensor description

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

dataType

.. raw:: html

   </td>

.. raw:: html

   <td>

Data sensor type (NUMBER, BOOLEAN or TEXT)

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

Location where de sensor is

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

type

.. raw:: html

   </td>

.. raw:: html

   <td>

Sensor type

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

unit

.. raw:: html

   </td>

.. raw:: html

   <td>

Unities in the sensor data coming

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

timeZone

.. raw:: html

   </td>

.. raw:: html

   <td>

Sensor’s timezone

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

publicAccess

.. raw:: html

   </td>

.. raw:: html

   <td>

Visualization check for the public area

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

component

.. raw:: html

   </td>

.. raw:: html

   <td>

Component is associated the sensor

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

componentType

.. raw:: html

   </td>

.. raw:: html

   <td>

Component type

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

componentDesc

.. raw:: html

   </td>

.. raw:: html

   <td>

Component description

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

componentPublicAccess

.. raw:: html

   </td>

.. raw:: html

   <td>

Visualization check for the public area

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

additionalInfo

.. raw:: html

   </td>

.. raw:: html

   <td>

Additional params related to the sensor

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

technicalDetails

.. raw:: html

   </td>

.. raw:: html

   <td>

Technical params related to the sensor

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

componentTechnicalDetails

.. raw:: html

   </td>

.. raw:: html

   <td>

Technical params related to the component

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

Request to retrieve all Providers / Sensors
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

    http://<your_api_server.com>/catalog

in the response we will receive

.. code:: json

   {
       "providers": [{
           "provider": "A",
           "permission": "WRITE",
           "sensors": [{
               "sensor": "MAR_01_00_SN001_1010",
               "description": "Sound Sensor MODI 001",
               "dataType": "NUMBER",
               "type": "noise",
               "unit": "dBa",
               "component": "MAR_01_00_SN001_1010",
               "componentType": "generic",
               "timeZone": "CET"
           }]
       }, {
           "provider": "C",
           "permission": "READ",
           "sensors": [{
               "sensor": "MAR_02_20_PM001_1010",
               "description": "PM10 Sensor IMI 001",
               "dataType": "NUMBER",
               "type": "air_quality_pm10",
               "unit": "ug/m3",
               "component": "air_quality",
               "componentType": "generic"
           }, {
               "sensor": "MAR_02_20_PM001_1012",
               "description": "PM10 Sensor IMI 002",
               "dataType": "NUMBER",
               "type": "air_quality_pm10",
               "unit": "ug/m3",
               "component": "air_quality",
               "componentType": "generic",
               "additionalInfo": {
                   "supportMail": "support@imi.com"
               },
               "technicalDetails": {
                   "producer": "xxxx",
                   "model": "x-1",
                   "serialNumber": "9999",
                   "energy": "220VAC"
               },
               "componentTechnicalDetails": {
                   "producer": "XXXX",
                   "model": "X-1",
                   "serialNumber": "9999",
                   "macAddress": "00:17:4F:08:5F:61",
                   "energy": "12_24_VDC",
                   "connectivity": "WIFI"
               }
           }]
       }]
   }

Request to recover all the sensors in the catalog filtered by type
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The request in this case is very similar to the previous one adding the
type parameter:

::

    http://<your_api_server.com>/catalog?type=air_quality_pm10

In this case as a response we will receive:

.. code:: json

   {"providers":[
       {
        "provider":"C","permission":"READ",
        "sensors":
        [{
          "sensor":"MAR_02_20_PM001_1010",
          "description":"PM10 Sensor IMI 001",
          "dataType":"NUMBER",
          "type":"air_quality_pm10",
          "unit":"ug/m3",
          "component":"air_quality",
          "componentType":"generic"
         },{
          "sensor":"MAR_02_20_PM001_1012",
          "description":"PM10 Sensor IMI 002",
          "dataType":"NUMBER",
          "type":"air_quality_pm10",
          "unit":"ug/m3",
          "component":"air_quality",
          "componentType":"generic",
          "additionalInfo":{"field1":"value1","field2":"value2"}
         }
        ]
       }
   ]}

Other examples
~~~~~~~~~~~~~~

::

   http://<your_api_server.com>/catalog?component=comp_demo&type=air_quality_pm10

::

   http://<your_api_server.com>/catalog?componentType=air_quality&type=air_quality_pm10
