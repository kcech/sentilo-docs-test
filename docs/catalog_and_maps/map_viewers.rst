Map Viewers
-----------

In the publicly accessible section of the Catalog, Sentilo offers 2 different map viewers that display
data in real-time, as they arrive to the system.

Both viewers are accessible from the *Explore* item
at the top menu bar (*Universal viewer* and *Route viewer*).


Universal viewer
~~~~~~~~~~~~~~~~

Components map
^^^^^^^^^^^^^^

The catalog provides a default map, based on Google Maps, which shows
all the public components registered at the platform. If the user is
logged as administrator, all the private components will be displayed as
well.

|universal_viewer_170_001.jpg|

On this page, you can filter the components to show by selecting a
*component type* from the top left select.

|universal_viewer_170_002.jpg|

Depending on the zoom level, the map will display the elements as
individuals POIs or grouped in clusters, showing the number of
components in each group.

|universal_viewer_170_003.jpg|

Component details
^^^^^^^^^^^^^^^^^

Sensors list
''''''''''''

When you select a component, a popup window is opened above the map and
displays the list of sensors related to it with the last activity for
each one of them (as noted above, the private sensors will be displayed
only for logged users):

|universal_viewer_170_004.jpg|

Sensors last activity view
''''''''''''''''''''''''''

If you click into the content area of the popup window, a new page is
open displaying some basic details about the component, and a
time-series graph with the last activity of each of its sensors:

|universal_viewer_170_005.jpg|

.. _navigate-the-last-data-chart-1:

Navigate the last data chart

You can navigate along the dates of the graph by using the buttons
located in the lower right corner of it:

|chart_controls.png|

-  **left arrow**: navigate to the past (only if there are older data)
-  **reload data (center button)**: reload last data / reset chart data
-  **right arrow**: navigate to the future (only if you have navigated
   or gone into the past before)

Default configuration
^^^^^^^^^^^^^^^^^^^^^

The initial map settings are configured in the file:

::

   sentilo-catalog-web/src/main/webapp/WEB-INF/jsp/common/include_script_maps.jsp

and includes settings such as the default map center, the default zoom,
….

.. code:: javascript

    // the initial map center (Barcelona city)
    var defaultMapCenter = [41.5667, 2.0167];
    var defaultZoomLevel = 14;
	var defaultInputLocationZoomLevel = 17;
	// the maximum zoom level beyond which pois are not grouped into clusters
	var defaultMaxZoomCluster = 13;
    // flag for control if routes must be displayed or no on the current map
    var showRoutes = false;
    // flag for control if only components that fit into bounds's map must be searched on the server
    var filterByBounds = true;
   ...

You could change these configuration parameters or customize the look
and feel to meet your requirements, but instead of overwrite the
existing values you could add the new values to the file:

::

   sentilo-catalog-web/src/main/webapp/WEB-INF/jsp/common/include_script_maps_config.jsp

For example, add the following line to the *include_script_maps_config*
file if you would change the initial map center to London:

::

   var defaultMapCenter [ 51.4991257, -0.11325074];

When Catalog starts, properties in this file overwrites existing ones
having the same name in the file *include_script_maps.jsp*

Displaying complex data
^^^^^^^^^^^^^^^^^^^^^^^

In some cases, you may want to inform **complex data** as an observation
on Sentilo, such like a large json object. For these cases, Sentilo will
detect that the text is a json object and then it will be shown to you
as a prettyfied json value:

|complex_data_170_001.jpg|

You can expand or compress the prettified json with the bottom buttons
under the status field,

Route viewer
~~~~~~~~~~~~

As the name suggest, the route viewer is a specific map that shows the
routes followed by the mobile components (keep in mind that only the
last 20 points are displayed for each route):

|route_viewer_170_001.jpg|

The same features described previously apply on this map and its markers
(popup window, … ), but with the particularity that if you click over a
*route point* then the popup window displays sensor activity related to
the time instant in which component was at that location.

|route_viewer_170_002.jpg|


.. |universal_viewer_170_001.jpg| image:: ../_static/images/catalog_and_maps/universal_viewer_170_001.jpg
.. |universal_viewer_170_002.jpg| image:: ../_static/images/catalog_and_maps/universal_viewer_170_002.jpg
.. |universal_viewer_170_003.jpg| image:: ../_static/images/catalog_and_maps/universal_viewer_170_003.jpg
.. |universal_viewer_170_004.jpg| image:: ../_static/images/catalog_and_maps/universal_viewer_170_004.jpg
.. |universal_viewer_170_005.jpg| image:: ../_static/images/catalog_and_maps/universal_viewer_170_005.jpg
.. |chart_controls.png| image:: ../_static/images/catalog_and_maps/chart_controls.png
.. |complex_data_170_001.jpg| image:: ../_static/images/catalog_and_maps/complex_data_170_001.jpg
.. |route_viewer_170_001.jpg| image:: ../_static/images/catalog_and_maps/route_viewer_170_001.jpg
.. |route_viewer_170_002.jpg| image:: ../_static/images/catalog_and_maps/route_viewer_170_002.jpg

