# Tests
This folder contains tests to support the implementation of some key IFC 4.3 concepts. Some of these tests may be used by the IFC Global Software Certification (Import).

## Folder structure

Each test has a folder named as the test title, containing:
1. a reference IFC file
2. a README.md listing:
   - Title
   - Description
   - Reference IFC file
   - Main concepts tested
   - Verification checklist
3. a success-records subfolder (optional)

:round_pushpin: See the README template here: **TO BE ADDED**

### Success Records

Some test folders may contain a `success-records` subfolder. This includes one markdown file for each tool that wishes to share their results at importing the Reference IFC file.

**How to add records?**

Submit a pull request to the `success-records` folder including one markdown file, with the naming convention below, showing how your tool performs against the items in the Verification checklist

Naming convention
`This-is-the-test-title_Company_Tool_ToolVersion.md`

Example
`rollercoaster-alignment-with-cant_Acme Inc_TNT BIM_2.18.md`

:round_pushpin: See an example here: **TO BE ADDED**
