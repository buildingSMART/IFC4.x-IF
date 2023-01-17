# Stationing on one alignment-1

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| STN01     | WP4             | RFI                 | Export         |



## Intent
This test case addresses the **export** of the required IFC entities for the exchange of data related to **Stationing on one alignment-1**.

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
>:information_source: *list the tests that must be passed before performing this test. If not applicable, delete the whole "Prerequisites" section.*

All validation criteria (and usages) of prerequisites' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| Test code | Test title                         | Comments |
|-----------|------------------------------------|----------|
| PJ01      | Project Setup                      | none     |
| GL01      | Global Positioning RFI dataset     | none     |


## Test dataset (input)
>:information_source: *list the input for the test. May include a reference IFC file. If dataset requires further description use the `README.md` in the Dataset folder of this test*

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)                                    | Description                                                        |
|------------------------------------------------------|--------------------------------------------------------------------|
| LineLayout.svg                                       | Schematic line layout of the test case                             |
| Alignment_horizontal.csv                             | Alignment parameters for horizontal segments                       |
| Alignment_vertical.csv                               | Alignment parameters for vertical segments                         |
| Alignment_cant.csv                                   | Alignment parameters for cant segments                             |
| Alignment_exchange.xml                               | Alignment description in LandXML file format                       |
| Alignment_2D_with_stationing_values.dxf              | 2D CAD model of the alignment with mileage referents (dxf file)    |
| Alignment_3D_with_signals.dxf                        | 3D CAD model of the alignment with 2 signals (dxf file)            |
| Stationing_values.csv                                | Stationing values according to national conventions                |
| Stationing_values_horizontal_segments.csv            | Stationing values of the horizontal segments                       |
| Stationing_values_vertical_segments.csv              | Stationing values of the vertical segments                         |
| Signal_3D.dxf                                        | 3D CAD model of the signal (dxf file)                              | 
| Signals_positions.csv                                | Signals positions parameters                                       |
| Stationing_values_signals.csv                        | Stationing values of the signals                                   |
| Geographic_Coordinate_System.pdf                     | Geographic Coordinate System properties                            |
| Ifc file  **wIP**                                    | **Reference IFC file**. Contains the alignment curve with stationing and 2 signals for this test |


## Validation criteria
>:information_source: *list the validation criteria to define the success of the test. These may include:*
>- ***Formal rules**, reference to bSI Validation Service rules (or to an IDS file)*
>- ***Informal criteria**, mainly aimed to verify “Required SW features” (see Step 3)*
>- ***Expected geometry**, to provide a visual idea of the expected result*
>- ***Control parameters**, to check the content of the model against the given dataset*
+
:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules
>:information_source: *add link to bSI Validation Service rules or to IDS file/bSDD domain*


<details><summary>General</summary>

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  |
|-------------|-------------------------------------------------------------------|-----------------------|
| GENE_00     | All validation criteria of precondition's tests shall be verified |                       |
| GENE_01     | All requested entities (and attributes) exist in file             | As per Entities Table |

#### Entities Table

| **Element**            | **Attribute**   | **Value**                                               | **Notes** |
|------------------------|-----------------|---------------------------------------------------------|-----------|


</details>

<details><summary>Stationing </summary>

> **Acceptance criteria**: For the **Railway alignment ** capability, the validation procedure must verify that **all** the following validation criteria are satisfied.

| **RULE ID** | **CRITERIA**                                                      | **VALUE [examples]**  |
|-------------|-------------------------------------------------------------------|-----------------------|
| RI-6        | Alignment layout in IFC                                           |**WIP**                |
| RI-8        | Alignment horizontal common in IFC                                |**WIP**                |
| RI-11       | Alignment vertical common in IFC                                  |**WIP**                |
| RI-13       | Alignment cant common in IFC                                      |**WIP**                |
| RI-15       | Start station in IFC                                              |**WIP**                |

</details>


</details>

### Informal criteria
>:information_source: *list informal criteria, or refer to external documentation*

...

### Expected geometry
>:information_source: *add image of the expected geometry. Upload the jpeg/png file in the Dataset folder of this test*

[Alignment_3D_with_signals](./Dataset/Alignment_3D_with_signals.dxf)   
3D CAD model of the alignment with 2 signals (dxf file)


<p align="center">
    <img src="./Dataset/Signals_on_alignment.svg" height="500"/>
</p>


### Control parameters
>:information_source: *add link to bSI Validation Service rules or to IDS file/bSDD domain*

...

## Link to requirements
>:information_source: *list requirements covered by this test, or refer to external documentation*

...



