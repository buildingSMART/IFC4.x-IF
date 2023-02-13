# BC01 - Model Federation

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| MF01      | WG4             | SBB                 | Export         |



## Intent

The intention of this Business Case is to test how model federation works in the context of IFC4.3. 
In particular we want to test the behaviour of objects that are located in relation to an alignemnt (for example a turnout within an alignment) and in relation to fixed coordinates (for example existing buildings)

<details><summary>Main IFC concept involved in this test</summary> 

- Project Global Positioning - Georeferencing
- Model referencing
- Alignment Layout
- Spatial Decomposition - IfcFacilityPart implementation
- Model integration and display
</details>


## Test dataset (input)

The dataset is made up of different specialist models of an existing section of a railaway line. The geographic coordinate system is LV95. More infor about this system can be found in https://www.swisstopo.admin.ch/en/home/meta/supply-structure/standard-range.html. Some of the details might have changed but they represent as much as possible an existing rail condition. 
All the required files are collected in the Dataset folder and summarised in the table below.

| Filename (format)         | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| MF01_Alignment.landxml    | Middle axis of the alignemnt                                       |
| MF01_Alignment.xtr        | Alignment's information in Toporail format (SBB's propietary)      |
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
