Update Alerts
=============

Description
-----------

This action allows to update one or more alerts in the catalog.

::

   http://<your_api_server.com>/catalog/alert/<entity_id>

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Formats

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

Returns

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

The internal alerts should be updated through the catalog console or by
the API, but only using the catalog token.

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

alerts

.. raw:: html

   </td>

.. raw:: html

   <td>

Alerts list (alert) to update

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

Every alert element has the following structure:

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

id

.. raw:: html

   </td>

.. raw:: html

   <td>

Alert identifier to update

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

name

.. raw:: html

   </td>

.. raw:: html

   <td>

New alert name

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

description

.. raw:: html

   </td>

.. raw:: html

   <td>

New alert description

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

Alert type

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

trigger

.. raw:: html

   </td>

.. raw:: html

   <td>

New trigger type

.. raw:: html

   </td>

.. raw:: html

   <td>

Mandatory for internal, not applies for externals

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

expression

.. raw:: html

   </td>

.. raw:: html

   <td>

New expression to evaluate with the trigger

.. raw:: html

   </td>

.. raw:: html

   <td>

Mandatory for internal, not applies for externals

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Please, note the following observations:

-  The list of trigger’s types and expressions are defined in: `Trigger
   types <../alert/alert.html#InternalTriggerTypes>`__.
-  The possible values ​​for the alert type are: INTERNAL or EXTERNAL.

Response data
-------------

This action doesn’t return additional data beyond the `HTTP status
code <../../general_model.html#reply>`__.

Examples
--------

Update one external alert
~~~~~~~~~~~~~~~~~~~~~~~~~

If rec entity wants to update the external alert with REC_ALERT_001
identifier to modify its name, the request to do will be:

::

   http://<your_api_server.com>/catalog/alert/rec

and in the body message:

.. code:: json

   {"alerts":[
      {"id":"REC_ALERT_001",
       "name":"REC_EXTERNAL_ALERT_001",
       "type":"EXTERNAL"
      }
   ]}

This request will update the external alert with REC_ALERT_001
identifier updating its name to REC_EXTERNAL_ALERT_001.

Remember, the external alerts are defined by third party
entities(providers or applications), which will be the responsibles of
calculating their logic and throw the related alarms when applies.

Update one internal alert
~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to update the internal alert with REC_GT_45_ALERT_001
identifier to change its description, the request will be:

::

   http://<your_api_server.com>/catalog/alert/rec

and in the body message:

.. code:: json

   {"alerts":[
      {"id":"REC_GT_45_ALERT_001",    
       "type":"INTERNAL",
       "description":"New description"
      }
   ]}

This request will update the description of the internal alert with
REC_GT_45_ALERT_001 identifier changing its value to “New description”.

**This operation must be done using the catalog token.**
