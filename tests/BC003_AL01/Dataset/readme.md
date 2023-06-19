# Test dataset

| Test code | Test author     | Test dataset source | Test direction |
|-----------|-----------------|---------------------|----------------|
| AL01      | Joao Correa     | MINnD               | Import/Export  |

## Content
- [Test dataset](#test-dataset)
  - [Content](#content)
  - [Model Dataset](#model-dataset)
  - [Test Data (Input)](#test-data-input)


## Model Dataset

This dataset is an example of what the Railway Alignment model could contain. This test will test the creation of alignment geometry and its visualization. The alignments created in this Test will be used as the linear positioning based for subsequent Tests. As the shared data required by all the subsequent tests.

### Main IFC concepts involved in this test

The concept templates that are focused by this series of tests are listed as follows. Specific concept templates that are focused by this test are in bold.
- Project Global Positioning
- Alignment Layout
- Alignment Geometry
- Product Local Placement
- Revision Control
- Software Identity
- Object Nesting

### Main software features involved in this series of tests
	
- Alignment visualization

## Test dataset (input)

The dataset is made of a LandXML file that has multiple alignments for a section of a tramway line. The coordinates system is based on RGF93 Lambert Zone 3 ([EPSG:3944](https://epsg.io/3944)) and vertical datum based on the NGF IGN69 ([EPSG:5720](https://epsg.io/5720)).
 It has in total 4 alignments and the railway section is about 1.7 kilometers long. An IFC 4.3 reference file is also provided.

| Filename (format) | Description  |
|-----------------------------|-----------------------------------------------------------------------------------------|
|  BC003_AL01_alignments.xml  |  Data containing track alignments in LandXML format  |
|  BC003_AL01_alignments.dwg  |  Data containing track alignments in DWG format  |
|  BC003_AL01_reference.ifc  | Data containing track alignments in IFC 4.3. Please, note that this IFC file was created using the existing capabilities of Civil 3D, which means that the file is not 100% compliant with the test requirements.  |


### Alignment
The **Alignment** is described through its **horizontal** and **vertical** layouts. They are all described in the LandXML file. In LandXML, each alignment is made as an instance of "Alignment". For example:



### Units

The project defines default units:

- *metre* as `LENGTHUNIT`
- *square metre* as `AREAUNIT`
- *cubic metre* as `VOLUMEUNIT`
- *radian* as `PLANEANGLEUNIT`


### Georeferencing

The coordinate reference system is defined as:

- geodetic datum: EPSG:4171 ([EPSG:4171](https://epsg.io/4171)) 
- projected CRS: EPSG:3944 ([EPSG:3944](https://epsg.io/3944)) 
- vertical datum: EPSG:5720 ([EPSG:5720](https://epsg.io/5720))

The project's context's point of origin is defined relative to the CRS's point of origin with an offset:

- Easting: 1892000.000
- Northing: 3126700.000
- Elevation: 0.000


### Proxys

There are three `IfcBuildingElementProxy`:

1. its id is `'0SGxbfZ753H9JxUygRKEif'`
  - its name is *Reference Point*
  - its tag is 714D
  - its geometry is a pyramid turned upside down, with base length 0.5, and height 1.5
  - the global position of its apex is:
    - Easting: 1892028.44995586
    - Northing: 3126717.20273397
    - Elevation: 3.95935497

2. its id is `'1QGIfOv2vCmP6wCdfw661z'`
  - its name is *Reference Point*
  - its tag is 7184
  - its geometry is a pyramid turned upside down, with base length 0.5, and height 1.5
  - its position is at (relative to project's origin):
    - Easting: 1891963.00866927
    - Northing: 3126717.20273397
    - Elevation: 3.95935497

3. its id is `'0gElLyvUP7pu3MBs30OjlL'`
  - its name is *Reference Point*
  - its tag is 7151
  - its geometry is a pyramid turned upside down, with base length 0.5, and height 1.5
  - its position is at (relative to project's origin):
    - Easting: 1892026.93786196
    - Northing: 3126788.73823184
    - Elevation: 3.64980163


## Geographic Coordinate System properties

| Coordinate System |                                       |
|-------------------|---------------------------------------|
| Name              | EPSG:3944                             |
| Description       | RGF 1993 CC44 - France – mainland onshore between 43ºN and 45ºN    |
| EPSG Code         | EPSG:3944                             |
| Source            | EPSG                                  |
| Projection        | Lambert Conformal Conic               |
| Units             | Meter                                 |
| Origin Latitude   | 44.0°                                 |
| Origin Longitude  | 43.25°                                |
| False Easting     | 1700000.0                             |
| False Northing    | 3200000.0                             |
| Quadrant          | Positive X and Y                      |
| Minimum Longitude | 2883307.63                            |
| Maximum Longitude | 4113035.68                            |
| Minimum Latitude  | 623631.35                             |
| Maximum Latitude  | 2319381.0                             |

| Geodetic Datum    |                                       |
|-------------------|---------------------------------------|
| Name              | EPSG:4171                             |
| Description       | D RGF 1993                            |

| Ellipsoid         |                                       |
|-------------------|---------------------------------------|
| Name              | GRS 1980                              |
| Description       |                                       |
| Equatorial Radius | 6378137.0                             |
| Inverse flattening| 298.257222101                         |

| Vertical Datum    |                                       |
|-------------------|---------------------------------------|
| Name              | EPSG :5720                            |
| Description       |                                       |

