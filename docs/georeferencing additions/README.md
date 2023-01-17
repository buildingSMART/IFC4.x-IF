## Changes in documentation

### 1. IfcCRS
Edit the description of **Name** and **Description** attributes of _IfcCoordinateReferenceSystem_

<img src="./IfcCRS_1.png" width="800"/>

1. Name: make only one NOTE saying:
 > When the CRS is described using EPSG, the Name shall be taken from ...
 > When the CRS is described using WKT, the CRS shall be further specified using the _IfcWellKnownText_ entity

2. Description: just remove the note and example

### 2. IfcProjectedCRS
Edit entity definition for _IfcProjectedCRS_, saying that 

> IfcProjectedCRS can also be used to represent a Compound CS, which combines the coordinate of two other coordinate systems. For example, a compound 3D coordinate system could be made up of a horizontal coordinate system and a vertical coordinate system

Examples:
- EPSG:9286 (ETRS89 + NAP height), is the combination of a Geographic CS (ETRS89) and a Vertical CS (NAP height)
- EPSG:9306 (HS2 Survey Grid + HS2-VRF height), is the combination of a Projected CS (HS2 Survey Grid), and a Vertical CS (HS2-VRF height)

These examples, referenced using their EPSG codes, have also a description using OGC WKT literals.

### 3. IfcCoordinateOperation
Edit the entity definition of _IfcCoordinateOperation_, to explain the different scenarios in which this entity (its subtypes) can be used.

---
_IfcCoordinateOperation_ is an abstract supertype to handle any operation (transformation or conversion) between two coordinate reference systems.

A common coordinate operation is the one between the local engineering coordinate system of a construction project and any map or other coordinate reference system.

In this case, _IfcCoordinateOperation_ is used to connect a _IfcGeometricRepresentationContext_ (the base reference system of your virtual model) to a _IfcCoordinateReferenceSystem_ (a coordinate system which is related to the real world by a datum/a). To do this, _IfcCoordinateOperation_ uses its two attributes: SourceCRS and TargetCRS.

The SourceCRS is the _IfcGeometricRepresentationContext_
The TargetCRS can be a:
-	_IfcProjectedCRS_, if you have defined easting, northing and orthogonal height
-	_IfcGeographicCRS_, if you have defined latitude, longitude and ellipsoidal height

{ .extDef}
> NOTE  in IFC, _IfcProjectedCRS_ can also be used to represent a Compound CS. See _IfcProjectedCRS_ for further details.


There are 3 types of _IfcCoordinateOperation_. The one to be used depends on the specific data exchange scenario.

- _IfcMapConversion_ and _IfcMapConversionScaled_ involve a transformation.
They are coordinate operations that tells that the local engineering coordinate system of the model (which is a topocentric one) is "put in place" in a ProjectedCRS.
They can use one unique scale value for x,y,z (_IfcMapConversion_) or three different scale values for x,y,z (_IfcMapConversionScaled_) - example of a Helmert transformation.

- _IfcRigidOperation_ involves a translation.
It is a coordinate operation that tells that the whole model is translated in the same way the ProjectedCRS is translated - continuously and in all directions.

<img src="./CoordinateOperation-scenarios.jpg" width="1000"/>

Example scenarios:

**Scenario 1: buildings on map**
- Data in the IFC file is in **local engineering coordinates and ground meters**

- To be able to place and visualise the model on a projected map of the earth, the receiving application shall: use the parameters of _IfcMapConversion_ (or _IfcMapConversionScaled_) and _IfcProjectedCRS_ for the transformation of data (translate, rotate and scale), from the local engineering coordinate system to the projected CRS.

**Scenario 2: linear infrastructures on map**
- Data in the IFC file is in **map coordinates and map meters**
- To be able to place and visualise the model on a projected map of the earth, the receiving application shall: use the parameters of _IfcRigidOperation_ and _IfcProjectedCRS_ for the translation of data.
  - **without translation**: the origin of the base reference system of your virtual model (set by _IfcGeometricRepresentationContext_) coincide with the origin of the _IfcProjectedCRS_
  - **with translation**: the origin of the base reference system of your virtual model (set by _IfcGeometricRepresentationContext_) does not coincide with the origin of the _IfcProjectedCRS_

<div align="center">
<img src="./IfcROexample.png" width="700"/>
</div>

**IMPORTANT**: the receiving application does not have to change data in the IFC file, just to interpret the coordinates correctly - according to the information specified in the Coordinate Reference System entity.






