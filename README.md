<h1> Building Data Model </h1>

Semantic sense-making, for modern smart buildings. Sponsored by HM Smart Buildings!

This repository is designed to give guidance to the design of smart enabled buildings. MSI's/SI's and control sysem vendors should use it to name devices, points and parameters accross all their systems and application developers should use it to identify the mechanism for binding the the data they need.

While there are many emerging models and solutions already well established in the building technology sector, most of them are either overly complicated and fail in their core objectives or do not contain the basic elements of building systems data resulting in a high degree of augmentation from the base model.

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

<ol>
  <li><strong>SystemRef:</strong> shall be a three character string abbreviation for the system which the asset is a part of</li>
  <li><strong>SystemItem:</strong> shall be a three character string abbreviation that describes the asset type</li>
  <li><strong>ItemID:</strong> shall be a four character unique identifier for the asset</li>
</ol>

For devices which are sub-components of assets;
<strong>_SubItem</strong> is appended to the associated main asset name

