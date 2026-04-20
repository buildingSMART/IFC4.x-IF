# Test dataset

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| ALX4      | Joao Correa     | MINnD               | Import/Export  |

## Content
- [Test dataset](#test-dataset)
  - [Content](#content)
  - [Model Dataset](#model-dataset)
  - [Test Data (Input)](#test-data-input)


## Model Dataset

This dataset is an example of what the railway low voltage, signalling and communication equipment model should contain. The objectives of this test are to validate the creation of cable joints, their placement and visualization in the model. The content of this file will be used as reference for subsequent Tests. 


### Main IFC concepts involved in this test

:zap:


## Test dataset (input)

The dataset considers a segment of tramway line. It is made of a dwg file containing part of a signalization system including equipments chambers, cable troughs, cable carriers, cables and cable joints.
The coordinates system is based on RGF93 Lambert Zone 3 ([EPSG:3944](https://epsg.io/3944)) and vertical datum based on the NGF IGN69 ([EPSG:5720](https://epsg.io/5720)).
 In the reference file, there are in total **2 cable joints** represented by **3D solids** exported as `IfcCableFitting` with the predefined type `CONNECTOR` that will be used in the next tests. It also contains the same 4 railway alignments, 7 cabling alignments, 3 chambers, 2 cable troughs, 1 cable carrier, and two equipment used in the previous test plans.

| Filename (format)                   | Description                                                        |
|-------------------------------------|--------------------------------------------------------------------|
| BC003_ALX4_reference.ifc  | **Reference IFC file.** Contains an exemplary export for this test. Please, note that this IFC file was created using the existing capabilities of Civil 3D, which means that the file is not 100% compliant with the test requirements.|
| BC003_ALX4_cable_joints.dwg | **Native file.** It’s an Autodesk Civil 3D 2024 file containing generic objects to represent the signalling system, including the two cable joints. |


### Cable joints

**Cable joints** are components used to connect different cable segments in diverse technical situations like when the maximun cable lenght is exceeded or when technical restrictions imposes it use. They are represented by **3D solids** or **3D Blocks** placed inside of chambers along the railway alignment using **georeferenced coordinates (XYZ)**. Once placed, these coordinates are then correlated to railway alignments to facilitate their localization in the real world.
Each element has a group of general properties like Global Id, Ifc class, base point, reference alignment and reference station, and a group of technical propertiens including dimensions, material, system or systems that it’s part of and etc.
