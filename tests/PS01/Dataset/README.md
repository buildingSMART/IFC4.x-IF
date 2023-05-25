# Test dataset

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| PS01      | Stefan Jaud     | SBB                 | Export         |

## Content
- [Test dataset](#test-dataset)
  - [Content](#content)
  - [Model Dataset](#model-dataset)
  - [Geographic Coordinate System properties](#geographic-coordinate-system-properties)


## Model Dataset

This dataset is an example of what the project setup model could contain.


### Units

The project defines default units:

- *metre* as `LENGTHUNIT`
- *square metre* as `AREAUNIT`
- *cubic metre* as `VOLUMEUNIT`
- *degree* as `PLANEANGLEUNIT`
- *kilogram* as `MASSUNIT`
- *second* as `TIMEUNIT`
- *CHF* as monetary unit


### Georeferencing

The coordinate reference system is defined as:

- geodetic datum: CH1903+ ([EPSG:4150](https://epsg.io/4150)) 
- projected CRS: LV95 ([EPSG:2056](https://epsg.io/2056)) 
- vertical datum: LN02 ([EPSG:5728](https://epsg.io/5728))

The project's context's point of origin is defined relative to the CRS's point of origin with an offset:

- Easting: 2689000.0
- Northing: 1253000.0
- Elevation: 450.0


### Annotations

There are three `IfcAnnotation`:

1. its id is `'2RhbhoXQ53yAzPOejOTUcp'`
  - its name is *Punkte:Referenzpunkt:11547115*
  - its geometry is a cartesian point with coordinates:
    - Easting: 700.000970772933
    - Northing: 1570.0
    - Elevation: 0.0

2. its id is `'2RhbhoXQ53yBzPOejOTUcp'`
  - its name is *Punkte:Referenzpunkt:11547333*
  - its geometry is a cartesian point with coordinates:
    - Easting: 2005.00097121531
    - Northing: 1765.0
    - Elevation: 0.0

3. its id is `'2RhbhoXQ53yCzPOejOTUcp'`
  - its name is *Punkte:Referenzpunkt:12053356*
  - its geometry is a cartesian point with coordinates:
    - Easting: 195.00097114034
    - Northing: 2100.0
    - Elevation: 0.0


### Proxys

There are three `IfcBuildingElementProxy`:

1. its id is `'3RhbhoXQ53yRzPOejOTUcp'`
  - its name is *Punkte:Referenzpunkt:11547115*
  - its tag is 11547115
  - its geometry is a pyramid turned upside down, with base length 0.5, and height 1.5
  - its position is at (relative to project's origin):
    - Easting: 700.000970772933
    - Northing: 1570.0
    - Elevation: 0.0

![Reference point 11547115 in the context of whole model.](./referencePointFromAfar.png)

![Reference point 11547115 up close with the north direction marked.](./referencePointUpClose.png)

2. its id is `'3RhbhoXQ53yRzPOejOTUgT'`
  - its name is *Punkte:Referenzpunkt:11547333*
  - its tag is 11547333
  - its geometry is a pyramid turned upside down, with base length 0.5, and height 1.5
  - its position is at (relative to project's origin):
    - Easting: 2005.00097121531
    - Northing: 1765.0
    - Elevation: 0.0

3. its id is `'3XMP46M8P65ugGKLEpO4FP'`
  - its name is *Punkte:Referenzpunkt:12053356*
  - its tag is 12053356
  - its geometry is a pyramid turned upside down, with base length 0.5, and height 1.5
  - its position is at (relative to project's origin):
    - Easting: 195.00097114034
    - Northing: 2100.0
    - Elevation: 0.0


## Geographic Coordinate System properties

| Coordinate System |                                       |
|-------------------|---------------------------------------|
| Name              | EPSG:2056,EPSG:5728                   |
| Description       | Swiss  H1903+ / LV95 + LN02 height    |
| EPSG Code         | non existant                          |
| Source            | EPSG                                  |
| Projection        | Hotine Oblique Mercator Azimuth Center |
| Units             | Meter                                 |
| Origin Latitude   | 46.9524055555556°N                    |
| Origin Longitude  |  7.4395833333333°N                    |
| Azimuth           | 90°                                   |
| Rectified grid angle | 90°                                |
| Scale Reduction   | 1.0                                   |
| False Easting     | 2600000.0                             |
| False Northing    | 1200000.0                             |
| Quadrant          | Positive X and Y                      |
| Minimum Longitude |  5.96°E                               |
| Maximum Longitude | 10.49°E                               |
| Minimum Latitude  | 45.82°N                               |
| Maximum Latitude  | 47.81°N                               |

| Geodetic Datum    |                                       |
|-------------------|---------------------------------------|
| Name              | EPSG:4150                             |
| Description       | Swiss CH1903+                         |

| Ellipsoid         |                                       |
|-------------------|---------------------------------------|
| Name              | EPSG:7004                             |
| Description       | Bessel 1841                           |
| Equatorial Radius | 6377397.155                           |
| Inverse flattening| 299.1528128                           |

| Vertical Datum    |                                       |
|-------------------|---------------------------------------|
| Name              | EPSG:5728                             |
| Description       | Landesnivellement 1902                |
