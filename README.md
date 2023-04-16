# DotRecast
C# Port of Recast & Detour navigation mesh toolset

![DotRecast of a navmesh baked with the sample program](/src/DotRecast.Recast.Demo/screenshot.png?raw=true)

## DotRecast.Recast

Recast is state of the art navigation mesh construction toolset for games.

Recast is...
* 🤖 **Automatic** - throw any level geometry at it and you will get a robust navmesh out
* 🏎️ **Fast** - swift turnaround times for level designers
* 🧘 **Flexible** - easily customize the navmesh generation and runtime navigation systems to suit your specific game's needs.

Recast constructs a navmesh through a multi-step rasterization process:

1. First Recast voxelizes the input triangle mesh by rasterizing the triangles into a multi-layer heightfield.
2. Voxels in areas where the character would not be able to move are removed by applying simple voxel data filters.
3. The walkable areas described by the voxel grid are then divided into sets of 2D polygonal regions.
4. The navigation polygons are generated by triangulating and stiching together the generated 2d plygonal regions.

## DotRecast.Detour

Recast is accompanied by Detour, a path-finding and spatial reasoning toolkit. You can use any navigation mesh with Detour, but of course the data generated with Recast fits perfectly.

Detour offers a simple static navmesh data representation which is suitable for many simple cases.  It also provides a tiled navigation mesh representation, which allows you to stream of navigation data in and out as the player progresses through the world and regenerate sections of the navmesh data as the world changes.

## DotRecast.Recast.Demo

You can find a comprehensive demo project in the `DotRecast.Recast.Demo` folder. It's a kitchen sink demo showcasing all the functionality of the library. If you are new to Recast & Detour, check out [Sample_SoloMesh.cpp](/RecastDemo/Source/Sample_SoloMesh.cpp) to get started with building navmeshes and [NavMeshTesterTool.cpp](/RecastDemo/Source/NavMeshTesterTool.cpp) to see how Detour can be used to find paths.

### Building DotRecast.Recast.Demo

`DotRecast.Recast.Demo` uses [dotnet 7](https://dotnet.microsoft.com/) to build platform specific projects. Download it and make sure it's available on your path, or specify the path to it.

#### Linux & macOS & Windows

- Navigate to the `DotRecast.Recast.Demo` folder and run `dotnet run`

### Running Unit tests

## Integrating with your game or engine

It is recommended to add the source directories `DotRecast.Core`, `DotRecast.Detour.Crowd`, `DotRecast.Detour.Dynamic`, `DotRecast.Detour.TitleCache`, `DotRecast.Detour.Extras` and `DotRecast.Recast` into your own project depending on which parts of the project you need. For example your level building tool could include `DotRecast.Core`, `DotRecast.Recast`, and `DotRecast.Detour`, and your game runtime could just include `DotRecast.Detour`.

## Discuss

- Discuss Recast & Detour: http://groups.google.com/group/recastnavigation
- Development blog: http://digestingduck.blogspot.com/

## License

Recast & Detour is licensed under ZLib license, see `LICENSE.txt` for more information.
