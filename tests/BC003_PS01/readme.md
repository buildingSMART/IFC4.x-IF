# Project Setup 01 - BC001-PS01

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
|BC001-PS01 | Joao Correa     | MINnD               | Export/Import  |


## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The series of tests that belong to this Business Case are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| **PS01**  | **Project setup with georeferencing** |
| AL01      | Multiple alignments of railway line |
| RR01      | Railway track elements validation |
| ALX1      | Stationing tests on equipment (punctual)|
| ALX2      | Stationing tests on nodes (punctual) |
| ALX3      | Alignment reference check on linear elements |
| NE01      | Network integrity/continuity check on linear elements |
| ALX4      | Stationing tests on cable joints (punctual) |
| NE02      | Cable routing |


## Prerequisites

None.

## Test dataset (input)

The coordinates system is based on RGF93 Lambert Zone 3 ([EPSG 3944](https://epsg.io/3944)) and the vertical datum NGF IGN69 ([EPSG:5720](https://epsg.io/5720)).

See [AL01](../AL01/Readme.md) for more details.

This test case utilises the dataset collected in the Dataset folder and is summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| BC003_PS01_reference.ifc  | **Reference IFC file**. Contains an exemplary export for this test. Please, note that this IFC file was created using the existing capabilities of Civil 3D, which means that the file is not 100% compliant with the test requirements.|


## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check


#### Test case-specific checks

[IDS file BC003_PS01.ids](./Dataset/BC003_PS01.ids):

- There must be 1 instance of `IfcProject` and must be named BC003: Test plan 1.

Not covered by the IDS file (must be checked otherwise):

- There must be at least 1 instance of `IfcSIUnit` assigning METRE as default units for length. It shall be applied to the whole project.
- There must be at least these 1 instance of `IfcSIUnit` assigning RADIAN as default units for plane angle. It shall be applied to the whole project.  RADIAN plane angles can then be converted/presented using DEGREES units.
- Georeferencing of the project shall be assigned as RGF93 Lambert Zone 3 ([EPSG 3944](https://epsg.io/3944))


### Informal criteria

- Check if three pyramids are turned upside down.


### Expected geometry


There should be three pyramids turned upside down:

- with base width of 5 decimeters and height of 1.5 meters (map measurements).

1. product with `GlobalId='0SGxbfZ753H9JxUygRKEif'` with its apex at position `(1892028.44995586, 3126573.34741202, 3.58214714)` ;
2. product with `GlobalId='1QGIfOv2vCmP6wCdfw661z'` with its apex at position `(1891963.00866927, 3126717.20273397, 3.95935497)` ; and
3. product with `GlobalId='0gElLyvUP7pu3MBs30OjlL'` with its apex at position `(1892026.93786196, 3126788.73823184, 3.64980163)`.


### Control parameters

The following steps should be performed in order to corroborate that the software is working as expected.

After importing the reference file (`BC003_PS01_reference.ifc`):

- project units set to meters for length and radians for angles;
- coordinate reference system set to RGF93 Lambert Zone 3 as stated above; and
- the apex of the pyramid with `GlobalId='0gElLyvUP7pu3MBs30OjlL'` shall have global coordinates `(1892026.93786196, 3126788.73823184, 3.64980163)` (up to a delta of `1e-6`).


## Link to requirements

:zap:

