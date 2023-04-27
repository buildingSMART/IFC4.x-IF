# AL01 - Multiple alignments of railway line

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| MF01      | Mercedes Santos, Chi Zhang             | SBB                 | Export, Import         |



## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The intention of this Business Case is to test how model federation works in the context of IFC 4.3. 
In particular we want to test the behaviour of objects that are located in relation to an alignemnt (for example a turnout within an alignment) and in relation to fixed coordinates (for example existing buildings) with georeferencing information set as the global context.
We would also like to test other essential concepts that are related to model federation like project break down structure (or to say, Spatial Structure) and revision and access control for elements.
The series of tests that belong to this Business Cases are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| PS01      | Project setup with georeferencing |
| **AL01**  | **Multiple alignments of railway line** |
| LG01      | Loading gauge|
| TR01      | Track panels positioned along alignments |
| BD01      | Building and terrain as existing condition model |
| BD02      | Building positioned along alignment |
| DR01      | Drainage system for railway line |
| MF01      | Model federation|


With this series of tests, we are attempting to build a step-by-step process to realize a business case.
The dependency between them are shown in the following diagram:

![Alt text](Dataset/Test_case_dependency.PNG "Dependency between tests")

To perform a certain test in this series, developers can start from the very beginning (AKA. PS01) to build all the prerequisites independently, or based on outcomes from prerequisites tests.

This particular Test aims to test the implementation of alignment in IFC 4.3. It is based on the PS01, which defines the overall context of the project (geometric representation context and projection to a map coordinate system), and TR01, which defines a terrain model as existing environment. This test will test the creation of alignment geometry and its visualization. The alignments created in this Test will be used as the linear positioning based for subsequent Tests. As the shared data required by all the subsequent tests, the alignments created in this Test will also be key for the final model federation (MF01).

<details>
	<summary>Main IFC concept involved in this test</summary> 

The concept templates that are focused by this series of tests are listed as follows. Specific concept templates that are focused by this test are in Bold.

- [Project Global Positioning](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Project_Context/Project_Global_Positioning/content.html)
- [Alignment Layout](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Composition/Nesting/Alignment_Layout/content.html)
- [Alignment Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Alignment_Geometry/content.html)
- [Product Local Placement](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Placement/Product_Local_Placement/content.html)
- [Revision Control](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Attributes/Revision_Control/content.html)
- [Software Identity](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Attributes/Software_Identity/content.html)
docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Clearance_Geometry/content.html)
- [Object Nesting](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Composition/Nesting/Object_Nesting/content.html)

</details>
<details>
	<summary>Main software features involved in this series of tests</summary> 

- Alignment visualization
</details>


## Test dataset (input)

The dataset is made of a LandXML file that has multiple alignments for a section of railway line. The coordinates are defined based on the LV95 ([EPSG 2056](https://epsg.io/2056)) and the vertical datum is LN02 ([EPSG:5728](https://epsg.io/5728)). It has in total 11 alignments and the railway section is about 18 kilometers long. 
An IFC 4.3 reference file is also provided.



| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| [BC001_Alignment.xml](Dateset/BC001_Alignment.xml)    |    Data containing track alignments in LandXML format                                   |
| [BC001_Alignment.dwg](Dateset/BC001_Alignment.dwg)     |    Data containing track alignments in DWG format                                 |
| BC001_Alignment(Reference).ifc    |    Data containing track alignments in IFC 4.3                                  |

In addition, the outcome of the Test PS01 and TE01 shall be used as inputs of this Test.
## Validation criteria
⚡ For this test case to be considered passed, all criteria listed in this section, and the ones of prerequisites tests shall be verified. ⚡

### Formal rules
Formal Rules are those contained in the Gerkin documentation provided within the bSI validation system. In particular, the following list of rules will apply

#### IFC standard (schema and specification)
When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check
- All following rules:
  - ALB002 - Alignment layout 
  - ALB003 - Alignment directions
  - TBD000 - Alignment shape representation 
  - TBD000 - Stationing along alignment

#### Test case-specific checks

Link to IDS file: STN01.ids 🚧

- (RI-18) Each IfcProduct must have a Name.
- Each IfcAlignment shall have a Name which is the same with the one in the LandXML file.
- There must be 11 instance(s) of IfcAlignment(s).
- (RI-21) Each IfcAlignment must have OwnerHistory assigned, which has OwningUser, OwningApplication, ChangeAction, CreationDate and State. The IfcOwnerHistory can be shared by multiple IfcAlignment(s) if they have the same information.
- (RI-15, RI-7) Each IfcAlignment must have a start station.
- (RI-8) The horizontal layout must include only the following types of segments: Line, Circular Arc, Clothoid
- (RI-11) The vertical layout must include only the following types of segments: Constant Gradient, Circular Arc
- (RI-13) The cant layout must include only the following types of segments: Constant Cant, Linear Transition
- (TBD) Each IfcAlignment must be aggregated directly under IfcProject.
- (TBD) Each alignment must nest a list of stationing. The list of stationing is defined following this principle:
  - Each alignment shall have a start stationing of 0
  - There should be 1 stationing every 100 meters
  - There should be 1 stationing in each intersection between alignment horizontal segments
  - There should be 1 stationing in each intersection between alignments


### Informal criteria
The following steps should be performed in order to corroborate that the software is working as expected:

- All alignments shall be visualized in 3D.
- It is recommended that each layout of alignments can be visualized in 2D.
- Stationing along alignments shall be visualized in horizontal 2D layout and 3D.
- Each alignment must be continuous with certain delta. This also applies to tangent continuity and curvature continuity, in these two cases gaps that exceed the delta will be checked case by case.



### Expected geometry
>:information_source: *add image of the expected geometry. Upload the jpeg/png file in the Dataset folder of this test*

![Alt text](Dataset/Alignments_visualization.PNG "Visualization of alignments")

### Control parameters
>:information_source: *add parameters/data that can be use to support the validation of import into a receiving application. Example: total length of one alignment, coordinates for end point of the alignment.*

| Alignment        | 2D Length | 3D Length | ending point | vertical height difference |
|------------------|-----------|-----------|--------------|----------------------------|
|   A50034A        |           |           |              |                            |
|   A50068A        |           |           |              |                            |
|   A50113A        |           |           |              |                            |
|   A50114A        |           |           |              |                            |
|   A50115A        |           |           |              |                            |
|   A50116A        |           |           |              |                            |
|   A50117A        |           |           |              |                            |
|   A50118A        |           |           |              |                            |
|   A50119A        |           |           |              |                            |
|   A50120A        |           |           |              |                            |
|   A50121A        |           |           |              |                            |

### Link to requirements
>:information_source: *list requirements covered by this test, or refer to external documentation*

...
