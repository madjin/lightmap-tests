# lightmap-tests
testing glTF lightmaps

- https://engine.needle.tools/docs/export.html#exporting-lightmaps
- https://github.com/needle-tools/needle-engine-support/blob/main/documentation/technical-overview.md#needle_lightmaps

### NEEDLE_lightmaps

This is a root extension defining a set of lightmaps for the glTF file.

```json
"NEEDLE_lightmaps": {
  "textures": [
    {
      "pointer": "textures/20",
      "type": 1,
      "index": 0
    }
  ]
}
```

> **Note**: At the moment this extension also contains environment texture references. We're planning to change that in a future release. 

| Texture Type | Value |
| -- | -- |
| Lightmap | 0 |
| Environment Map  | 1 |
| Reflection Map | 2 |

How lightmaps are applied is defined in the `MeshRenderer` component inside the [`NEEDLE_components`](#needle_components) extension per node:  

```json
"NEEDLE_components": {
  "builtin_components": [
    {
      "name": "MeshRenderer",
      ...
      "lightmapIndex": 0,
      "lightmapScaleOffset": {
        "x": 1.00579774,
        "y": 1.00579774,
        "z": -0.00392889744,
        "w": -0.00392889744
      },
      ...
    }
  ]
}
```

> **Note**: We may change that in a future release and move lightmap-related data to a `NEEDLE_lightmap` extension entry per node. 


![image](https://user-images.githubusercontent.com/32600939/215252640-e1e8c7e7-edb7-4ede-861e-f973d2d62cf5.png)

![image](https://user-images.githubusercontent.com/32600939/215252667-92af3fe9-2008-4435-8650-8b21c56e5ba2.png)

How it looks in [gltf-viewer](https://gltf-viewer.donmccurdy.com/)
![image](https://user-images.githubusercontent.com/32600939/215252677-e28af83d-9998-42b3-924d-2aef8ce49436.png)

How it looks in [hyperfy.io](https://hyperfy.io/uq9p8o1qjq)

![image](https://user-images.githubusercontent.com/32600939/215253456-757c17d0-10f0-4165-b828-de89b1dadeaf.png)
