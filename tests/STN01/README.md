# Stationing on alignment without broken chainage

| Test code | Test author   | Test dataset source | Test direction |
| --------- | ------------- | ------------------- | -------------- |
| STN01     | Ciro Vendrame | RFI                 | Export         |



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


## Validation criteria

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules

#### IFC standard (schema and specification)

When validated using the bSI Validation Service, the IFC must pass:
- Syntax & Schema check
- All following rules:
  - ALB002 - Alignment layout (RI-6)
  - ALB003 - Alignment directions
  - TBD000 - Alignment shape representation (RI-5, RI-9, RI-10, RI-12, RI-14)
  - TBD000 - Stationing along alignment (RI-7)

#### Test case-specific checks

Link to IDS file: [STN01.ids](./Dataset/STN01.ids)

- (RI-18) Each IfcProduct (and subtypes) must have the attribute `Name` not null and not empty
- (RI-4) An IfcProject must have the attribute `Description` not null and not empty
- There must be 1 instance(s) of IfcAlignment and must be named `Track alignment`,its PredefinedType must be `USERDEFINED` and its ObjectType must be `Railway track alignment`
- There must be 1 instance(s) of IfcAlignmentHorizontal and must be named `H1`
- There must be 1 instance(s) of IfcAlignmentVertical and must be named `V1`
- There must be 1 instance(s) of IfcAlignmentCant and must be named `C1`
- There must be 2 instance(s) of IfcSignal and must be named `Route Indicator_01`, `Route Indicator_02`
- (RI-8) The horizontal layout must include only the following types of segments: Line, Circular Arc, Clothoid
  - (or one step closer to IFC) The PredefinedType of IfcAlignmentHorizontalSegment must be `LINE` or `CIRCULARARC` or `CLOTHOID`
- (RI-11) The vertical layout must include only the following types of segments: Constant Gradient, Circular Arc
- (RI-13) The cant layout must include only the following types of segments: Constant Cant, Linear Transition
- (RI-19) An IfcSignal shall have 'Body' geometry.
  
### Informal criteria

1. Check if the signals are facing opposite direction.
2. Check if the signals are placed on the correct side of the railway.
3. (RI-15) The start station of the alignment is *-153.1 m*
5. (RI-16) Check that the distance between one reference marker and the next one is 50 m, except for the first one


<p align="center">
    <img src="./Dataset/Signals_on_alignment.svg" height="500"/>
</p>

 <p align="center">
 Overall view of Route Indicator_01 and Route Indicator_02
 </p>
<br/>

<p align="center">
    <img src="./Dataset/Route_indicator_01_top.jpg" height="400"/>
</p>

 <p align="center">
 Route Indicator_01 top view
 </p>
<br/>

  <p align="center">
    <img src="./Dataset/Route_indicator_02_top.jpg" height="490"/>
</p>

 <p align="center">
 Route Indicator_02 top view
 </p>
 <br/>

### Expected geometry


<p align="center">
    <img src="./Dataset/Expected_geometry.jpg" height="450"/>
</p>


### Control parameters

1. The total 2D length of the track alignment (horizontal projection) is 1029.3721 meters
2. The total 3D length of the track alignment is 1029.3861 meters
3. The ending point of the track alignment has coordinate (x, y, z) 453202.5241, 4539831.9287, 2.0000
4. The ending point of the track alignment has mileage (pk)	0+876.2721
5. The vertical height difference between starting and ending points of the track alignment 3D curve is -3.0000 meters

## Link to requirements

[BC-002 Requirements.xlsx](./Dataset/BC-002.xlsx)