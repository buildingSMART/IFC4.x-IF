# This is the title of the test

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| ABCD123   | Colonel Mustard | bSI                 | Export/Import  |

>**After completing the test description delete all the instructions (in Italic, marked with :information_source:). Including this one.**

## Intent
>:information_source: *describe the intention of the test, and (optionally) list the main IFC concepts covered.*

...

<details><summary>Main IFC concept involved in this test</summary> 

- Project Global Positioning
- Alignment Layout
- Spatial Decomposition
- ...
</details>



## Prerequisites
>:information_source: *list the tests that must be passed before performing this test. If not applicable, delete the whole "Prerequisites" section.*

All validation criteria (and usages) of prerequisites' tests shall be **verified for this test too** (regression test principle). Prerequisites for the present test case are listed below.

| Test code | Test title                     | Comments |
|-----------|--------------------------------|----------|
| PJ01      | Project Setup                  | none     |
| GL01      | Global Positioning RFI dataset | none     |



## Test dataset (input)
>:information_source: *list the input for the test. May include a reference IFC file. If dataset requires further description use the `README.md` in the Dataset folder of this test*

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| LineLayout.svg            | Schematic line layout of the test case                             |
| Alignment1_horizontal.csv | Alignment parameters for horizontal segments of the Primary Route  |
| Alignment1.ifc            | **Reference IFC file**. Contains the alignment curve for this test |


## Validation criteria
>:information_source: *list the validation criteria to define the success of the test. These may include:*
>- ***Formal rules**, reference to bSI Validation Service rules (or to an IDS file)*
>- ***Informal criteria**, mainly aimed to verify “Required SW features” (see Step 3)*
>- ***Expected geometry**, to provide a visual idea of the expected result*
>- ***Control parameters**, to check the content of the model against the given dataset*

:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules
>:information_source: *add link to bSI Validation Service rules or to IDS file/bSDD domain*

#### IFC standard (schema and specification)
When validated using the bSI Validation Service, the IFC must pass:
- Syntax & Schema check
- All following rules:
  - ALB002 - Alignment layout
  - ALB003 - Alignment directions
  - TBD000 - Alignment shape representation
  - TBD000 - Stationing along alignment

>:information_source: *above is just an example of how to reference rules form the bSI Validation Service. Use a placeholder when a rule is not yet defined*

#### Test case-specific checks
>:information_source: *list or copy-paste the requirements in plain language, and **point to the IDS that formalises them - where applicable***

Link to IDS file: [ABCD123.ids]() :construction:

- There must be 1 instance(s) of IfcAlignment and must be named `Track alignment`,its PredefinedType must be `USERDEFINED` and its ObjectType must be `Railway track alignment`
- There must be 1 instance(s) of IfcAlignmentHorizontal and must be named `H1`
- There must be 1 instance(s) of IfcAlignmentVertical and must be named `V1`
- There must be 1 instance(s) of IfcAlignmentCant and must be named `C1`
- There must be 2 instance(s) of IfcSignal and must be named `Route Indicator_01`, `Route Indicator_02`
- The horizontal layout must include only the following types of segments: Line, Circular Arc, Clothoid
   - (or one step closer to IFC) The PredefinedType of IfcAlignmentHorizontalSegment must be `LINE` or `CIRCULARARC` or `CLOTHOID`

>:information_source: *above is just an example of plain language requirements. Note how the last one can be either listed as IFC-agnostic requirement, or can be specified in an IFC-fashioned way. It's up to the test case owner to decide.*

### Informal criteria
>:information_source: *list informal criteria, or refer to external documentation*

...

### Expected geometry
>:information_source: *add image of the expected geometry. Upload the jpeg/png file in the Dataset folder of this test*

...

### Control parameters
>:information_source: *add parameters/data that can be use to support the validation of import into a receiving application. Example: total lenght of one alignment, coordinates for end point of the alignment.*

...

## Link to requirements
>:information_source: *list requirements covered by this test, or refer to external documentation*

...
