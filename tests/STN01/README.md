# Stationing on alignment without broken chainage

| Test code | Test author | Test dataset source | Test direction |
| --------- | ----------- | ------------------- | -------------- |
| STN01     | WG4         | RFI                 | Export         |



## Intent
This test case addresses the **export** of the required IFC entities for the exchange of data related to **Stationing on alignment without broken chainage**.

<details><summary>Main IFC concept involved in this test</summary> 

- Project Global Positioning
- Alignment Layout
- Spatial Decomposition
- Spatial Containment
- Alignment Geometry
- Alignment Geometry Gradient
- Alignment Geometry Cant
- Product Linear Placement
- Product Local Placement
- Product Shape 
</details>


## Prerequisites
All validation criteria (and usages) of prerequisites' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| Test code | Test title                     | Comments |
| --------- | ------------------------------ | -------- |
| PJ01      | Project Setup                  | none     |
| GL01      | Global Positioning RFI dataset | none     |


## Test dataset (input)

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)                         | Description                                                                        |
| ----------------------------------------- | ---------------------------------------------------------------------------------- |
| LineLayout.svg                            | Schematic line layout of the test case                                             |
| Alignment_horizontal.csv                  | Alignment parameters for horizontal segments                                       |
| Alignment_vertical.csv                    | Alignment parameters for vertical segments                                         |
| Alignment_cant.csv                        | Alignment parameters for cant segments                                             |
| Alignment_exchange.xml                    | Alignment description in LandXML file format                                       |
| Alignment_2D_with_stationing_values.dxf   | 2D CAD model of the alignment with mileage referents (dxf file)                    |
| Alignment_3D_with_signals.dxf             | 3D CAD model of the alignment with 2 signals (dxf file)                            |
| Stationing_values.csv                     | Stationing values according to national conventions                                |
| Stationing_values_horizontal_segments.csv | Stationing values of the horizontal segments                                       |
| Stationing_values_vertical_segments.csv   | Stationing values of the vertical segments                                         |
| Signal_3D.dxf                             | 3D CAD model of the signal (dxf file)                                              |
| Signals_positions.csv                     | Signals positions parameters                                                       |
| Stationing_values_signals.csv             | Stationing values of the signals                                                   |
| Geographic_Coordinate_System.pdf          | Geographic Coordinate System properties                                            |
| Ifc file  **WIP**                         | **Reference IFC file**. Contains the alignment curve with stationing and 2 signals |


## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

<details><summary>General</summary>

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  |
| ----------- | ----------------------------------------------------------------- | --------------------- |
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table |

#### Entities Table

| **Element**            | **Attribute**  | **Value**               | **Notes** |
| ---------------------- | -------------- | ----------------------- | --------- |
| IfcAlignment           | ObjectType     | Railway track alignment |           |
|                        | PredefinedType | USERDEFINED             |           |
| IfcAlignmentHorizontal | Name           | H1                      |           |
| IfcAlignmentVertical   | Name           | V1                      |           |
| IfcAlignmentCant       | Name           | C1                      |           |
| IfcSignal              | Name           | Route Indicator_01      |           |

</details>

<details><summary>Railway alignment with cant</summary>

> **Acceptance criteria**: For the **Railway alignment with cant** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.

| **bSI RULE ID** | **Project RULE ID** | **Rule Type** | **CRITERIA**                       | VALUE [examples] |
| --------------- | ------------------- | ------------- | ---------------------------------- | ---------------- |
| WIP             | RI-6                | Gherkin       | Alignment layout in IFC            | WIP              |
| WIP             | RI-8                | Gherkin       | Alignment horizontal common in IFC | WIP              |
| WIP             | RI-8                | IDS           | Alignment horizontal common in IFC | WIP              |
| WIP             | RI-11               | Gherkin       | Alignment vertical common in IFC   | WIP              |
| WIP             | RI-13               | Gherkin       | Alignment cant common in IFC       | WIP              |
</details>

<details><summary>Stationing</summary>

> **Acceptance criteria**: For the **Stationing** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.

| **bSI RULE ID** | **Project RULE ID** | **Rule Type** | **CRITERIA**         | VALUE [examples] |
| --------------- | ------------------- | ------------- | -------------------- | ---------------- |
| WIP             | RI-15               | Gherkin       | Start station in IFC | WIP              |
>
> </details>

</details>

### Informal criteria

Check  if the signals are facing opposite direction.

Check  if the signals are placed on the correct side of the railway.


<p align="center">
    <img src="./Dataset/Signals_on_alignment.svg" height="500"/>
</p>

 <p align="center">
 Overall view of Route Indicator_01 and Route Indicator_02
 </p>
<br/>

<p align="center">
    <img src="./Dataset/Route_indicator_01_top.jpg" height="335"/>
</p>

 <p align="center">
 Route Indicator_01 top view
 </p>
<br/>

  <p align="center">
    <img src="./Dataset/Route_indicator_02_top.jpg" height="335"/>
</p>

 <p align="center">
 Route Indicator_02 top view
 </p>
 <br/>

### Expected geometry
>:information_source: *add image of the expected geometry. Upload the jpeg/png file in the Dataset folder of this test*

...


### Control parameters
>:information_source: *add link to bSI Validation Service rules or to IDS file/bSDD domain*

...

## Link to requirements
>:information_source: *list requirements covered by this test, or refer to external documentation*

...



