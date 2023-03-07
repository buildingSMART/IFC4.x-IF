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
| AL01      | Multiple alignments of railway line |
| LD01      | Loading gauge|
| TR01      | Track panels positioned along alignments |
| BD01      | Building and terrain as existing condition model |
| BD02      | Building positioned along alignment |
| DR01      | Drainage system for railway line |
| MF01      | Model federation|


<details><summary>IFC concepts involved in this test</summary> 

- [Project Global Positioning Mapped](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/project-global-positioning-mapped.htm)
- [Project Unit Assignment](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/project-units.htm)
- [Project Representation Context](https://bsi-infraroom.github.io/IFC-Documentation-Tunnel/4_4_0_0/general/HTML/link/project-representation-context.htm)
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

> TODO *remains to be determined*

When validated using the bSI Validation Service, the IFC must pass:
- Syntax & Schema check
- All following rules:
  - ??

#### Test case-specific checks

Link to IDS file: `[ABCD123.ids]()` :construction:

- There must be 1 instance of IfcProject and must be named `BC001: Test plan 1`.
- There must be at least these 2 instances of IfcNamedUnit assigned as default units:
    - one `.LENGTHUNIT.` and
    - one `.PLANEANGLEUNIT.`.
- Georeferencing of the project shall be assigned as
    - LV95 ([EPSG 2056](https://epsg.io/2056)) and 
    - LN02 ([EPSG:5728](https://epsg.io/5728)).


### Informal criteria

> TODO *remains to be determined*

None ?? 


### Expected geometry

No expected geometry.


### Control parameters

> TODO *remains to be determined*

The following steps should be performed in order to corroborate that the software is working as expected.

After importing the reference file (`BC001_PS01_reference.ifc`): :construction:
- project base point shall have coordinates ??
- coordinate reference system set to LV95 and LN02 as stated above
- project units set to meters for length and degrees for angles


## Link to requirements

> TODO *remains to be determined*

:zap: ??
