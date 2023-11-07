## Intent

This folder contains example IFC files, used by the Implementers Forum to deal with the case of railway sleepers linearly placed along a track alignment that includes cant.

**Original input from Acca**: *[...] examples of objects placed with Linear Placement and affected by Cant (e.g. Sleepers). Do they automatically tilt, based on the fact that the linear placement refers the Cant curve (i.e., IfcSegmentedReferenceCurve), or should the rotation be included in the object axis? Wish for the first one but at the moment we had to fallback to the second solution.* - @michelangelo-acca

**Full recording available [here](https://app.box.com/s/7btxwfdnyrqkr2x9jl7cmjt5a8ms2b1w) (from min. 20)**


## Content
It has been agreed to provide 2 types of IFC files, to test how importing applications should behave in the 2 different scenarios.

1. Examples where the tilting value of each sleeper is explicitly stored in the IFC file by the authoring application (using _IfcAxis2PlacementLinear.Axis_ and _IfcAxis2PlacementLinear.RefDirection_) 
2. Examples where no tilting value for sleepers is explicitly stored in the IFC file

**Additional data from exporting applications**

When providing an IFC file, for any of the two scenarios above, the exporting application should also provide the followings - to facilitate the import checking:

- the coordinates (x,y,z) of a particular point of the sleeper (e.g., center of gravity of the bottom surface)
- the value of _IfcLinearPlacement.CartesianPoint_ explicit
- the same example file just with mesh geometry of the sleepers, without any alignment
- if available, dwg file of the sleeper


## Notes

- If not explicitly stated, these files shall be considered as draft, yet to be validated.
- None of the authors, in any way whatsoever, can be responsible for the use of the information contained in these files.


## Naming convention
Start the file name by identifying the vendor authoring it.

> EXAMPLE `Acme_sleepers-linear-placement-cant-explicit.ifc`
