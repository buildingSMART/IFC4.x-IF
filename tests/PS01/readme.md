# Project Setup 01 - BC001-PS01

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| PS01      | Stefan Jaud     | SBB                 | Export/Import  |


## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The series of tests that belong to this Business Case are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| **PS01**  | **Project setup with georeferencing** |
| TE01      | Terrain as existing condition model |
| AL01      | Multiple alignments of railway line |
| LD01      | Loading gauge|
| TR01      | Track panels positioned along alignments |
| BU01      | Building(s) as existing condition model |
| BU02      | Building positioned along alignment |
| MF01      | Model federation|


## IFC concepts involved in this test

- [Project Global Positioning Mapped](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Project_Context/Project_Global_Positioning/content.html)
- [Project Units](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Project_Context/Project_Units/content.html)
- [Project Representation Context](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Project_Context/Project_Representation_Context/content.html)
- [Spatial Decomposition](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Composition/Aggregation/Spatial_Decomposition/content.html)
- [Spatial Containment](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Connectivity/Spatial_Structure/Spatial_Containment/content.html)
- [Mapped Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Mapped_Geometry/content.html)
- [Body Brep Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Body_Geometry/Body_Brep_Geometry/content.html)
- [Type Body Brep Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Type_Shape/Product_Type_Geometric_Representation/Type_Body_Geometry/Type_Body_Brep_Geometry/content.html)
- [Annotation Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Annotation_Geometry/content.html)


## Prerequisites

None.

## Test dataset (input)

The coordinates are defined based on the LV95 ([EPSG 2056](https://epsg.io/2056)) and the vertical datum LN02 ([EPSG:5728](https://epsg.io/5728)).

See [AL01](../AL01/Readme.md) for more details.

This test case utilises the dataset collected in the Dataset folder and is summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| BC001_PS01_reference.ifc  | **Reference IFC file**. Contains an exemplary export for this test.|


## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check


#### Test case-specific checks

[IDS file PS01.ids](./Dataset/PS01.ids):

- (RI-04) An `IfcProject` shall have attributes `Name` and `Description`.
    - The `Name` must be `BC001: Test plan 1`.
    - The `Description` must be non-empty.

Not covered by the IDS file (must be checked otherwise):

- (RI-01) An `IfcProject` shall define relevant measurement units.
    - There must be at least these 2 instances of `IfcNamedUnit` assigned as default units:
        - one `.LENGTHUNIT.` and
        - one `.PLANEANGLEUNIT.`.
- (RI-03) An `IfcGeometricRepresentationContext` shall be associated with the `IfcProject`. The project origin should be `(0,0,0)`.
- (RI-64) The placement of `IfcAnnotation` shall be relative to the `IfcSite` in which it is contained.
- (RI-65) The placement of `IfcSite` shall be absolute within the `IfcGeometricRepresentationContext`.
- (RI-77) `IfcAnnotation.USERDEFINED` with `ObjectType='Annotation point'` shall have `'Point'` geometry and use `IfcCartesianPoint`.
- (RI-87) The model shall containts an `IfcProjectedCRS` that defines the map coordinate system and an `IfcMapConversion` or `IfcRigidOperation` that defines the mapping between `IfcProjectedCRS` and `IfcGeometricRepresentationContext`. 
    - Georeferencing of the project shall be assigned as
        - LV95 ([EPSG:2056](https://epsg.io/2056)) and 
        - LN02 ([EPSG:5728](https://epsg.io/5728)).


### Informal criteria

- Check if three pyramids are turned upside down.
- Check if annotations lie at apexes of the pyramids (pair-wise).


### Expected geometry

There should be three annotations:

1. `IfcAnnotation` with `GlobalId='2RhbhoXQ53yAzPOejOTUcp'` with its geometry at position `(700.000970772933, 1570., 0.)` relative to project base point;
2. `IfcAnnotation` with `GlobalId='2RhbhoXQ53yBzPOejOTUcp'` with its geometry at position `(2005.00097121531, 1765., 0.)` relative to project base point; and
3. `IfcAnnotation` with `GlobalId='2RhbhoXQ53yCzPOejOTUcp'` with its geometry at position `(195.00097114034, 2100., 0.)` relative to project base point.

There should be three pyramids turned upside down:

- with base width of 5 decimeters and height of 1.5 meters (map measurements).

1. product with `GlobalId='3RhbhoXQ53yRzPOejOTUcp'` with its apex at position `(700.000970772933, 1570., 0.)` relative to project base point;
2. product with `GlobalId='3RhbhoXQ53yRzPOejOTUgT'` with its apex at position `(2005.00097121531, 1765., 0.)` relative to project base point; and
3. product with `GlobalId='3XMP46M8P65ugGKLEpO4FP'` with its apex at position `(195.00097114034, 2100., 0.)` relative to project base point.


### Control parameters

The following steps should be performed in order to corroborate that the software is working as expected.

After importing the reference file (`BC001_PS01_reference.ifc`):

- project units set to meters for length and degrees for angles;
- coordinate reference system set to LV95 and LN02 as stated above; and
- the apex of the pyramid with `GlobalId='3RhbhoXQ53yRzPOejOTUcp'` shall have global coordinates `(2689700.000970772933, 1254570., 450.)` (up to a delta of `1e-6`).


## Link to requirements

:zap:
