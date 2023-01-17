## Example files for IFC georeferencing
This folder contains IFC example files, **using the latest IFC4.3 version**, and containing georeferencing data - with different combinations of:

- Coordinate Reference Systems (Projected+Vertical, Compound, Geographic)
- Encoding for such coordinate systems (OGC WKT, EPSG)
- Coordinate operations available in IFC (MapConversion, RigidOperation, MapConversionScaled)

| Filename                                  | Type of CS                      | CS encoded using | Coordinate operation   | Notes                                                          |
|-------------------------------------------|---------------------------------|------------------|------------------------|----------------------------------------------------------------|
| Georeferencing_COMPDCS(WKT)-RO.ifc        | Compound*                       | OGC WKT          | IfcMapConversion       | RigidOperation is all set to 0. The WKT literal contains epoch |
| Georeferencing_COMPDCS(EPSG)-MC.ifc       | Compound*                       | EPSG             | IfcMapConversion       | This is in Norway                                              |
| :construction:                            | Compound*                       | tbc              | IfcMapConversionScaled | to be created                                                  |
| :construction:                            | Compound*                       | tbc              | IfcRigidOperation      | to be created                                                  |
| Georeferencing_PROJCS,VERTCS(EPSG)-MC.ifc | Projected (with vertical datum) | EPSG             | IfcMapConversion       | EPSG code is deprecated. Contains 2 shapes for visualisation   |
| Georeferencing_PROJCS,VERTCS(WKT)-RO.ifc  | Projected (with vertical datum) | WKT              | IfcRigidOperation      | WKT to be completed. Contains 2 shapes for visualisation       |
| Georeferencing_GEOGCS(EPSG)-RO.ifc        | Geographic                      | EPSG             | IfcRigidOperation      | Contains 2 shapes for visualisation                            |

*In IFC, a Compound CS (e.g., Projected CS + Vertical CS) is described using the IfcProjectedCRS entity. Apologies for the misleading name in IFC
