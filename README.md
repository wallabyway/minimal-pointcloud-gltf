## minimal-pointcloud-gltf
a gltf 'profile' for an open format Point-cloud standard, leveraging glTF and 3d-tiles-next.


### Point-Cloud profile

##### Recommended extensions:
- [GLTF_EXT_meshopt_compression](https://gltf-transform.donmccurdy.com/classes/extensions.meshoptcompression.html)
- [3DTILES_content_gltf](https://github.com/CesiumGS/3d-tiles/tree/3d-tiles-next/extensions/3DTILES_content_gltf)
- [3DTILES_implicit_tiling](https://github.com/CesiumGS/3d-tiles/tree/3d-tiles-next/extensions/3DTILES_implicit_tiling)

##### Constraints:
1. glb is point primitives only
2. only one gltf node per tile
3. only one large uint32 buffer (do not break up into 65k buffer chunks)


##### References
- 3DTiles-Next extensions - https://github.com/CesiumGS/3d-tiles/tree/3d-tiles-next/extensions
- meshopt_compression https://gltf-transform.donmccurdy.com/classes/extensions.meshoptcompression.html
- Gltfpack - https://github.com/zeux/meshoptimizer/tree/master/gltf


### Demo
1. take point clouds
2. convert to glb
3. view in mapbox

(watch this space)
