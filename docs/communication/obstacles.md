---
layout: default
parent: Communication
title: Obstacles API
nav_order: 2
permalink: communication/obstacles
---

# Obstacles API

Following JSON Schemas are used to communicate obstacle details from the simualtor to visualizer.
(Not a fully completed yet)

```json
{
    id: 1000,
    geometry: { … },
    material : { … },
    position: { x: 0, y: 0  },
    rotation:{ x: 0,  y: 0,  z: 0 }
}
```
### Geometry

Available geometric shapes, with options:
- Box Geometry

    - width: required, ex: 300,
    - height: required, ex: 5,
    - depth: required, ex: 20

- Cylinder Geometry

    - radiusTop: required, ex: 20,
    - radiusBottom: required, ex: 20,
    - height: required, ex: 20
    - heightSegments: optional, default: 2
    - radialSegments: optional, default: 16

- Sphere Geometry

    - radius: required, ex: 20
    - widthSegments: optional, default: 16
    - heightSegments: optional, default: 16

#### Geometry for a box shaped object:
```json
{
    type: 'BoxGeometry',
    width: 300,
    height: 5,
    depth: 20
}
```

#### Geometry for a cylinder shaped object:
```json
{
    type: 'CylinderGeometry',
    radiusTop: 20,
    radiusBottom: 20,
    height: 20
}
```

#### Geometry for a sphere shaped object:
```json
{
    type: 'SphereGeometry',
    radius: 20
}
```


### Material

Available materials:
- MeshBasicMaterial
(https://threejs.org/docs/#api/en/materials/MeshBasicMaterial)

- MeshNormalMaterial
(https://threejs.org/docs/api/en/materials/MeshNormalMaterial.html)

- MeshPhongMaterial
(https://threejs.org/docs/#api/en/materials/MeshPhongMaterial)

- MeshPhysicalMaterial
(https://threejs.org/docs/#api/en/materials/MeshPhysicalMaterial)

- MeshStandardMaterial
(https://threejs.org/docs/#api/en/materials/MeshStandardMaterial)

Example:
```json
{
    type: 'MeshPhysicalMaterial',
    properties: {
        color:0x7602f9,
    }
}
```

Full Example:
```json
{
  "geometry":{"type":"BoxGeometry","width":300,"height":20,"depth":5},
  "material":{"type":"MeshPhysicalMaterial","properties":{"color":7734009}},
  "position":{"x":0,"y":0},
  "rotation":{"x":0,"y":0,"z":0}
}
```
