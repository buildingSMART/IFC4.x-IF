# 2 Multiple alignments of railway line - BC003-AL01

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
|BC003-AL01 | Joao Correa     | MINnD               | Import/Export  |


## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The series of tests that belong to this Business Case are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
|   PS01    | Project setup with georeferencing |
| **AL01**  | **Multiple alignments of railway line** |
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

The dataset is composed of a LandXML file that contains alignments for a section of a 1.7 kilometers long tramway line. In this file you’ll find 4 aligments that compose this section.
The coordinates system is based on RGF93 Lambert Zone 3 ([EPSG 3944](https://epsg.io/3944)) and the vertical datum NGF IGN69 ([EPSG:5720](https://epsg.io/5720)).

This test case utilises the dataset collected in the Dataset folder and is summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| BC003_AL01_reference.ifc  | **Reference IFC file.** Contains an exemplary export for this test. Please, note that this IFC file was created using the existing capabilities of Civil 3D, which means that the file is not 100% compliant with the test requirements.|
| BC003_AL01_alignments.dwg  | **Reference native file.** It’s an Autodesk Civil 3D 2023 file containing the 4 project alignments.|
| BC003_AL01_alignments.xml  | **The exported LandXML** format from the native file containing the same 4 alignments.|

In addition, the outcome of the test PS01 shall be used as input of this test.

## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check


#### Test case-specific checks

[IDS file BC003_AL01.ids](./Dataset/BC003_AL01.ids):

- There must be 1 instance of `IfcProject` and must be named `BC003: Test plan 1` and the `GUID “3cyAkba2v5a9pVuthidcpX”`.
- Each `IfcAlignment` shall have a Name which is the same with the one in the LandXML file.
- Each `IfcAlignment` must have a start station.
- The horizontal layout must include only the following types of segments: Line, Circular Arc, Clothoid
- The vertical layout must include only the following types of segments: Constant Gradient, Parabolic Arc

Not covered by IDS but information can be extracted from it for external analysis:
- There must be 4 instance(s) of `IfcAlignment`.

Not covered by IDS file (must be checked otherwise):
- Each `IfcAlignment` must have OwnerHistory assigned, which has OwningUser, OwningApplication, ChangeAction, CreationDate and State. The `IfcOwnerHistory` can be shared by multiple `IfcAlignment`(s) if they have the same information.
- (TBD) Each `IfcAlignment` must be aggregated directly under `IfcProject`.
- (TBD) Each `alignment` must nest a list of stationing. The list of stationing is defined following this principle:
	- There should be 1 stationing every 10 meters;
	- There should be 1 stationing at both start and end point of the alignments;
	- There should be 1 stationing at each start and end point of the horizontal curves.


### Informal criteria

The following steps should be performed in order to corroborate that the software is working as expected:
1. All alignments shall be visualized in 3D.
2. It is recommended that each layout of alignments can be visualized in 2D.
3. Stationing along alignments shall be visualized in horizontal 2D layout and 3D.
4. Each alignment must be continuous with certain delta. This also applies to tangent continuity and curvature continuity, in these two cases gaps that exceed the delta will be checked case by case.


### Expected geometry

![Alt text](Dataset/BC003_AL01_Alignments_Image.PNG "Visualization of alignments")


### Control parameters

The following steps should be performed in order to corroborate that the software is working as expected.

After importing the reference file (`BC003_AL01_alignments.xml`):

1. **Alignment SAN1_XD-B02:**
- The total `2D length` of the track alignment (horizontal projection) is `1709.845 meters`
- The `ending point` of the track alignment has coordinate (x, y, z) `1891846.487, 3128145.730, 20.987`.
- The `vertical height` difference between starting and ending points of the track alignment 3D curve is `16.928 meters`

2. **Alignment SAN1_XG-B02:**
- The total `2D length` of the track alignment (horizontal projection) is `1693.042 meters`.
- The station `0+280.000` has coordinate (x, y, z) `1892098.988, 3126816.919, 3.710`. 
- The `vertical height` difference between station 0+280.000 and 0+870.000 of the track alignment 3D curve is `4.214 meters`.

3. **Alignment SAN1_COM:**
- The total `2D length` of the track alignment (horizontal projection) is `0.179 meters`.
- The station `0+20.000` has coordinate (x, y, z) `1892000.407, 3126651.012, 5.462`. 
- The `vertical height` difference between station `0+10.000` and `0+30.000` of the track alignment 3D curve is `0.000 meters`.

4. **Alignment SAN1_XG-3eme_Voie:**
- The total `2D length` of the track alignment (horizontal projection) is `104.421 meters`.
- The `ending point` of the track alignment has coordinate (x, y, z) `1891962.999, 3126722.276, 3.886`
- The `vertical height` difference between starting and ending points of the track alignment 3D curve is `0.190 meters`.


## Link to requirements

:zap:

