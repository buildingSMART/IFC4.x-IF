# BC01 - Model Federation

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| MF01      | Mercedes Santos, Chi Zhang             | SBB                 | Export, Import         |



## Intent

The intention of this Business Case is to test how model federation works in the context of IFC4.3. 
In particular we want to test the behaviour of objects that are located in relation to an alignemnt (for example a turnout within an alignment) and in relation to fixed coordinates (for example existing buildings) with georeferencing information set as the global context.

<details><summary>Main IFC concept involved in this test</summary> 

- [Project Global Positioning](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Project_Context/Project_Global_Positioning/content.html)
- [Alignment Layout](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Composition/Nesting/Alignment_Layout/content.html)
- [Spatial Structure](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Connectivity/Spatial_Structure/content.html)
- [Spatial Decomposition](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Composition/Aggregation/Spatial_Decomposition/content.html)
- [Alignment Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Alignment_Geometry/content.html)
- [Product Linear Placement](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Placement/Product_Linear_Placement/content.html)
- [Product Local Placement](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Placement/Product_Local_Placement/content.html)
- [Revision Control](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Attributes/Revision_Control/content.html)
- [Software Identity](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Attributes/Software_Identity/content.html)
- [Element Decomposition](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Composition/Aggregation/Element_Decomposition/content.html)
- [Body Tessellation Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Body_Geometry/Body_Tessellation_Geometry/content.html)
- [Body Advanced Swept Solid Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Body_Geometry/Body_AdvancedSweptSolid_Geometry/content.html)
- [Clearance Geometry](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Product_Shape/Product_Geometric_Representation/Clearance_Geometry/content.html)
- [Object Nesting](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Composition/Nesting/Object_Nesting/content.html)
- [Product Relative Positioning](https://ifc43-docs.standards.buildingsmart.org/IFC/RELEASE/IFC4x3/HTML/concepts/Object_Connectivity/Product_Relative_Positioning/content.html)

</details>

<details><summary>Main software features involved in this test</summary> 

- Map coordinate system
- Ownership and revision control
- Model referencing
- Element merging and update
- Model integration and display
- Model filter and hide
</details>


## Test dataset (input)

The dataset is made up of different specialist models of an existing section of a railaway line. The geographic coordinate system is LV95. More infor about this system can be found in https://www.swisstopo.admin.ch/en/home/meta/supply-structure/standard-range.html. Some of the details might have changed but they represent as much as possible an existing rail condition. 
All the required files are collected in the Dataset folder and summarised in the table below.

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| MF01_Alignment.landxml    | Middle axis of the alignemnt                                       |
| MF01_buildings.ifc        | Data containing existing Building in ifc 4.0                       |
| MF01_Fahrbahn.ifc         | Data containing existing rails, sleepers and turnouts in ifc 4.0   |
| MF01_LRP.ifc              | Data containing existing clearance gauge information in ifc 4.0    |
| MF01_Entwasserung.ifc     | Data containing existing drainage information in ifc 4.0           |


## Validation criteria
⚡ For this test case to be considered passed, all criteria listed in this section, and the ones of prerequisites tests shall be verified. ⚡

### Formal rules
Formal Rules are those contained in the Gerkin documentation provided within the bSI validation system. In particular, the following list of rules will apply

|Rule Number                | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| RI-###                    | Rule to check..                                                    |
| RI-###                    | Rule to check..                                                    | 
| RI-###                    | Rule to check..                                                    |


### Informal criteria
The following steps should be performed in order to corroborate that the software is working as expected:

- Each file mades up a specialist model. Each model is to be loaded within one IfCFacilityPart.
- All of the models should be first converted into ifc4.3.
- When loaded together, all the models shold be able to be federated into one. An export of the federated model is not required.
- The existing building model should be independent of the other models and the location of its objects based only on its geocoordinates.
- The alignment model should be independent of the other models and the location of its objects based only on its geocoordinates.
- The alignment model should guide the location of both the railway and a gauge model. It should also guide some, but not all, the objects of the drainage model. Geolocation of the "guided" objects should be obtained by transformation within the software but it should not be fixed to any coordinated system.
- The drainage model will contain both fixed and "guided" objects in terms of its location. Georefencing will be both fixed and guided, depending on the type of element.
- The test will consist a correction of the alignment model and the consecuent correction of the guided models.
- We expect an export in ifc4.3 of all models before ans after the correction.


### Expected geometry
The following figure displays the federetad model before the correction



### Link to requirements
>:information_source: *list requirements covered by this test, or refer to external documentation*

...
