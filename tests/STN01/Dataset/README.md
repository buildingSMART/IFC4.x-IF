# BC002 Stationing on alignment dataset "A"

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| STN01     | Ciro Vendrame   | RFI                 | Export         |

## Overview

<img src="./LineLayout.svg" width="500" />

| Info                         |                                           |
|------------------------------|-------------------------------------------|
| Number of alignment(s)       | 1                                         |
| Vertical Measurement         | Lower Rail                                |
| Properties of segments       | no                                        |
| Horizontal layout            | Line, Circular Arc, Clothoid              |
| Vertical layout              | Constant Gradient, Circular Arc           |
| Cant layout                  | Constant Cant, Linear Transition          |
| Broken chainage              | No                                        |
| IFC reference file available | # to check                                |

## Model Dataset
This dataset is an example of what the file “F02: IFC with alignment and signal” model could contain.
It represents one alignment with cant on which two signals are placed.

| Filename                                             | Description                                                                                       |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| [LineLayout](./LineLayout.svg)                       | Schematic [line layout](#Line-layout) of the test case                                            |
| [Alignment_horizontal](./Alignment_horizontal.csv)   | [Alignment parameters for horizontal segments](#Alignment-parameters-for-horizontal-segments)     |
| [Alignment_vertical](./Alignment_vertical.csv)       | [Alignment parameters for vertical segments](#Alignment-parameters-for-vertical-segments)         |
| [Alignment cant](./Alignment_cant.csv)               | [Alignment parameters for cant segments](#Alignment-parameters-for-cant-segments)
| [Alignment_exchange](./Alignment_exchange.xml)       |  Alignment description in xml
| [Alignment_2D_with_stationing_values](./Alignment_2D_with_stationing_values.dxf) | 2D model of the alignment with mileage referents
| [Alignment_3D_with_signals](./Alignment_3D_with_signals.dxf)       | 3D model of the alignment with 2 signals
| [Alignment_stationing_values_by_pace](./Alignment_stationing_values_by_pace.csv) | Alignment stationing values by pace
| [Alignment_stationing_values_by_segment_type](./Alignment_stationing_values_by_segment_type.csv) | Alignment stationing values by segment type
| [Signals_positions](./Signal_position.csv)           | [Signals positions parameters](#Position-parameters-for-signals)
| [Signals_stationing_values](./Signals_positions.csv) | [Signals stationing values](#Stationing-values-of-the-Signals) along the alignment
| [Geographic_Coordinate_System](./Geographic_Coordinate_System.pdf) | [Geographic Coordinate System properties](#Geographic-Coordinate-System-properties)

## Content

- [BC002 Stationing on alignment dataset "A"](#bc002-stationing-on-alignment-dataset-a)
  - [Overview](#overview)
  - [Model Dataset](#model-dataset)
  - [Content](#content)
  - [Line layout](#line-layout)
  - [Alignment parameters for horizontal segments](#alignment-parameters-for-horizontal-segments)
  - [Alignment parameters for vertical segments](#alignment-parameters-for-vertical-segments)
  - [Alignment parameters for cant segments](#alignment-parameters-for-cant-segments)
  - [Signals](#signals)
    - [Signals shape](#signals-shape)
    - [Signals position parameters](#signals-position-parameters)
  - [Stationing](#stationing)
    - [Stationing values according to national conventions](#stationing-values-according-to-national-conventions)
    - [Stationing values of the horizontal segments](#stationing-values-of-the-horizontal-segments)
    - [Stationing values of the vertical segments](#stationing-values-of-the-vertical-segments)
    - [Stationing values of signals](#stationing-values-of-signals)


## Line layout

The line for the test is made of one alignment (*IfcAlignment*):


<img src="./LineLayout.svg" height="600"/>

The **Alignment** is described through its **horizontal**, **vertical** and **cant** profiles.

All parameters of the segments, for both alignments, are detailed below in:


## Alignment parameters for horizontal segments

The horizontal profile is described using a CSV file and is made of the following 9 horizontal segments.
The column headers match the IFC attributes for `IfcAlignmentHorizontalSegment`. Refers to the standard's documentation for their description.

| Entity                        | PredefinedType | Name | Start Point X | Start Point Y | Start Direction | Start Radius of Curvature | End Radius of Curvature | Segment Length |
|-------------------------------|----------------|------|---------------|---------------|-----------------|---------------------------|-------------------------|----------------|
| IfcAlignmentHorizontalSegment | LINE           | H1   | 452270,1883   | 4539403,9474  | 0,349924146     | 0                         | 0                       | 387,7233       |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H2   | 452634,415    | 4539536,8692  | 0,349924146     | 0                         | 1000                    | 40             |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H3   | 452671,898    | 4539550,8322  | 0,369924153     | 1000                      | 1000                    | 193,4645       |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H4   | 452844,4075   | 4539637,7367  | 0,563388612     | 1000                      | 0                       | 40             |
| IfcAlignmentHorizontalSegment | LINE           | H5   | 452877,9371   | 4539659,5475  | 0,583388619     | 0                         | 0                       | 38,9815        |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H6   | 452910,4711   | 4539681,0207  | 0,583388619     | 0                         | -1000                   | 40             |
| IfcAlignmentHorizontalSegment | CIRCULARARC    | H7   | 452944,0007   | 4539702,8314  | 0,563388612     | -1000                     | -1000                   | 109,4317       |
| IfcAlignmentHorizontalSegment | CLOTHOID       | H8   | 453039,5298   | 4539756,1001  | 0,453956871     | -1000                     | 0                       | 40             |
| IfcAlignmentHorizontalSegment | LINE           | H9   | 453075,7086   | 4539773,1600  | 0,433956864     | 0                         | 0                       | 139,7711       |


**NOTE**:
- All distances are in meters
- All angles are in radian (see note below)
- All the coordinates are defined using the UTM Coordinate System (EPSG:3065)
- The *Radius Of Curvature* is considered positive when the curve is to the right, and negative when it is to the left

**IMPORTANT**:

When using IFC to exchange information, the file must respect IFC convention [marked as ii) in the figure below].
This implies a right-hand cartesian coordinate systems; and angles are measured from x-axis, counter clock-wise.

<p align="center">
    <img src="SurveyToIFCangleConvention.png" height="500"/>
</p>



## Alignment parameters for vertical segments

The vertical layout of the alignment (both for Alignment 1 and Alignment 2) is described using a CSV file. The column headers match the IFC attributes for `IfcAlignmentVerticalSegment`. Refers to the standard's documentation for their description.


Alignment 2_Diverted route

| Entity                      | PredefinedType   | Name | Start Dist Along | Horizontal Length | Start Height | Start Gradient | End Gradient | RadiusOfCurvature |
|-----------------------------|------------------|------|------------------|-------------------|--------------|----------------|--------------|-------------------|
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V1   | 0                | 0                 | 5            | 0              | 0            |                   |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V2   | 277.0671         | 49.8646           | 5            | 0              | -0.009973    | 5000              |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V3   | 326.9317         | 250.9366          | 4.7513       | -0.009973      | -0.009973    |                   |
| IfcAlignmentVerticalSegment | CIRCULARARC      | V4   | 577.8683         | 49.8646           | 2.2487       | -0.009973      | 0            | -5000             |
| IfcAlignmentVerticalSegment | CONSTANTGRADIENT | V5   | 627.7329         | 200.3636          | 2            | 0              | 0            |                   |

**NOTE**:
- All distances are in meters
- All angles are in gradian
- The radius (*RadiusOfCurvature*) is considered positive when the curve is a *crest*, and negative when it is a *sag* (opposite to IFC).


## Alignment parameters for cant segments

## Signals

### Signals shape

### Signals position parameters

## Stationing

### Stationing values according to national conventions

### Stationing values of the horizontal segments

### Stationing values of the vertical segments

### Stationing values of signals