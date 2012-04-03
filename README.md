TiledSharp
==========
A .NET C# library for importing Tiled TMX tile maps

About TiledSharp
----------------
TiledSharp is a .NET C# library for importing TMX tilemaps and TSX tilesets
generated by Tiled, a tile map generation tool. The data is saved as a Map
object whose structure is to the TMX file, and is constructed from standard
.NET C#4 structures and objects.

As a generic TMX and TSX parser, TiledSharp does not use any XNA Game Studio
libraries. However, it can be used as a starting point for XNA game and library
development.

This project is currently under development.

Usage
-----
To import a TMX file into your C# application:

- Include TiledSharp into your project, either as source or a DLL
- Include the TiledSharp namespace:

  `using TiledSharp;`

- Create a Map object:

  `Map map = new Map("yourFile.tmx");`

TiledSharp supports both resource names and explicit paths, and should work as
expected in most situations. A detailed description will be placed in the wiki.

Map fields generally correspond with the XML structure. For example:

    Map map = new Map("yourFile.tmx");
    string version = map.version;
    List<Layer> layers = map.layer;
    int width = map.layer[0].width;
    MapObject town = map.objectgroup[0].object[0];

Details will be placed in the wiki.

Tilesets, layers, objects, and other lists are currently accessed as arrays.
In the future, they will hopefully be accessible by name.

Licensing
---------
I have not yet chosen a license, although I soon plan to release it under
one permitting public use and modification. Please feel free to use or modify
the code as necessary.

Unimplemeneted Features
-----------------------
- Recast tile gid array as List, with bit-flipped elements
- Replace `List<e>` with `Dictionary<"name", e>`?
- Testing suite should have a separate project

Contact
-------
Marshall Ward (<marshall.ward@gmail.com>)

Notes
-----
Tiled (<http://mapeditor.org>) is an open-source (GPL) tile map editor
developed and maintained by Thorbjørn Lindeijer.

Zlib decompression uses the Zlib implementation of DotNetZip v1.9.1.8
(<http://dotnetzip.codeplex.com>).
