# Test dataset

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| ALX1      | Joao Correa     | MINnD               | Import/Export  |

## Content
- [Test dataset](#test-dataset)
  - [Content](#content)
  - [Model Dataset](#model-dataset)
  - [Test Data (Input)](#test-data-input)


## Model Dataset

This dataset is an example of what the railway low voltage, signalling and communication equipment model should contain. The objectives of this test are to validate the creation of low voltage and communication infrastructure equipment like traffic signs, information panels and etc, and their visualization. The content of this file will be used as reference for subsequent Tests. 


### Main IFC concepts involved in this test

:zap:


## Test dataset (input)

The dataset considers a segment of tramway line. It is made of a dwg file containing two signalling equipment.
The coordinates system is based on RGF93 Lambert Zone 3 ([EPSG:3944](https://epsg.io/3944)) and vertical datum based on the NGF IGN69 ([EPSG:5720](https://epsg.io/5720)).
 There are in total **2 traffic lights** represented by **3D solids** exported as `IfcSign` that will be used in the next tests. It also contains the same 4 alignments used in the previous test plans.

| Filename (format)                   | Description                                                        |
|-------------------------------------|--------------------------------------------------------------------|
| BC003_ALX1_reference.ifc  | **Reference IFC file.** Contains an exemplary export for this test. Please, note that this IFC file was created using the existing capabilities of Civil 3D, which means that the file is not 100% compliant with the test requirements.|
| BC003_ALX1_equipment.dwg | **Native file.** It’s an Autodesk Civil 3D 2023 file two generic objects that represents railway signals. |


### Low voltage and communication equipment

**Low voltage, signalling and communication equipment** are electric and electronic devices placed along the railway line for several purposes including the transmission of rolling stock information, traffic control, alerts and instructions for the train driver. They are represented by **3D solids** or **3D Blocks** placed along the model using **georeferenced coordinates (XYZ)** that are then correlated to railway alignments to facilitate their localization in the real world.
Each element has a group of general properties like Global Id, Ifc class, base point, reference alignment and reference station, and a group of technical propertiens including dimensions, material, system or systems that it’s part of and etc.



