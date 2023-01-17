# IFC4.x-IF
*IFC4.x Implementers Forum*

<div align="center">
<img src="./docs/IFC4.x-IF_approach.png" width="500"/>
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

➡ [Go to the list of rules](https://github.com/buildingSMART/ValidationService) :construction:

**Validation**

Validation depends on the type of test, and can be more or less automated. When done against an IFC file, the validation shall ensure that the file is syntactically, structurally, and semantically, correct. It can be done also against other test evidence - produced to demonstrate the fulfillment of validation criteria.


## Safe Harbour Notice

Certain statements made in the context of Implementers Forum meeting, its presentations and subsequent follow-up information, including Q&A materials, are forward-looking statements which may include roadmaps, project plans, release plans and development timescales that are estimates and projections.

No assurance is given nor implied that bSI and/or any third-parties involved in the work will be able to meet such estimates or projections by the dates specified, or at all. 

They are not a commitment to deliver any update, milestone, development or functionality and should not be relied upon when making investment or purchasing decisions. buildingSMART International reserves the right to make changes to all such information at its sole discretion or subject to the agreement of third-parties where required.


## Resources

🌐 [Official website](https://www.buildingsmart.org/resources/ifc-4x-if/) 

📂 [Public box folder](https://app.box.com/s/vfwibc0w9cby4skdry6t1vsh8yprktp0)

💬 [Slack channel](https://bsi-technicalservices.slack.com/archives/C042ZUVGBTP)


## List of SDK supporting IFC4.3 (ADD1)
Below is a list of SDK solutions supporting IFC 4.3 ADD1.
> If you see a missing product, or information that needs updating, simply edit this file or open an issue in this repository.

| Toolbox                 | Developer                 | Can parse IFC4.3 ADD1 | Can visualise IFC4.3 ADD1 geometry | License                       | Source code access                            | Language                                 | Contact             |
|-------------------------|---------------------------|:---------------------:|:----------------------------------:|:-----------------------------:|:---------------------------------------------:|:----------------------------------------:|---------------------|
| GeometryGym Toolbox     | GeometryGym               | :heavy_check_mark:    | :x:                                | MIT                           | https://github.com/GeometryGym/GeometryGymIFC | C#                                       |                     |
| CSTB STEP Toolbox       | CSTB (eveBIM)             | :heavy_check_mark:    | :x:                                |                               |                                               |                                          |                     |
| IFC Engine              | RDF                       | :heavy_check_mark:    | :heavy_check_mark:                 | commercial                    | :heavy_check_mark:                            | C++11                                    | peter.bonsma@rdf.bg |
| THC.IFC.Reactor         | The Hard Code GmbH        | :heavy_check_mark:    | :x:                                | commercial                    |                                               | C#                                       | info@the-hard-code.com |
| IfcOpenShell            | IfcOpenShell              | :heavy_check_mark:    | :x:                                | LGPL                          | https://github.com/IfcOpenShell/IfcOpenShell  | C++ (compile-time) and Python (run-time) |                     |
| IFC-SDK                 | ODA                       | :grey_question:       | :grey_question:                    | commercial                    |                                               |                                          |                     |
| TUM Open Infra Platform | TUM                       | :heavy_check_mark:    | some :construction:                | GPL v3                        | https://github.com/tumcms/Open-Infra-Platform | C++20                                    |                     |
| web-IFC                 | IFC.js                    | :x:                   | :x:                                | Mozilla Public License V. 2.0 |                                               |                                          |                     |
| XBIM Toolkit            | XBIM                      | :heavy_check_mark:    | :grey_question:                    |              CDDL             |         https://github.com/XbimTeam                   | .NET, C#                                 | info@xbim.net           |
