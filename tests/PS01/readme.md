# Project Setup 01 - BC001-PS01

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| PS01      | Stefan Jaud     | SBB                 | Export/Import  |


## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The series of tests that belong to this Business Cases are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| **PS01**      | **Project setup with georeferencing** |
| TE01      | Terrain as existing condition model |
| AL01      | Multiple alignments of railway line |
| LD01      | Loading gauge|
| TR01      | Track panels positioned along alignments |
| BU01      | Building(s) as existing condition model |
| BU02      | Building positioned along alignment |
| MF01      | Model federation|


<details><summary>IFC concepts involved in this test</summary> 

- [Project Global Positioning Mapped](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/project-global-positioning-mapped.htm)
- [Project Units](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/project-units.htm)
- [Project Representation Context](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/project-representation-context.htm)
- [Spatial Decomposition](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/spatial-decomposition.htm)
- [Spatial Containment](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/spatial-containment.htm)
- [Mapped Geometry](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/mapped-geometry.htm)
- [Body Brep Geometry](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/body-brep-geometry.htm)

</details>


## Test dataset (input)

The coordinates are defined based on the LV95 ([EPSG 2056](https://epsg.io/2056)) and the vertical datum LN02 ([EPSG:5728](https://epsg.io/5728)).

See [AL01](../AL01/Readme.md) for more details.

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| BC001_PS01_reference.ifc  | **Reference IFC file**. Contains an exemplary export for this test.|


## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check

> TODO *remains to be determined, which service to use*

- All following rules:
  - RI-01
  - RI-03
  - RI-04
  - RI-77
  - RI-87


#### Test case-specific checks

Link to IDS file: `[ABCD123.ids]()` :construction:

- There must be 1 instance of IfcProject and must be named `BC001: Test plan 1`.
- There must be at least these 2 instances of `IfcNamedUnit` assigned as default units:
    - one `.LENGTHUNIT.` and
    - one `.PLANEANGLEUNIT.`.
- Georeferencing of the project shall be assigned as
    - LV95 ([EPSG:2056](https://epsg.io/2056)) and 
    - LN02 ([EPSG:5728](https://epsg.io/5728)).


### Informal criteria

> TODO *remains to be determined*


### Expected geometry

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

> TODO *remains to be determined*

:zap: ??
