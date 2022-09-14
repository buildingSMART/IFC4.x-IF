# IFC4.x-IF
*IFC4.x Implementers Forum*

<div align="center">
<img src="./IFC4.x-IF_approach.png" width="500"/>
</div>

## Approach
The Forum is part of a larger ecosystem, into which interacts with other buildingSMART initiatives and solutions.

- Primary goal of the software vendors joining the forum is to find agreements on implementations. These agreements are captured in formal, computer-interpretable rules (also human-readable)
- The same kind rules can be made by other bSI initiatives (i.e. Projects). All the rules are included in the bSI Validation Service
- bSI Projects can create Test cases, to challenge the IFC standard on a specific scenario. These tests may reference some of the available rules
- In this way, when a software vendor take a test and produce an IFC file, this can be automatically checked using the bSI Validation Service

**Test creation**
A Test case is created following a provided template. It includes: test instructions, test dataset, validation criteria, and optionally a reference IFC file.

➡ [Go to the list of available tests](./tests/)

**Validation**
Validation depends on the type of test, and can be more or less automated. When done against an IFC file, the validation shall ensure that the file is syntactically, structurally, and semantically, correct. It can be done also against other test evidence - produced to demonstrate the fulfillment of validation criteria.

