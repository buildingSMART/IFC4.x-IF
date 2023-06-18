# MF01 - Model Federation

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| MF01      | Chi Zhang       | SBB                 | Export, Import |



## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The intention of this Business Case is to test how model federation works in the context of IFC 4.3. 
In particular we want to test the behaviour of objects that are located in relation to an alignemnt (for example a turnout within an alignment) and in relation to fixed coordinates (for example existing buildings) with georeferencing information set as the global context.
We would also like to test other essential concepts that are related to model federation like project break down structure (or to say, Spatial Structure) and revision and access control for elements.
The series of tests that belong to this Business Cases are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| PS01      | Project setup with georeferencing |
| TE01      | Terrain as existing condition model|
| AL01  | Multiple alignments of railway line |
| LG01      | Loading gauge|
| TR01      | Track panels positioned along alignments |
| BU01      | Building and terrain as existing condition model |
| BU02      | Building positioned along alignment |
| **MF01**      | **Model federation** |


With this series of tests, we are attempting to build a step-by-step process to realize a business case.
The dependency between them are shown in the following diagram:

![Alt text](Dataset/Test_case_dependency.PNG "Dependency between tests")

To perform a certain test in this series, developers can start from the very beginning (AKA. PS01) to build all the prerequisites independently, or based on outcomes or reference files from prerequisites tests.

This particular Test is the final step of this series. It aims to test the model federtion that integrates multiple models from different domains. It is at least based on the TR01, which defines model of track panels, and BU02, which contains buildings. This Test will test a few topics:
- whether the federated model has the proper spatial structure
- whether certain elements from different models are merged based on GlobalID
- whether models can be coordinated correctly based on the project context and georeferencing
- and etc.

<details>
	<summary>Main IFC concepts involved in this test</summary> 

The concept templates that are focused by this Test are listed as follows. 

- [Project Global Positioning](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Project_Context/Project_Global_Positioning/content.html)
- [Product Local Placement](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Placement/Product_Local_Placement/content.html)
- [Product Linear Placement](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Placement/Product_Linear_Placement/content.html)
- [Spatial Structure](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Connectivity/Spatial_Structure/content.html)
- [Revision Control](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Attributes/Revision_Control/content.html)
- [Software Identity](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Attributes/Software_Identity/content.html)


</details>
<details>
	<summary>Main software features involved in this series of tests</summary> 

- Model Federation
</details>


## Prerequisites

The test plan builds upon the [TR01 test plan](../TR01/Readme.md) and [BU02 test plan](../BU02/Readme.md)


## Test dataset (input)

This Test is based on outcomes or reference files from previous Tests. No other datasets are provided.

## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

Formal Rules are those contained in the Gerkin documentation provided within the bSI validation system. In particular, the following list of rules will apply.

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check
- All rules that defined in previous Tests

#### Test case-specific checks

[IDS file MF01.ids](./Dataset/MF01.ids):

Not covered by the IDS file (must be checked otherwise):

- There must be 11 instance(s) of `IfcAlignment`s.
- The spatial structure of the file shall be as follows:
  - `IfcProject`
    - `IfcAlignment`
    - `IfcSite.Name='DORF-BSD'`
      - `IfcGeographicElement`
      - `IfcBuilding.ObjectPlacement[Type]='IfcLocalPlacement'`
    - `IfcRailway.Name='RL'`
      - `IfcRailwayPart.TRACKSTRUCTUREPART.Name='TRCK'`
        - `IfcElementAssembly.TRACKPANEL`
          - `IfcTrackElement.SLEEPER`
          - `IfcRail.RAIL`
        - `IfcElementAssembly.TURNOUTPANEL`
          - `IfcTrackElement.SLEEPER`
          - `IfcRail.RAIL`
    - `IfcBuilding.ObjectPlacement[Type]='IfcLinearPlacement'`
   


### Informal criteria

The following steps should be performed in order to corroborate that the software is working as expected:

- Models shall be coordinated correctly, regarding positions and geometry.


### Expected geometry

![Alt text](Dataset/Visualization.PNG "Visualization of federated model")

### Control parameters



### Link to requirements

:zap:

