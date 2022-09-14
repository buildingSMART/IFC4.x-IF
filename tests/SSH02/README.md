# SectionedSolidHorizontal-2

| Test code | Test author             | Test dataset source | Test direction |
|-----------|-------------------------|---------------------|----------------|
| SSH02     | Michelangelo Cianciulli | ACCA                | Export         |



## Intent
This scenario allows testing of a sectioned swept area solid. It uses a changing profile from start to end (same profile but smaller at the end).

<details><summary>Main IFC concept templates involved in this test</summary> 

- Project Global Positioning
- Alignment Layout
- Spatial Decomposition
- Spatial Containment
- Alignment Geometry
- Alignment Geometry Gradient
- Product Geometric Representation
- Body SectionedSolidHorizontal
</details>



## Prerequisites
None



## Test dataset (input)
This test case utilises the dataset collected in the Dataset folder and summarised in the table below.

| Filename(format)                   | Description                                                                                                                                                                                                               |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SectionedSolidHorizontal-2.ifc | **Reference IFC file**. Contains the definition of a sectioned solid horizontal with different profile from start to end and the use of IfcSectionedSolidHorizontal to sweep along the gradient curve of the defined alignment |
| SectionedSolidHorizontal-2.png     | Screenshot of the IFC model                                                                                                                                                                                               |




## Validation criteria
:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules
n.a.


### Informal criteria
n.a


### Expected geometry

<img src="./Dataset/SectionedSolidHorizontal-2.png" width="500"/>


### Control parameters
n.a.