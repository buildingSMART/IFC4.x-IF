# Stationing on alignment broken chainage

## Description

This test represent a single railway alignment (horizontal, vertical and cant layouts included) with chainage break and four signals linearly placed along it.

## Reference IFC file

:file_folder: [stationing-on-alignment-broken-chainage.ifc](./stationing-on-alignment-broken-chainage.ifc)

IFC Validation Service results:

- [x] Syntax
- [x] Schema
- [x] Normative IFC rules

checked with version:
`validate 1.0.0 - #18e8e38` on April 15, 2025

## Main concepts tested

Alignment business logic, alignment representation, referents, linear placement, georeferencing.

## Verification checklist

**Alignment business logic**

1. all three layouts (horizontal, vertical, cant) of alignment are present
1. all horizontal segments are present (14)
1. all vertical segments are present (10)
1. all cant segments are present (14)

**Alignment representation**

1. all three layouts (horizontal, vertical, cant) of alignment are present
1. all horizontal segments are present (14, 4 straight lines and 3 circular arcs, each one with 2 transitions)
1. all vertical segments are present (9)
1. all cant segments are present (13)

**Referents**
1. 36 referents are present (34 REFERENCEMARKER and 2 STATION)
1. stationing pace is 50 m
1. starting station is -153.100 m 
1. after the 21st marker (Name: Referent_Mileage_21) there is a stationing jump (broken chainage). IncomingStation is 876.2721 m, Station is 5,350.0000 (or 5+350.0000), DistanceAlong is 1,029.3721, (**X**: 453,202.5241; **Y**: 4,539,831.9287; **Z**: 2.0)
1. ending station is 5,779.2225 m

**Linear placement**

1. four signals are placed along the alignment. They are all IfcSignal of type VISUAL, and have the same shape.
1. two signals are placed on the left and two on the right side of the alignment.
1. two signals (1st, 3rd) face the start of the alignment, two (2nd and 4th) face the end of the alignment.
1. stationing values of the signals are, respectively: 200; 700; 5+430.0; and 5+740.0

| # | Name               | Distance Along | Offset Horizontal | Offset Vertical | Rotation         |
|---|--------------------|----------------|-------------------|-----------------|------------------|
| 1 | Route Indicator_01 | 353.1000       | 3.0000            | 2.5000          | 0                |
| 2 | Route Indicator_02 | 853.1000       | -3.0000           | 2.5000          | 3.14159265358979 |
| 3 | Route Indicator_03 | 1109.3721      | 3.0000            | 2.5000          | 0                |
| 4 | Route Indicator_04 | 1419.3721      | -3.0000           | 2.5000          | 3.14159265358979 |

> NOTE:
> - All distances are in meters, all angles are in radian.
> - The horizontal offset is positive when an element is placed at the left of the alignment, negative > when is placed at the right.
> - The vertical offset represents the distance between the signal origin and its vertical projection on the rail level (without cant). 
> - The rotation is based on the line perpendicular to the alignment, is always positive and follows a CCW direction.

**Georeferencing**

1. CRS is EPSG:3065
1. vertical datum is EPSG:5214  

