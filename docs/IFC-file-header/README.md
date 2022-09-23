# IFC file header

Each IFC file (.ifc), using the STEP physical file format (as per ISO10303-21), consists of a **header** section and a **data** section

Each header of IFC files should contain, in this order, the following instances:
- FILE_DESCRIPTION
- FILE_NAME
- FILE_SCHEMA

## Header structure
The table below captures the structure of the header.

| **FILE_DESCRIPTION** | **Explanation**                                                  | **Example**                                   |
|----------------------|------------------------------------------------------------------|-----------------------------------------------|
| description          | formal definition of the underlying view definition              | ViewDefinition [Alignment-basedReferenceView] |
| implementation_level | see ISO10303-21, currently always 2;1 for IFC files              | 2;1                                           |
| **FILE_NAME**        |                                                                  |                                               |
| name                 | file name of the IFC export file                                 | Header example.ifc                            |
| time_stamp           | time of creation of the IFC export file                          | 2022-09-16T10:35:07                           |
| author               | user defined field to capture the author/creator of the IFC file | Evandro Alfieri                               |
| organization         | user defined field to capture the organization of the author     | buildingSMART Int.                            |
| preprocessor_version | name of the toolbox used to create the IFC file                  | MyToolboxName Version 1.0                     |
| originating_system   | name of the application (including built number)                 | MyApplicationName Version 22                  |
| authorization        | user defined field to capture the authorizer of the IFC file     | none                                          |
| **FILE_SCHEMA**      |                                                                  |                                               |
| schema_identifiers   | name of the IFC schema                                           | IFC4X3_TC2                                    |

## Header example
The code snippet below is an example of file header, **extracted from the file [Header example.ifc](./Header%20example.ifc)**

```
HEADER;
FILE_DESCRIPTION(('ViewDefinition [Alignment-basedReferenceView]'),'2;1');
FILE_NAME('Header example.ifc', '2022-09-16T10:35:07', ('Evandro Alfieri'), ('buildingSMART Int.'), 'MyToolboxName Version 1.0', 'MyApplicationName Version 22', 'none');
FILE_SCHEMA(('IFC4X3_TC2'));
ENDSEC;`
```


*For further information, see the complete [IFC header policy](https://standards.buildingsmart.org/documents/Implementation/ImplementationGuide_IFCHeaderData_Version_1.0.2.pdf)*