# Terrain 01 - BC001-TE01

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| TE01      | Stefan Jaud     | SBB                 | Export/Import  |


## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The series of tests that belong to this Business Cases are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| PS01      | Project setup with georeferencing |
| **TE01**      | **Terrain as existing condition model** |
| AL01      | Multiple alignments of railway line |
| LD01      | Loading gauge|
| TR01      | Track panels positioned along alignments |
| BU01      | Building(s) as existing condition model |
| BU02      | Building positioned along alignment |
| DR01      | Drainage system for railway line |
| MF01      | Model federation|


<details><summary>IFC concepts involved in this test</summary> 

- [Body Tessellation Geometry](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/body-tessellation-geometry.htm)

</details>

## Prerequisites

The dataset builds upon the dataset from PS01 - see [PS01](../PS01/Readme.md) for more details.


## Test dataset (input)

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| BC001_TE01_reference.ifc  | **Reference IFC file**. Contains an exemplary export for this test.|


## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

> TODO *remains to be determined*

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check
- All following rules:
  - ??

> TODO *remains to be determined*

#### Test case-specific checks

Link to IDS file: `[ABCD123.ids]()` :construction:

1. Either:
- There must be 4 instances of `IfcGeographicElement` in the dataset
- There must be 4 instances of `IfcTriangulatedIrregularNetwork` in the dataset (as representations of the elements above)

2. Or:
- There must be 1 instances of `IfcGeographicElement` in the dataset
- There must be 1 instances of `IfcTriangulatedIrregularNetwork` in the dataset (as representation of the element above)
    - a union of the 4 elements above

The `IfcGeographicElement` instances shall be aggregated in `IfcSite`.

The provided reference file follows option 1.


### Informal criteria

None. See Expected geometry below.


### Expected geometry

There should be one or four triangulated irregular networks (TINs) defined as described in the [Dataset description](Dataset/README.md).



### Control parameters

The following steps should be performed in order to corroborate that the software is working as expected.

After importing the reference file (`BC001_TE01_reference.ifc`):

- the three reference bodies from PS01 should lie outside, but in proximity of the terrain
- the min/max values of terrain provided in Expected geometry above should be equal


## Link to requirements

> TODO *remains to be determined*

:zap: ??
