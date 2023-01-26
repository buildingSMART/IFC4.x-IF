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

...

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
