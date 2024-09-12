# 4 Stationing tests on equipment - BC003-ALX1

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
|BC003-ALX1 | Joao Correa     | MINnD               | Import/Export  |


## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The series of tests that belong to this Business Case are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| PS01      | Project setup with georeferencing |
| AL01      | Multiple alignments of railway line |
| RR01      | Railway track elements validation |
| **ALX1**  | **Stationing tests on equipment (punctual)** |
| ALX2      | Stationing tests on nodes (punctual) |
| ALX3      | Alignment reference check on linear elements |
| NE01      | Network integrity/continuity check on linear elements |
| ALX4      | Stationing tests on cable joints (punctual) |
| NE02      | Cable routing |

## IFC concepts involved in this test

The following diagram represents the rationale used for this test: locating signals using XWZ positions and computing their positioning on the alignment.
![Alt text](ALX01-rationale.png "ALX01 - rationale")

The following diagram represents the entities involved in this test.
![Alt text](ALX01-diagram.png "ALX01 - involved entities")

## Prerequisites

The test plan builds upon the previous test plans. All requirements presented in previous test plans must be met.

## Test dataset (input)

This test case utilises the dataset collected in the Dataset folder and is summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)                   | Description                                                        |
|-------------------------------------|--------------------------------------------------------------------|
| BC003_ALX1_reference.ifc  | **Reference IFC file.** Contains an exemplary export for this test. Please, note that this IFC file was created using the existing capabilities of Civil 3D, which means that the file is not 100% compliant with the test requirements.|
| BC003_ALX1_equipment.dwg | **Native file.** It’s an Autodesk Civil 3D 2023 file two generic objects that represents railway signals. |

In addition, the outcome of the previous tests shall be used as input of this test.

## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check


#### Test case-specific checks

[IDS file BC003_ALX1.ids](./Dataset/BC003_ALX1.ids):

- The `IfcProject` must be named `BC003: Test plan 1`;
- `IfcAlignment`s must have these Names and Lengths:

| Name              |  Length (m)  |
|-------------------|--------------|
| SAN1_XD-B02       | 1709.845     |
| SAN1_XG-B02       | 1693.042     |
| SAN1_COM          | 40.179       |
| SAN1_XG-3eme_Voie | 104.421      |

- There must be 2 `IfcSignal`s in the file with these Names:

| Name              |
|-------------------|
| Traffic_Light01   |
| Traffic_Light02   |


#### Not covered by the IDS file (must be checked otherwise):

1. There must be 2 instances of `IfcSign`. 
1. Traffic lights are placed in the model using coordinates (XYZ). Once placed, **railway alignment station** is used to **locate** them for works and maintenance purposes. So, the authoring software shall **correlate their XYZ placement and a station in the railway alignment**. The table below represents for each traffic light, its referenced alignment, the referenced station and its placement coordinates of the base center point:

| Name              | Ref. Alignment    |  Station   |  Coord. XYZ (top center point)  |
|-------------------|-------------------|------------|----------------------------------------|
| Traffic_Light01   | SAN1_XD-B02       | 0+052.0866 | 1891995.6561, 3126679.5487, 4.1500 |
| Traffic_Light02   | SAN1_XG-3eme_Voie | 0+052.0002 | 1891982.5663, 3126673.6030, 4.1400 |

1. (RI-300) Signal geometries are mapped (`IfcMappedItem`) to the `IfcSignType` geometry;
1. (RI-301) Signals are represented as 3D solids with a cylindrical shape (extruded along the Z axis, using `IfcSweptDiskSolid`);
1. (RI-302) Signals are defined by their `IfcSignType`, which are declared in the `IfcProject`.

### Informal criteria

- Railway alignments presented in [BC003_ALX1_Reference](./Dataset/BC003_ALX1_Reference.ifc) file shall be coincident with the ones presented in  [BC003_AL01_Reference](../BC003_AL01/Dataset/BC003_AL01_Reference.ifc) file ;

### Open questions

- Shall every `IfcElement` instance be accessible through the software Spatial Decomposition Tree?
- `IfcSign` instances are contained in the SpatialStructure, hence located according to its `IfcLocalPlacement`. This could contradict their own position through the `IfcLinearPlacement`?

### Expected geometry

![Alt text](Dataset/BC003_Equipment_Signals.png "Expected Geometry - Signals")

![Alt text](Dataset/BC003_Equipment_tramway.png "Expected Geometry - Signals and railway elements")


### Control parameters

The following steps should be performed in order to corroborate that the software is working as expected.

After importing the reference file ([BC003_ALX1_Reference](./Dataset/BC003_ALX1_Reference.ifc)):
- Signals base points shall be the same as presented in the previous table;
- Signals 3D solid shall have `radius=0.05m` and `height=3.50m` ;
- `Traffic_Light01` base point is located at Station `0+052.0866`, distant `2.326m` at the right side of `SAN1_XD-B02` alignment ;
- `Traffic_Light02` base point is located at Station `0+052.0002`, distant `2.006m` at the left side of `SAN1_XG-3eme_Voie` alignment ; 

## Link to requirements

|ID (local)	| Name | Description | Requirements for Appointed Party |
|-|-|-|-| 
| RI 84 | Assemblies |  | RA-75 | IfcElement that are aggregated in another IfcElement shall not be contained using IfcRelContainedInSpatialStructure. | NUL |
|RI 85 | Component placement | Parts of IfcElementAssembly (or other assembled IfcElement) shall be placed relative to the parent's placement. | NIM |
| RI 86 | Unique containment | "Each IfcElement shall be either: - contained in one and only one IfcSpatialStructureElement, or - contained in one and only one IfcLinearPositioningElement." | RA-75 |
|RI 300 | Signals reused geometries | Signal parts geometries shall be mapped (IfcMappedItem) to their matching type geometry | Every signal sharing the same type shall reuse shared geometry defined for the  signal type|
|RI 301 | Signals as assemblies| Signals shall be modeled as an IfcElementAssembly with aggregated post, foundation, mast and signal port| Signal posts shall use parametric/lighweight geometry and avoid heavy tessalated or BRep geometry |
|RI 302 | Signals reused types| Signal parts shall be using IfcElementAssemblyType entities| Signals shall be defined by their type with their characteristics |
|RI 304 | Stationing address | IfcReferents (typed POSITION or STATION) linked to IfcAlignments need a IfcRelPositions relationship | A Linear address shall be known from the alignment it relates to |
|RI 306 | Trackside Signals geometries | Signal masts shall be modeled as IfcColumn with an extruded geometry along the Z axis of the profile (IfcExtrudedAreaSolid), using IfcSweptDiskSolid | A Signal shall be modeled  with a column / 3D solids with some extruded shape |
| RI 314 | Project structure | The only "container" aggregated to the project shall be either IfcSite, IfcFacility, IfcAlignment. Other non-IfcProducts shall be connected to the project with IfcRelDeclares | NIL |
| RI 316 | ElementAssemblies stationing | IfcElementAssembly.SIGNAL shall be linked to IFcReferent.STATION by a IfcRelPositions relationship | A signal assembly should have its stationing defined |


