# IFC Implementers Forum

The **IFC Implementers Forum** (abbreviated, IF) is a joint testing, implementation and collaboration effort between IFC software developers. Its objective is to accelerate and support the implementation of the IFC standard, and inform the community about its overall implementation progress and results.

It is hosted and coordinated by **buildingSMART International**, and it is part of the larger [buildingSMART Implementers Assembly](https://www.buildingsmart.org/implementers-assembly/) (formerly ISG), which oversees and support implementation activities for all buildingSMART solutions & standards (e.g., IFC, BCF, IDS, bSDD, Validation & Software Certification services, etc.). The forum allows software developers to meet, discuss, test and progress IFC implementation for their products.

Please read the [Safe Harbour Notice](#safe-harbour-notice) at the end of this page.

**To join** the IFC Implementers Forum, send an email to evandro.alfieri@buildingsmart.org



## Approach

The forum operates through the following pipeline:

* **Software implementers join the forum**, identify challenges, propose solutions and reach agreements on implementations.
  * Depending on the nature of the issue, solutions may be in the form of improved documentation, formal rules for the [IFC Validation Service](https://validate.buildingsmart.org/), suggested improvements for future versions of IFC, or a combination of the above.
* **Test cases and example IFC files** can be created and used by the forum, and are published in this repository
  * Some of these files may be also used for Import verification by the [IFC Software Certification Program](https://www.buildingsmart.org/compliance/software-certification/)

### Test creation

Test cases may be created following a provided template, which includes: test instructions, test dataset, validation criteria, and optionally a reference IFC file.

➡ [See available tests](./tests/)

### IFC file validation

Validation depends on the type of test, and can be more or less automated. When done against an IFC file, the validation shall first ensure that the IFC file complies to the IFC standard - and this is done using the buildingSMART [Validation Service](https://validate.buildingsmart.org/). After that, the validation can proceed using test-specific requirements captured in [IDS](https://www.buildingsmart.org/standards/bsi-standards/information-delivery-specification-ids/) files, and/or be done against other test evidence produced to demonstrate the fulfillment of validation criteria.

➡ [See Validation Service rules](https://buildingsmart.github.io/ifc-gherkin-rules/branches/main/features/index.html#)


## Repository Structure

- [tests/](./tests/) — Test cases created by bSI Projects, each including instructions, datasets, validation criteria, and optionally a reference IFC file.
- [IFC-files/](./IFC-files/) — IFC sample files used as reference datasets.
- [docs/](./docs/) — Supporting documentation and diagrams.


## Getting Started

Whether you are a software vendor, a bSI project contributor, or a tool developer, here is how to get involved:

- **Create a test:** Follow the template in [tests/](./tests/) to add a new test case.
- **Add or update an SDK entry:** Edit [docs/sdk-support.md](./docs/sdk-support.md) or [open an issue](../../issues/new) if your tool is missing or outdated.
- **Review existing rules:** Browse the [ifc-gherkin-rules repository](https://github.com/buildingSMART/ifc-gherkin-rules/tree/main/features).

See [CONTRIBUTING.md](./.github/CONTRIBUTING.md) for detailed guidelines.


## Resources

[Official website](https://www.buildingsmart.org/resources/ifc-if/)

[Public box folder](https://app.box.com/s/vfwibc0w9cby4skdry6t1vsh8yprktp0)

[Slack channel](https://bsi-technicalservices.slack.com/archives/C042ZUVGBTP)

[SDKs supporting IFC 4.3 ADD2](./docs/sdk-support.md)


## Safe Harbour Notice

Certain statements made in the context of Implementers Forum meeting, its presentations and subsequent follow-up information, including Q&A materials, are forward-looking statements which may include roadmaps, project plans, release plans and development timescales that are estimates and projections.

No assurance is given nor implied that bSI and/or any third-parties involved in the work will be able to meet such estimates or projections by the dates specified, or at all.

They are not a commitment to deliver any update, milestone, development or functionality and should not be relied upon when making investment or purchasing decisions. buildingSMART International reserves the right to make changes to all such information at its sole discretion or subject to the agreement of third-parties where required.
