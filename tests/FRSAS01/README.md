# FixedReferenceSweptAreaSolid-1

| Test code | Test author             | Test dataset source | Test direction |
|-----------|-------------------------|---------------------|----------------|
| FRSAS01   | Michelangelo Cianciulli | ACCA                | Export         |



## Intent
This scenario allows testing of a fixed reference swept area solid using IfcFixedReferenceSweptAreaSolid. It will be changed with the new proposed IfcDirectrixDerivedReferenceSweptAreaSolid when the new release candidate standard will be available.

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
| FixedReferenceSweptAreaSolid-1.ifc | **Reference IFC file**. Contains the definition of a simple profile and the use of IfcFixedReferenceSweptAreaSolid to sweep along the gradient curve of the defined alignment |
| FixedReferenceSweptAreaSolid-1.png | Screenshot of the IFC model                                                                                                                                                                                               |




## Validation criteria
:zap: For this test case to be considered passed, **all criteria listed in this section**, and **the ones of prerequisites tests** shall be verified. :zap:

### Formal rules
n.a.


### Informal criteria
n.a


### Expected geometry

<img src="./Dataset/FixedReferenceSweptAreaSolid-1.png" width="500"/>


### Control parameters
n.a.