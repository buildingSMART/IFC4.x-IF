# Spatial Model from OpenRoads Designer

In version 10.10 and up (last year) we implemented a new IFC export that allowed for support of a Spatial Model. It allows for the user to define the classification of the different parts of the Corridor Template inside ORD. This not only maps to classes and predefined types, but it also maps to where in the Spatial Structure the different elements will be added.

The word document [Semantics in ORD](https://github.com/buildingSMART/IFC4.x-IF/blob/main/IFC-files/Bentley/Semantics%20in%20ORD.docx) I tried to describe how this mapping works (in an early version of our application).

The two example files [test1.ifc](https://github.com/buildingSMART/IFC4.x-IF/blob/main/IFC-files/Bentley/test1.ifc) and [test2.ifc](https://github.com/buildingSMART/IFC4.x-IF/blob/main/IFC-files/Bentley/test2.ifc) are example exports showing the result on some simple examples. Note that this is currently in version 4x3_RC4 and are a bit outdated. I hope it still shows the idea how Classification and Spatial Containment can be related.
