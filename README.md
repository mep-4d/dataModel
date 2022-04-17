<h1> Building Data Model </h1>

Semantic sense-making, for modern smart buildings. Sponsored by HM Smart Buildings!

This repository is designed to give guidance to the design of smart enabled buildings. MSI's/SI's and control sysem vendors should use it to name devices, points and parameters accross all their systems and application developers should use it to identify the mechanism for binding the the data they need.

While there are many ontological solutions already well established in the building technology sector, most of them are either overly complicated and fail in their core objectives or do not contain the basic elements of building systems data resulting in a high degree of augmentation from their base model.

This toolset aims to simplify the smart enablement journey. Its made up of three core elements which are;

<ol>
  <li><strong>Asset naming tool that enables the unique identification/naming of every physical object within a building</strong></li>
  <li><strong>Point naming tool that enables the naming of every physical/virtual control object within a building</strong></li>
  <li><strong>Data structuring tool that enables us to precisely structure the data from or to the building systems</strong></li>
</ol>

All of these tools have been built into freely accessible web-apps that do all the nitty gritty work for you and links are provided in the relevant sections of this guide. Providing this guide is followed, the smart enablement outcome is a guaranteed success.
  

<h2> Asset Naming </h2>

Each asset shall be named in accordance with the following naming structure:

For main devices;
<strong>SystemRef_SystemItem_ItemID</strong>

<ul>
  <li><strong>SystemRef:</strong> shall be a three character string abbreviation for the system which the asset is a part of i.e. HTG</li>
  <li><strong>SystemItem:</strong> shall be a three character string abbreviation that describes the asset type i.e. PMP</li>
  <li><strong>ItemID:</strong> shall be a four character unique identifier for the asset i.e. 001A</li>
</ul>

This example names a main asset (heating pump) --> HTG_PMP_001A

For sub-devices which are components of assets;
<strong>_SubItem</strong> is appended to the associated main asset name

<ul>
  <li><strong>SubItem:</strong> shall be a string descriptor that represents a component of the asset. The string shall use camel case and be made up of a maximum three words (a,b,c) where (a) is a context string i.e. differential, (b) is a variable descriptor i.e. Pressure, (c) is the component descriptor i.e. Switch</li>
</ul>

This example names a component of the main asset --> HTG_PMP_001A_diffPressSwitch

To make the above asset names truly global <strong>BuildingRef_</strong> is prepended to the asset name where required. BuildingRef is a five character string that uniquely identifies the building i.e. 100LS, so the above asset would become globally identifiable as 100LS_HTG_PMP_001A

<a href="https://mep-4d.github.io/naming.html">HERE IS A TOOL</a>

<h2> Control Object Naming </h2>

Each control point that is a associated with a main device shall be named in accordance with the following naming structure:

<strong>main asset name_Variable_PointType</strong>

<ul>
  <li><strong>main asset name:</strong> shall be the device name as per the previous section i.e. HTG_PMP_001A</li>
  <li><strong>Variable:</strong> shall be a descriptor that represents the physical, measured or controlled dicrete or continuous variable i.e. fault</li>
  <li><strong>PointType:</strong> shall be a descriptor that represents the type of control point and its use i.e. status</li>
</ul>

This example names a control point --> HTG_PMP_001A_fault_status

Each control point that is part of a sub-device shall be named in accordance with the following naming structure:

<strong>SubItem_Variable_PointType</strong>

<ul>
  <li><strong>SubItem:</strong> shall be the name of the sub-device which the point is a child component of i.e. htgValve</li>
  <li><strong>Variable:</strong> shall be a descriptor that represents the physical, measured or controlled variable i.e. position</li>
  <li><strong>PointType:</strong> shall be a descriptor that represents the type of control point and its use i.e. control</li>
</ul>

This example names a control point --> htgValve_position_control

In this example the main device could be a fan coil unit with example name MEP_FCU_1001, and the control point which is a child object of the main device would therefore have the fully qualified name of MEP_FCU_1001_htgValve_position_control
  

<h2> Surfacing Data </h2>

All data surfaced will be JSON objects over MQTT. An MQTT broker will be provided either internal or external to the building network for third party data access. Data will be published from systems to the broker allowing data read, and data will be subscribed to by systems via the broker allowing data write. MQTT topics provide 

For main devices;
<strong>SystemRef_SystemItem_ItemID</strong>
