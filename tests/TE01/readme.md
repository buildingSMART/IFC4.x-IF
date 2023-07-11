# Terrain 01 - BC001-TE01

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| TE01      | Stefan Jaud     | SBB                 | Export/Import  |


## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The series of tests that belong to this Business Case are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| PS01      | Project setup with georeferencing |
| **TE01**  | **Terrain as existing condition model** |
| AL01      | Multiple alignments of railway line |
| LD01      | Loading gauge|
| TR01      | Track panels positioned along alignments |
| BU01      | Building(s) as existing condition model |
| BU02      | Building positioned along alignment |
| MF01      | Model federation|


## IFC concepts involved in this test

- All listed in [PS01](https://github.com/buildingSMART/IFC4.x-IF/tree/main/tests/PS01#ifc-concepts-involved-in-this-test)
- [Surface Tessellation Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Surface_Geometry/Surface_Tessellation_Geometry/content.html)


## Prerequisites

The test plan builds upon the [PS01 test plan](../PS01/Readme.md).


## Test dataset (input)

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| BC001_TE01_reference.ifc  | **Reference IFC file**. Contains an exemplary export for this test.|


## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check


#### Test case-specific checks

[IDS file TE01.ids](./Dataset/TE01.ids):

- The `IfcGeographicElement` instances shall be contained in `IfcSite`.

Not covered by the IDS file (must be checked otherwise):

- (RI-60, RI-68) `IfcGeographicElement.TERRAIN` shall have tessellated `Surface` geometry.
- (RI-64) `IfcGeographicElement` shall be placed locally within `IfcSite` they are contained within.

1. Either:
- There must be 4 instances of `IfcGeographicElement` in the dataset
- There must be 4 instances of `IfcTriangulatedIrregularNetwork` in the dataset (as representations of the elements above)

2. Or:
- There must be 1 instances of `IfcGeographicElement` in the dataset
- There must be 1 instances of `IfcTriangulatedIrregularNetwork` in the dataset (as representation of the element above)
    - a union of the 4 elements above

The provided reference file follows option 1.


### Informal criteria

- The three reference pyramids from PS01 should lie outside, but in proximity of the terrain.


### Expected geometry

There should be one or four triangulated irregular networks (TINs) defined as described in the [Dataset description](./Dataset/README.md).



### Control parameters

The following steps should be performed in order to corroborate that the software is working as expected.

After importing the reference file (`BC001_TE01_reference.ifc`):

- The min/max values of terrain provided in Expected geometry above should be equal to those provided in [Expected Geometry](#expected-geometry).


## Link to requirements

:zap:
