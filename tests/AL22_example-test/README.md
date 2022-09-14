(test template)
# Two railway track alignments without cant

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| AL22      | Evandro Alfieri | RFI                 | Export         |



## Intent
This test case addresses the **export** of the required IFC entities for the exchange of data related to **two railway track alignments without cant**.

<details><summary>Main IFC concept templates involved in this test</summary> 

- Project Global Positioning
- Alignment Layout
- Spatial Decomposition
- Spatial Containment
- Alignment Geometry
- Alignment Geometry Gradient
</details>



## Prerequisites
All validation criteria (and usages) of prerequisites' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| Test code | Test title                     | Comments |
|-----------|--------------------------------|----------|
| PJ01      | Project Setup                  | none     |
| GL01      | Global Positioning RFI dataset | none     |



## Test dataset (input)
This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename              | Type (format) | Description                                                        |
|-----------------------|---------------|--------------------------------------------------------------------|
| LineLayout            | figure (svg)  | Schematic line layout of the test case                             |
| Alignment1_horizontal | csv           | Alignment parameters for horizontal segments of the Primary Route  |
| Alignment2_horizontal | csv           | Alignment parameters for horizontal segments of the Diverted Route |
| Alignment1_vertical   | csv           | Alignment parameters for vertical segments of the Primary Route    |
| Alignment2_vertical   | csv           | Alignment parameters for vertical segments of the Diverted Route   |



## Validation criteria
:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

<details><summary>General</summary>

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  |
|-------------|-------------------------------------------------------------------|-----------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table |

#### Entities Table

| **Element**            | **Attribute**   | **Value**                                               | **Notes** |
|------------------------|-----------------|---------------------------------------------------------|-----------|
| IfcAlignment           | Name            | Alignment 1_Primary route                               |           |
|                        | ObjectType      | Railway track alignment                                 |           |
|                        | PredefinedType  | USERDEFINED                                             |           |
| IfcAlignment           | Name            | Alignment 2_Diverted route                              |           |
|                        | ObjectType      | Railway track alignment                                 |           |
|                        | PredefinedType  | USERDEFINED                                             |           |
| IfcAlignmentHorizontal | Name            | AH1                                                     |           |
| IfcAlignmentVertical   | Name            | AV1                                                     |           |
| IfcAlignmentHorizontal | Name            | AH2                                                     |           |
| IfcAlignmentVertical   | Name            | AV2                                                     |           |
| IfcSite                | Name            | Sito                                                    |           |
|                        | Description     | 'One of the many sites that can be present in the file' |           |
| IfcRailway             | Name            | LO1336                                                  |           |
|                        | Description     | Foligno                                                 |           |
|                        | ObjectType      | Località                                                |           |
|                        | PredefinedType  | USERDEFINED                                             |           |
|                        | CompositionType | ELEMENT                                                 |           |

</details>




<details><summary>Railway alignment (without cant)</summary>

> **Acceptance criteria**: For the **Railway alignment (without cant)** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.

| **RULE ID** | **CRITERIA**                                                    | **VALUE [examples]**                           |
|-------------|-----------------------------------------------------------------|------------------------------------------------|
| SITE_00     | All IfcAlignment shall always be contained in an IfcSite        |                                                |
| ALIG_00     | Alignment layout structure is verified                          | See steps                                      |
| ALIG_01     | Number of alignments contained in file                          | [2]                                            |
| ALIG_02     | Parameters of alignment segments are verified                   | As per Alignment Table                         |
| ALIG_03     | Alignment geometric compliance is verified                      | As per Alignment geometric compliance document |
| DIST_02     | Required precision for length of alignment's segments           | [0,0001] or [1.E-4]                            |
| ANGL_02     | Required precision for angles and slope of alignment's segments | [0,000001] or [1.E-6]                          |


<details><summary>ALIG_00 steps</summary>

| **STEP ID** | **STEP**                                                                                                                                           |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| ALIG_00.1   | Each IfcAlignment must nest exactly 1 IfcAlignmentHorizontal                                                                                       |
| ALIG_00.2   | Each IfcAlignment must nest at most 1 IfcAlignmentVertical                                                                                         |
| ALIG_00.3   | Each IfcAlignment must nest exactly 1 IfcAlignmentVertical                                                                                         |
| ALIG_00.6   | Each IfcAlignmentHorizontal must be nested only by 1 IfcAlignment                                                                                  |
| ALIG_00.7   | Each IfcAlignmentVertical must be nested only by 1 IfcAlignment                                                                                    |
| ALIG_00.9   | Each IfcAlignment must nest only the following entities: IfcAlignmentHorizontal, IfcAlignmentVertical, IfcAlignmentCant, IfcReferent, IfcAlignment |
| ALIG_00.10  | Each IfcAlignmentHorizontal nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentHorizontalSegment         |
| ALIG_00.11  | Each IfcAlignmentVertical nests a list of IfcAlignmentSegment, each of which has DesignParameters typed as IfcAlignmentVerticalSegment             |

</details>

<details><summary>Details for DIST_02 and ANGL_02</summary>

Precision for length (DIST_002) applies to the values of the following attributes:
- `IfcAlignmentHorizontalSegment`.StartPoint
- `IfcAlignmentHorizontalSegment`.SegmentLength
- `IfcAlignmentVerticalSegment`.StartDistAlong
- `IfcAlignmentVerticalSegment`.HorizontalLength
- `IfcAlignmentCantSegment`.StartDistAlong
- `IfcAlignmentCantSegment`.HorizontalLength

Precision for angles and slope (ANGL_002) applies to the values of the following attributes:
- `IfcAlignmentHorizontalSegment`.StartDirection

</details>
</details>




<details><summary>Spatial (De)Composition</summary>

| **RULE ID** | **CRITERIA**                      | **VALUE [examples]**                 |
|-------------|-----------------------------------|--------------------------------------|
| SDEC_01     | Spatial decomposition is verified | As per Spatial (De)Composition Table |

> **Acceptance criteria**: For the **Spatial decomposition** capability, the validation procedure must verify that a Parent Element of the requested type aggregates (via `IfcRelAggregates`) exactly a given number of Child Elements of the requested type, no more and no less.

<details><summary>SDEC_01 details: Spatial decomposition is verified</summary>

> - Given a set of elements taken from the [Spatial (De)Composition Table](#Spatial-(De)Composition-Table)
> - Then the Parent Element, and optionally the Parent Element Type, exists
> - And the Parent Element must aggregate at least a number within [MinSize..MaxSize] of the requested Child Element

</details>

#### Spatial (De)Composition Table

| **Parent Element** | **Parent Element Type** | **Parent Element Name** | **MinSize** | **MaxSize** | **Child Element** | **Child Element Type** | **Child Element Name** |
|--------------------|-------------------------|-------------------------|-------------|-------------|-------------------|------------------------|------------------------|
| IfcProject         |                         | IFC4.3AbRV Project      | 1           | 1           | IfcSite           |                        | Sito                   |
| IfcSite            |                         | Sito                    | 1           | 1           | IfcRailway        |                        | LO1336                 |

**Bullet point example**:
- IfcProject *(Name: IFC4.3AbRV Project)*
  - IfcSite *(Name: Sito)*
    - IfcRailway *(Name: LO1336)*

</details>




<details><summary>Spatial Containment</summary>

| **RULE ID** | **CRITERIA**                    | **VALUE [examples]**             |
|-------------|---------------------------------|----------------------------------|
| SCON_01     | Spatial containment is verified | As per Spatial Containment Table |

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

<details><summary>SCON_01 details: Spatial containment is verified</summary>

> - Given a set of elements taken from the [Spatial Containment Table](#Spatial-Containment-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must contain at least a number within [MinSize..MaxSize] of the requested Element

</details>

#### Spatial Containment Table

| **Spatial Element** | **Spatial Element Type** | **MinSize** | **MaxSize** | **Element**     | **Element Type**        |
|---------------------|--------------------------|-------------|-------------|-----------------|-------------------------|
| IfcSite             |                          | 2           | 2           | IfcAlignment    | Railway track alignment |

**Bullet point example**:

- IfcProject *(Name: IFC4.3AbRV Project)*
  - IfcSite *(Name: Sito)*
    - `IfcAlignment` *(Name: Alignment 1_Primary route)*
    - `IfcAlignment` *(Name: Alignment 2_Diverted route)*
    - IfcRailway *(Name: LO1336)*

</details>


### Informal criteria

...


### Expected geometry

<img src="./Dataset/LineLayout.svg" width="500"/>


### Control parameters

The parameters contained in the following sections are meant to support the validation of the correct creation of the alignment, based on the dataset provided in this test.

**IMPORTANT**: These parameters can be used also to support the **validation of import** into a receiving application. To do so,  `IfcReferent` entities shall be above have to be defined.

<details><summary> Alignment 1_Primary route </summary>

| ID      | CRITERIA                                                            | VALUE        |
|---------|---------------------------------------------------------------------|--------------|
| ALIG_10 | Horizontal Starting point Mileage (pk)                              | 0+000        |
| ALIG_11 | Horizontal Starting point DistAlong                                 | 0.0000       |
| ALIG_12 | Horizontal Starting point X                                         | 452413.9199  |
| ALIG_13 | Horizontal Starting point Y                                         | 4539456.4011 |
| ALIG_14 | Vertical Starting point Mileage                                     | 0+000        |
| ALIG_15 | Vertical Starting point Z                                           | 5.0000       |
| ALIG_16 | Horizontal Ending point Mileage (pk)                                | 0+876.3682   |
| ALIG_17 | Horizontal Ending point DistAlong                                   | 876.3682     |
| ALIG_18 | Horizontal Ending point X                                           | 453202.5241  |
| ALIG_19 | Horizontal Ending point Y                                           | 4539831.9287 |
| ALIG_20 | Vertical Ending point Mileage                                       | 0+876.3682   |
| ALIG_21 | Vertical Ending point Z                                             | 2.0000       |
| ALIG_22 | Total 2D length of alignment (horizontal projection)                | 876.3682     |
| ALIG_23 | Total 3D length of alignment                                        | 876.3819     |
| ALIG_24 | Height difference between start and end point of alignment 3D curve | -3.0000      |

</details>


<details><summary> Alignment 2_Diverted route </summary>

| ID      | CRITERIA                                                            | VALUE        |
|---------|---------------------------------------------------------------------|--------------|
| ALIG_10 | Horizontal Starting point Mileage (pk)                              | 0+000        |
| ALIG_11 | Horizontal Starting point DistAlong                                 | 0.0000       |
| ALIG_12 | Horizontal Starting point X                                         | 452460.8898  |
| ALIG_13 | Horizontal Starting point Y                                         | 4539473.5425 |
| ALIG_14 | Vertical Starting point Mileage                                     | 0+000        |
| ALIG_15 | Vertical Starting point Z                                           | 5.0000       |
| ALIG_16 | Horizontal Ending point Mileage (pk)                                | 0+828.0965   |
| ALIG_17 | Horizontal Ending point DistAlong                                   | 828.0965     |
| ALIG_18 | Horizontal Ending point X                                           | 453208.8311  |
| ALIG_19 | Horizontal Ending point Y                                           | 4539818.3191 |
| ALIG_20 | Vertical Ending point Mileage                                       | 0+828.0965   |
| ALIG_21 | Vertical Ending point Z                                             | 2.0000       |
| ALIG_22 | Total 2D length of alignment (horizontal projection)                | 828.0965     |
| ALIG_23 | Total 3D length of alignment                                        | 828.1099     |
| ALIG_24 | Height difference between start and end point of alignment 3D curve | -3.0000      |

</details>

