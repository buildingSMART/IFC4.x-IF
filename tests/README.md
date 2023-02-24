# Tests

## How the tests are structured
Each test is structured as follows:

0. **Test title and metadata** (test code, author, dataset source, etc.)
1. **Intent**, a summary of the test. It includes:
   - A list of main IFC concept templates involved in the test
2. **Prerequisites**, a list of test that shall be passed before taking this test
3. **Test dataset (input)**, a list of files supporting the test. May include a **Reference IFC file**
4. **Validation criteria**, all the criteria that are used to validate the success of the test. It includes:
   - **Formal rules**
     - **IFC standard (schema and specification)**
     - **Test case-specific checks**
   - **Informal criteria**
   - **Expected geometry**
   - **Control parameters**

🔍 See the [Test template](./Test%20template.md) for details.

### Output of the test
Every test has a subfolder named **test-output**. Through a pull request, the party executing the test will upload in such subfolder:
   - n. 1 IFC file, named using this convention: `TestCode`_`SoftwareVendor`.`ifc` (Example: *STN01_AmazingSoft.ifc*)
   - where applicable, any other evidence of fulfillment of the informal validation criteria (e.g., screenshots)

❗ These output will be the base for the validation and verification of the results of the test case.

## List of tests

| Test code                   | Test title                                      | Dependencies |
|-----------------------------|-------------------------------------------------|--------------|
| PJ01                        | Project Setup                                   | none         |
| GL01                        | Global Positioning (map coordinates)            | PJ01         |
| [AL22](./AL22_example-test) | Two railway track alignments without cant       | GL01         |
| AL23                        | Two railway track alignments with cant          | AL22         |
| AL24                        | Stationing for two alignments                   | AL23         |
| SB01                        | Track sub-structure for single track            | AL23         |
| SP01                        | Track super-structure for single track          | AL23         |
| TSTP                        | Track Structures Turnout Panel                  | AL22         |
| GR01                        | Group objects                                   | SB01, SP01   |
| CL01                        | Classify objects                                | SB01, SP01   |
| PP01                        | Add properties                                  | GR01         |
| ALRW1                       | Alignment Railway Curves - Bloss                | none         |
| ALRW2                       | Alignment Railway Curves - Clothoid             | none         |
| ALRW3                       | Alignment Railway Curves - Cosine               | none         |
| ALRW4                       | Alignment Railway Curves - Helmert              | none         |
| ALRW5                       | Alignment Railway Curves - Sine                 | none         |
| ALRW6                       | Alignment Railway Curves - Viennese Bend        | none         |
| [STN01](./STN01)            | Stationing on alignment without broken chainage | GL01         |
| STN02                       | Stationing on alignment with broken chainage    | GL01         |
| [FRSAS01](./FRSAS01)        | FixedReferenceSweptAreaSolid-1                  |              |
| [SSH01](./SSH01)            | SectionedSolidHorizontal-1                      |              |
| [SSH02](./SSH02)            | SectionedSolidHorizontal-2                      |              |
| [SSH03](./SSH03)            | SectionedSolidHorizontal-3                      |              |
| [SSH04](./SSH04)            | SectionedSolidHorizontal-4                      |              |
| [SSH05](./SSH05)            | SectionedSolidHorizontal-5                      |              |
| [SSH06](./SSH06)            | SectionedSolidHorizontal-6                      |              |
| [DDRSAS01](./DDRSAS01)      | DirectrixDerivedReferenceSweptAreaSolid-1       |              |
| [DDRSAS02](./DDRSAS02)      | DirectrixDerivedReferenceSweptAreaSolid-2       |              |
