# TR01 - Track panels positioned along alignments

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| TR01      | Chi Zhang             | SBB                 | Export, Import         |



## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The intention of this Business Case is to test how model federation works in the context of IFC 4.3. 
In particular we want to test the behaviour of objects that are located in relation to an alignemnt (for example a turnout within an alignment) and in relation to fixed coordinates (for example existing buildings) with georeferencing information set as the global context.
We would also like to test other essential concepts that are related to model federation like project break down structure (or to say, Spatial Structure) and revision and access control for elements.
The series of tests that belong to this Business Cases are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| PS01      | Project setup with georeferencing |
| AL01  | Multiple alignments of railway line |
| LG01      | Loading gauge|
| **TR01**      | **Track panels positioned along alignments** |
| BD01      | Building and terrain as existing condition model |
| BD02      | Building positioned along alignment |
| MF01      | Model federation|


With this series of tests, we are attempting to build a step-by-step process to realize a business case.
The dependency between them are shown in the following diagram:

![Alt text](Dataset/Test_case_dependency.PNG "Dependency between tests")

To perform a certain test in this series, developers can start from the very beginning (AKA. PS01) to build all the prerequisites independently, or based on outcomes from prerequisites tests.

This particular Test aims to test the implementation of track panels in IFC 4.3. It is based on the AL01, which defines multiple alignments, based on which track panels are placed. This test will test the linear placement of track panels, and their element decomposition structures and element types. The track panels created in this Test will be used as one domain model for model federation (MF01).

<details>
	<summary>Main IFC concepts involved in this test</summary> 

The concept templates that are focused by this series of tests are listed as follows. Specific concept templates that are focused by this test are in Bold.

- [Product Linear Placement](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Placement/Product_Linear_Placement/content.html)
- [Product Local Placement](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Placement/Product_Local_Placement/content.html)
- [Product Relative Positioning](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Connectivity/Product_Relative_Positioning/content.html)
- [Element Decomposition](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Placement/Product_Local_Placement/content.html)
- [Revision Control](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Attributes/Revision_Control/content.html)
- [Software Identity](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Attributes/Software_Identity/content.html)

</details>
<details>
	<summary>Recommended IFC concepts involved in this test</summary> 

Optionally, these concepts templates should be applied in this Test.

- [Body AdvancedSwept Directrix Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Body_Geometry/Body_AdvancedSweptSolid_Geometry/Body_AdvancedSwept_Directrix_Geometry/content.html)
- [Object Typing](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Definition/Object_Typing/content.html)
- [Mapped Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Mapped_Geometry/content.html)

</details>
<details>
	<summary>Main software features involved in this series of tests</summary> 

- Alignment visualization
</details>


## Test dataset (input)

The dataset is made of an IFC 2x3 file. It contains a section of railway line that have tracks consist of track panels and turnout panels, which are instantiated as IfcElementAssembly. Each track panel and turnout panel consists of rails and sleepers. Rails and sleepers are all instantiated as IfcBuildingElementProxy, which have the body representation of Brep or SweptSolid.



| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| [BC001_Track.ifczip](https://app.box.com/s/vroc2d7zqoooi9idnx2x8zj0tsuv8xrq)    |    Data containing track panels in IFC 2x3 format                           |

In addition, the outcome of the Test AL01 shall be used as inputs of this Test.
## Validation criteria
⚡ For this test case to be considered passed, all criteria listed in this section, and the ones of prerequisites tests shall be verified. ⚡

### Formal rules
Formal Rules are those contained in the Gerkin documentation provided within the bSI validation system. In particular, the following list of rules will apply

#### IFC standard (schema and specification)
When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check
- All following rules:
  - ED001 - Each 'IfcElement' that is decomposed by other `IfcElement` shall not have body representation.
  - EP001 - An `IfcProduct` that is positioned based on an `IfcPositioningElement` shall be placed relative to the `ObjectPlacement` of the `IfcPositioningElement`.
  - EP002 - An `IfcElement` that composes another `IfcElement` shall not have `IfcRelPositions` relationship to an `IfcPositioningElement` or have `IfcRelContainedInSpatialStructure` relationship to an IfcSpatialStructureElement.

#### Test case-specific checks

Link to IDS file: STN01.ids 🚧

- (RI-18) Each `IfcElementAssembly.TRACKPANEL` or `IfcElementAssembly.TURNOUTPANEL` must have a `Name`.
- (RI-19) Each `IfcTrackElement.SLEEPER` and `IfcRail.RAIL` shall have 'Body' representation.
- (RI-60, RI-61) It is recommended that all 'Body' representations shall have extruded or swept solid geometry. It is acceptable to have tessellated geometry. All `IfcTrackElement.SLEEPER` shall have mapped geometry.
- (RI-21) Each `IfcElementAssembly.TRACKPANEL` and `IfcElementAssembly.TURNOUTPANEL` must have `OwnerHistory` assigned, which has `OwningUser`, `OwningApplication`, `ChangeAction`, `CreationDate` and `State`. The `IfcOwnerHistory` can be shared by multiple `IfcElementAssembly` if they have the same information, but the `IfcOwnerHistory` used by `IfcElementAssembly` shall be different with the ones used by `IfcAlignment` and `IfcProject`.
- Each `IfcElementAssembly.TRACKPANEL` or `IfcElementAssembly.TURNOUTPANEL` must be decomposed by `IfcRail.RAIL` and `IfcTrackElement.SLEEPER`.

### Informal criteria
The following steps should be performed in order to corroborate that the software is working as expected:

- All track panels shall be visualized in 3D.
- The hierarchy of the model shall be:
  - `IfcProject`
    - `IfcAlignment`
    - `IfcSite.Name='DORF-BSD'`
    - `IfcRailway.Name='RL'`
      - `IfcRailwayPart.TRACKSTRUCTUREPART.Name='TRCK'`
        - `IfcElementAssembly.TRACKPANEL`
          - `IfcTrackElement.SLEEPER`
          - `IfcRail.RAIL`
        - `IfcElementAssembly.TURNOUTPANEL`
          - `IfcTrackElement.SLEEPER`
          - `IfcRail.RAIL`





### Expected geometry
>:information_source: *add image of the expected geometry. Upload the jpeg/png file in the Dataset folder of this test*

![Alt text](Dataset/Visualization.PNG "Visualization of track panels")

### Control parameters
>:information_source: *add parameters/data that can be use to support the validation of import into a receiving application. Example: total length of one alignment, coordinates for end point of the alignment.*

| Track Panel        | Type | Alignment | StartDistAlong |
|------------------|-----------|-----------|--------------|
| Allgemeines Modell Baugruppe:Gleisrost_2:40004919 | IfcElementAssembly.TRACKPANEL   |              |              |  
| Allgemeines Modell Baugruppe:Gleisrost_002:40119142 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_003:40126858 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Weiche_13:40192369 | IfcElementAssembly.TURNOUTPANEL |              |              |    
| Allgemeines Modell Baugruppe:Weiche_14:40195002 | IfcElementAssembly.TURNOUTPANEL |              |              |    
| Allgemeines Modell Baugruppe:Weiche_15:40196791 | IfcElementAssembly.TURNOUTPANEL |              |              |    
| Allgemeines Modell Baugruppe:Weiche_17:40199109 | IfcElementAssembly.TURNOUTPANEL |              |              |    
| Allgemeines Modell Baugruppe:Weiche_16:40200465 | IfcElementAssembly.TURNOUTPANEL |              |              |    
| Allgemeines Modell Baugruppe:Gleisrost_001:40256392 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_010:40257923 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_011:40258190 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_012:40258457 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_013:40258724 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_014:40262086 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_015:40262387 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_016:40262642 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_017:40262897 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_018:40263208 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_019:40263463 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_020:40263721 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_021:40264005 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_022:40264408 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_023:40264690 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_024:40264972 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_025:40265227 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_026:40265538 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_027:40265820 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_028:40266075 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_029:40266386 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_030:40266640 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_031:40268538 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_032:40268784 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_033:40269143 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_034:40269389 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_035:40269636 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_036:40269946 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_037:40270274 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_038:40270528 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_039:40270774 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_040:40271021 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_041:40271331 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_042:40271632 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_043:40271912 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_044:40272240 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_045:40272520 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_046:40272766 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_047:40273040 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_048:40273320 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_049:40273620 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_050:40274116 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_051:40275972 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_052:40276318 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_053:40276573 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_054:40276911 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_055:40277181 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_056:40277487 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_057:40277742 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_058:40277997 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_059:40278307 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_060:40278554 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_061:40278865 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_062:40279120 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_063:40279375 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_064:40279629 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_065:40279903 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_066:40280157 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_084:40473697 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_085:40476692 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_086:40476715 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_087:40476734 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_088:40476746 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_089:40476769 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_090:40476797 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_091:40476876 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_092:40476901 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_093:40476925 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_094:40476948 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_095:40476972 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_096:40476994 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_097:40477016 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_098:40477040 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Gleisrost_099:40477060 | IfcElementAssembly.TRACKPANEL   |              |              |
| Allgemeines Modell Baugruppe:Weiche 18:40478440 | IfcElementAssembly.TURNOUTPANEL |              |              |

### Link to requirements

[BC-001_Requirements.xlsx](https://app.box.com/s/2sotgbbzx2mpry7oj9fud9b3xlv6p1i4)



...
