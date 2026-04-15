# Test dataset

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| BU02      | Stefan Jaud     | SBB                 | Export         |


## Model Dataset

This dataset is an example of what a terrain model with the surrounding buildings could look like.

Additionally to the content of [TE01](../../TE01/Dataset/readme.md),
 there are 2 `IfcBuilding`s:
- one is named `'Station'` and is decomposed by 2 `IfcBuildingElementProxy`s and
- the other is named `'Platform'` and is decomposed by 1 `IfcBuildingElementProxy`.

Each `IfcBuildingElementProxy` has a property set named `'SBB-CFF-FFS'` attached with these properties:
1. named `'Status'` with value `'Bestand'`,
1. named `'ObjectTypeName'` with value either `'Gebäude (CD)'` or `'Dach (CD)'` and
1. named `'ObjectTypeID'` with value `'tbd'`.

!["Top view of the station."](./topview.png)

!["Skewed view of the station."](./skewedview.png)
