## Note
This folder contains example IFC files, used by the Implementers Forum to deal with the topic of Digital Terrain Modelling (DTM).
> NOTE  If not explicitly stated, these files shall be considered as draft, yet to be validated.
> None of the authors, in any way whatsoever, can be responsible for the use of the information contained in these files.

## Naming convention
Start the file name by identifying the vendor authoring it.

> EXAMPLE `Contoso_terrain-model.ifc`, `Acme_terrain-breps.ifc`

## Files


### [ACCA_terrain-model.ifc](./ACCA/ACCA_terrain-model.ifc.zip)

#### Validation Data

| Validation data | Ref.      | Terrain surface (m2) | Total n. of triangles | (x,y,z) min         | (x,y,z) max |
|-----------------|-----------|----------------------|-----------------------|---------------------|-------------|
| Exporting tool  | [01](#01) | tbd                  | 927848                | 112.75, 2018.25, -2.18 | 992.25, 1738.75, 7.63      |
| 3DS             | [02](#02) |                      |                       |                     |             |
| Esri            | [03](#03) |                      |                       |                     |             |
| Sogelink        | [04](#04) | tbd                  | 927848                | 279.5, 879.5, 9.8   | update      |
| Trimble         | [05](#05) |                      |                       |                     |             |
| Bentley         | [06](#06) |                      |                       |                     |             |
| Infotech        | [07](#07) |                      |                       |                     |             |
| Adtollo         | [08](#08) | 249250               | 927848                | 279.5, 879.5, 9.81  | update      |

#### Screenshots

##### 01
[Link to model](https://service.usbim.com/link/651eae349242a358bea4321b)

##### 02
...

##### 03
<div>
<img src="./Esri/prototype-ACCA-geographic-elem-TIN.png" width="500"/>
</div>

##### 04
<div>
<img src="./Sogelink/Sogelink_Import_ACCA.png" width="500"/>
</div>

##### 05
...

##### 06
...

##### 07
...

##### 08
<div>
<img src="https://github.com/Samanii2/IFC4.x-IF/blob/patch-2/IFC-files/Terrain-models/Adtollo/ACCA_Terrain_model_Import_Adtollo.jpg" width="500"/>
</div>


### [Trimble_terrain-model.ifc](./TrimbleQuadri/Trimble_terrain-model.ifc)

#### Validation Data

| Validation data | Ref.      | Terrain surface (m2) | Total n. of triangles | (x,y,z) min          | (x,y,z) max |
|-----------------|-----------|----------------------|-----------------------|----------------------|-------------|
| Exporting tool  | [09](#09) | 1578901              | 196614                | tbd                  | tbd         |
| 3DS             | [10](#10) |                      |                       |                      |             |
| Esri            | [11](#11) |                      |                       |                      |             |
| Sogelink        | [12](#12) | 1578901.8            | 196614                | 1388.5, 1123.1, 51   | tbd         |
| Acca            | [13](#13) | tbd                  | 196614                | 98279.2, 1.21331e+06, 21 | 99667.7, 1.21218e+06, 72         |
| Bentley         | [14](#14) |                      |                       |                      |             |
| Infotech        | [15](#15) |                      |                       |                      |             |
| Adtollo         | [16](#16) | 1578901.9            | 196614                | 1388.55, 1123.15, 51 | tbd         |

#### Screenshots

##### 09
<div>
<img src="https://github.com/JanErikHoel/IFC4.x-IF/assets/48426749/5105e02d-864f-454f-b6d4-0f9580689314" width="500"/>
</div>

##### 10
...

##### 11
<div>
<img src="./Esri/prototype-Trimble-geotech-tri-face-set.png" width="500"/>
</div>

##### 12
<div>
<img src="./Sogelink/Sogelink_Import_Trimble.png" width="500"/>
</div>

##### 13
[Link to model](https://service.usbim.com/link/651eb1cb9242a35443a43288)

##### 14
...

##### 15
...

##### 16
<div>
<img src="./Adtollo/Adtollo_Trimble_Terrain_model_Import.jpg" width="500"/>
</div>

### [Sogelink](./Sogelink)

#### Validation Data

| Validation data | Ref.      | Terrain surface (m2) | Total n. of triangles | (x,y,z) min         | (x,y,z) max          |
|-----------------|-----------|----------------------|-----------------------|---------------------|----------------------|
| Exporting tool  | [17](#17) | 107916.8             | 2112                  | 745.4, 4757.1, 72.7 | 1269.8, 5039.3, 93.4 |
| 3DS             | [18](#18) | 107918.044           | 2132                  | tbd                 | tbd                  |
| Esri            | [19](#19) |                      |                       |                     |                      |
| ACCA            | [20](#20) |                      | 2132                  | 745.453, 5039.32, 72.73 | 1269.88, 4757.13, 93.39 |
| Trimble         | [21](#21) |                      |                       |                     |                      |
| Bentley         | [22](#22) |                      |                       |                     |                      |
| Infotech        | [23](#23) |                      |                       |                     |                      |
| Adtollo         | [24](#24) |                      |                       |                     |                      |

#### Screenshots

##### 17
<div>
<img src="./Sogelink/Sogelink_Terrain.png" width="500"/>
</div>

##### 18
<div>
<img src="./3DS/3DS_Import_Sogelink_TerrainModel.PNG" width="500"/>
</div>

##### 19
<div>
<img src="./Esri/prototype-Sogelink-geographic-elem-TIN.png" width="500"/>
</div>

##### 20
[Link to model](https://service.usbim.com/link/653bb4ff8e575401308ac958)

##### 21
...

##### 22
...

##### 23
...

##### 24
...


### [3DS](./3DS/3DS_Terrain-model.ifc)

#### Validation Data

| Validation data  | Ref.      | Terrain surface (m2) | Total n. of triangles |       (x,y,z)<sub>min</sub>      |       (x,y,z)<sub>max</sub>      |
|------------------|-----------|----------------------|-----------------------|----------------------------------|----------------------------------|
| Exporting tool   | [26](#26) | 434446.451           | 72640                 | (-427.131,-276.020,181.051)      | (427.163,276.018,282.245)        |
| ACCA             | [27](#27) |                      | 71702                 | -427.131, 276.018, 181.051       | 427.163, 276.02, 282.245         |
| Esri             | [28](#28) |                      |                       |                                  |                                  |
| Importing tool 3 | ...       |                      |                       |                                  |                                  |

#### Screenshots

##### 26
<div>
<img src="./3DS/3DS_terrain-model.PNG" width="500"/>
</div>

##### 27
[Link to model](https://service.usbim.com/link/653bb58c8e575406628ac960)

##### 28
<div>
<img src="./Esri/prototype-3DS-geographic-tri-face-set.png" width="500"/>
</div>


### [Bentley](./Bentley/Bentley_Terrain.ifc)

#### Validation Data

| Validation data  | Ref.      | Terrain surface (m2) | Total n. of triangles | (x,y,z)<sub>min</sub>     | (x,y,z)<sub>max</sub>   |
|------------------|-----------|----------------------|-----------------------|---------------------------|-------------------------|
| Exporting tool   | [40](#40) | tbd                  | tbd                   | tbd                       | tbd                     |
| ACCA             | [41](#41) |                      | 12761                 | 492971, 149436, 366.799   | 493395, 148872, 384.064 |
| 3DS              | [42](#42) | 144305.6             | 12761                 | (493000,148900,366.799)   | (493400,149400,384.064) |
| Importing tool 3 | ...       |                      |                       |                           |                         |

#### Screenshots

##### 40
<div>
<img src="./Bentley/Bentley_Terrain.png" width="500"/>
</div>

##### 41
[Link to model](https://service.usbim.com/link/653bb5ce8e575402688ac963)
##### 42
<div>
<img src="./3DS/3DS_Import_Bentley_TerrainModel.PNG" width="500"/>
</div>
