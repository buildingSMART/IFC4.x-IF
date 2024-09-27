# 5 Stationing tests on nodes - BC003-ALX3a

| Test code  | Test author     | Test dataset source | Test direction |
|------------|-----------------|---------------------|----------------|
|BC003-ALX3a | Joao Correa     | MINnD               | Import/Export  |


## Intent

This Test belongs to a series of Tests that share a dataset from the same project as a business case. 
The series of tests that belong to this Business Case are listed as follows:

| Test code | Test name     | 
|-----------|-----------------|
| PS01      | Project setup with georeferencing |
| AL01      | Multiple alignments of railway line |
| RR01      | Railway track elements validation |
| ALX1      | Stationing tests on equipment (punctual)|
| ALX2      | Stationing tests on nodes (punctual) |
| **ALX3a**     | **Alignment reference check on linear elements (early design)** |
| ALX3b     | Alignment reference check on linear elements (detailed design, precast) |
| ALX3c     | Alignment reference check on linear elements (detailed design, case-in-place) |
| NE01      | Network integrity/continuity check on linear elements |
| ALX4      | Stationing tests on cable joints (punctual) |
| NE02      | Cable routing |

## IFC concepts involved in this test

The following test intends to address the use case where the cable infrastructure is in concrete, following the tracks:
![ALX3a - cabling infrastructure](./BC003_ALX3a_cabling_infrastructure.jpg)


The following diagram represents the rationale used for this test: the cabling supporting structure follows the track alignment shifted from varying distances.
![ALX3a - rationale](./BC003-ALX3a_rationale.png)

The cabling supporting structure is represented by a swept volume using the following 2D profile:
![ALX3a - 2D profile](./BC003-ALX3a_2Dprofile.png)


The following diagram represents the entities involved in this test.
![ALX3a - involved entities](./BC003_ALX3a_diagram.png)

## Prerequisites

The test plan builds upon the previous test plans. All requirements presented in previous test plans must be met.

## Test dataset (input)

This test case utilises the dataset collected in the Dataset folder and is summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**


In addition, the outcome of the previous tests shall be used as input of this test.

## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:

- Syntax & Schema check


#### Test case-specific checks

:hourglass:

#### Not covered by the IDS file (must be checked otherwise):

:hourglass:

### Informal criteria

Open questions:
- Should we use some `IfcRelNests` relationship between Alignments?
- Some Concept Template seems required in order use `IfcRelPositions` to link the cable carrier to the alignment?
- The cable carrier needs to be spatially contained in the IfcRailway, but is located w.r.t. some alignment. Does it introduce some potential inconstistancy?  

### Expected geometry

![Expected Geometry - extruded cabling support](./BC003_ALX3a_extruded_cabling_support.png)


### Control parameters

The following steps should be performed in order to corroborate that the software is working as expected.

:hourglass:


## Link to requirements

|ID (local)	| Name | Description | Requirements for Appointed Party |
|-|-|-|-| 
| RI 86 | Unique containment | "Each IfcElement shall be either: - contained in one and only one IfcSpatialStructureElement, or - contained in one and only one IfcLinearPositioningElement." | RA-75 |
| RI 311 | Alignement extruded geometry placement | A IfcCableCarrierSement which geometry is a IfcSectionSolidHorizontal  shall be using the same IfcObjectPlacement as the IfcAlignment it is positioned along | NIL|
| RI 312 | Offset alignment placement | An IfcAlignment which geometry is a IfcOffsetCurveByDistances shall use the same IfcLocalPlacement as the IfcAlignment is relates to | NIL|
| RI 313 | Extruded CableCarrier positioning | A IfcSectionedSolidHorizontal geometry used for a IfcCableCarrierElement  positioned relatively from an IfcAlignment shall use its IfcLocalPlacement | NIL |
| RI 314 | Project structure | The only "container" aggregated to the project shall be either IfcSite, IfcFacility, IfcAlignment. Other non-IfcProducts shall be connected to the project with IfcRelDeclares | NIL |
| RI 315 | Elements referencing in Spatial structures | If IfcElements are positioned wrt IfcPositioning elements, then they must be also referenced (instead of aggregated) into a IfcSpatialStructure element | NIL |

