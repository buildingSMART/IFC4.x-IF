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

:round_pushpin: See a [README example for tests](./stationing-on-alignment-broken-chainage/README.md)

### Success Records

Some test folders may contain a `success-records` subfolder. This includes the test records from tools that wishes to share their results at importing the reference IFC file.

**How to add records?**

Submit a pull request to the `success-records` folder that adds one subfolder with the name of your company, containing one markdown file, with the naming convention below, showing how your tool performs against the items in the verification checklist.

Naming convention
`This-is-the-test-title_Company_Tool_ToolVersion.md`

Example
`stationing-on-alignment-broken-chainage_AcmeInc_TNT-BIM_2.18.md`

:round_pushpin: See a [Success Records example](./stationing-on-alignment-broken-chainage/success-records/Acme-Inc/stationing-on-alignment-broken-chainage_AcmeInc_TNT-BIM_2.18.md)

