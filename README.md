## minimal-pointcloud-gltf
a gltf 'profile' for an open format Point-cloud standard, leveraging glTF and 3d-tiles-next.


### Point-Cloud profile

##### Recommended extensions:
- [GLTF: EXT_meshopt_compression](https://gltf-transform.donmccurdy.com/classes/extensions.meshoptcompression.html)
- [GLTF: KHR_mesh_quantization](https://github.com/CesiumGS/glTF/tree/main/extensions/2.0/Khronos/KHR_mesh_quantization)
- [GLTF: KHR_materials_unlit](https://github.com/KhronosGroup/glTF/blob/main/extensions/2.0/Khronos/KHR_materials_unlit/README.md)
- [3DTILES: EXT_mesh_features](https://github.com/CesiumGS/glTF/tree/3d-tiles-next/extensions/2.0/Vendor/EXT_mesh_features)
- [3DTILES: implicit_tiling](https://github.com/CesiumGS/3d-tiles/tree/main/extensions/3DTILES_implicit_tiling)

##### Creating a glb Tile:
1. point primitives only
2. only one node
3. single buffer
4. required buffer view for VEC3 positions (max size uint32) (do not break up into 65k buffer chunks)
5. optional buffer view for VEC4 RGB colors (max size uint32) (do not break up into 65k buffer chunks)
5. optional buffer view for VEC3 normals (max size uint32) (do not break up into 65k buffer chunks)
7. single material using extension 'KHR_materials_unlit' 
8. finally, compress glb with [GLTF_EXT_meshopt_compression](https://gltf-transform.donmccurdy.com/classes/extensions.meshoptcompression.html) (ie. try [glTFpack](https://github.com/zeux/meshoptimizer/tree/master/gltf) )


##### Unlit Material example:
```json
"materials": [
    {
      "name": "unlit",
      "extensions": {
        "KHR_materials_unlit": {}
      },
    }
  ],
```

##### single position & color buffer example:

```json
"bufferViews": [
    {
      "buffer": 0,
      "byteLength": 200789448,
      "byteOffset": 0,
      "byteStride": 12,
      "name": "floatBufferViews",
      "target": 34962
    },
    {
      "buffer": 0,
      "byteLength": 267719264,
      "byteOffset": 200789448,
      "byteStride": 16,
      "name": "floatBufferViews",
      "target": 34962
    }
  ],
```

##### References
- all 3DTiles-Next extensions - https://github.com/CesiumGS/3d-tiles/tree/main/extensions


### Demo

Add point-cloud to mapbox, via 3d-Tiles/glTF pointcloud file set

(watch this space)

| three.js (ebeaufay)  | Cesium (experimental) |
| ------------- | ------------- |
| ![3d-tiles-next](https://user-images.githubusercontent.com/440241/148264966-f62d1e44-7e4e-4571-ba5d-e5da89f31823.gif)  | ![cesium-gltf-zeux-3d-tiles-next](https://user-images.githubusercontent.com/440241/148264951-283656e7-5e57-4528-967e-c2bb0f4eeb7d.JPG)  |





