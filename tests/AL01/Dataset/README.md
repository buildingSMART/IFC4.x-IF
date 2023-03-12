# Test dataset

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| AL01     | Chi Zhang   | SBB                 | Export         |

## Content
- [Test dataset](#test-dataset)
  - [Content](#content)
  - [Overview](#overview)
  - [Model Dataset](#model-dataset)
  - [Alignment](#alignment)
    - [Alignment parameters for horizontal segments](#alignment-parameters-for-horizontal-segments)
    - [Alignment parameters for vertical segments](#alignment-parameters-for-vertical-segments)
    - [Alignment parameters for cant segments](#alignment-parameters-for-cant-segments)


## Overview

<img src="Alignment_visualization.PNG" width="500" />

| Info                         |                                           |
|------------------------------|-------------------------------------------|
| Number of alignment(s)       | 11                                        |
| Vertical Measurement         | Track axis (center line)                  |
| Properties of segments       | no                                        |
| Horizontal layout            | Line, Circular Arc, Clothoid              |
| Vertical layout              | Constant Gradient, Circular Arc           |
| Cant layout                  | Constant Cant, Linear Transition          |
| Broken chainage              | No                                        |
| IFC reference file available | **WIP**                                   |

## Model Dataset
This dataset has 11 alignments, which in total are around 18 km long.

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| [BC001_Alignment.xml](./BC001_Alignment.xml)    |    Data containing track alignments in LandXML format                                   |
| [BC001_Alignment.dwg](./BC001_Alignment.dwg)     |    Data containing track alignments in DWG format                                 |
| BC001_Alignment(Reference).ifc    |    Data containing track alignments in IFC 4.3                                  |


## Alignment

The **Alignment** is described through its **horizontal**, **vertical** and **cant** layouts. They are all described in the LandXML file.
In LandXML, each alignment is made as an instance of "Alignment". For example:

https://github.com/bSI-RailwayRoom/IFC4.x-IF/blob/f6e0ec9875f7e0daf6565bd7e3c8a2cd675a97ab/tests/AL01/Dataset/BC001_Alignment.xml#L9

This defines an alignment object, which has name "A50034A" and start station of 0.000000. It should be created as an IfcAlignment with Name set to "A50034A" and start station (using IfcReferent) set to 0..
### Alignment parameters for horizontal segments

The horizontal profile is described in LandXML using "CoordGeom". Three kinds of segments are used: "Curve", which is an CIRCULARARC in IFC, "Line", which is LINE in IFC, and "Spiral", which in this case is CLOTHOID in IFC. For examples:

(https://github.com/bSI-RailwayRoom/IFC4.x-IF/blob/f6e0ec9875f7e0daf6565bd7e3c8a2cd675a97ab/tests/AL01/Dataset/BC001_Alignment.xml#L41-L54)

This defines one LINE segment, one CLOTHOID segment and one CIRCULARARC with geometric parameters and coordinates.

**IMPORTANT**:

When using IFC to exchange information, the file must respect IFC convention [marked as ii) in the figure below.
This implies a right-hand cartesian coordinate systems; and angles are measured from x-axis, counter clock-wise.

<p align="center">
    <img src="SurveyToIFCangleConvention.png" height="500"/>
</p>

### Alignment parameters for vertical segments

The vertical profile is described in LandXML as "Profile". An fundamental difference with IFC is that vertical layout is described using PVI, which is the point of intersection of the two adjacent grade lines. They must be converted to a segment-based representation in IFC.

https://github.com/bSI-RailwayRoom/IFC4.x-IF/blob/f6e0ec9875f7e0daf6565bd7e3c8a2cd675a97ab/tests/AL01/Dataset/BC001_Alignment.xml#L663-L665

For example, this section of data defines two adjacent grade lines by three points and the radius of rounding between them.

### Alignment parameters for cant segments

The cant profile is defined by "Cant" in LandXML. Unlike in IFC, cant is defined by cant values based on stationing. For example, the following section describes cant values based on two stations, which can be represented as a CONSTANTCANT segment in IFC.

https://github.com/bSI-RailwayRoom/IFC4.x-IF/blob/f6e0ec9875f7e0daf6565bd7e3c8a2cd675a97ab/tests/AL01/Dataset/BC001_Alignment.xml#L513-L514



