# `GARDEYN`

>Gardeyn, J., Berghe, G. V., & Wauters, T. (2025). An open-source heuristic to reboot 2D nesting research. arXiv preprint https://doi.org/10.48550/arXiv.2509.13329.

## About
This dataset contains ten 2D irregular strip packing instances (`gardeyn0` to `gardeyn9`) derived from real-world applications in the fashion/textile, metal sheet, CNC, shipbuilding and printing industries.

Each instance has two variants: 
- `gardeyn0`-`gardeyn9`: item rotation is restricted to 90-degree increments.
- `*_c` suffix: items can be rotated to any angle (continuous rotation).

Visualizations of all instances can be found in the publication linked above.

## Structure
The instances are provided as JSON files, with the structure following the one used in the [`jagua-rs`](https://github.com/JeroenGar/jagua-rs) library.

### Example
```javascript
{
  "name": "gardeyn0",
  "items": [
    { //the first type of item to be packed
      "id": 0,
      "demand": 10, // number of copies of this item
      "allowed_orientations": [...], // if defined, only these orientations are allowed (in degrees). If undefined, any orientation is allowed.
      "shape": {
        "type": "simple_polygon", // geometry type of the item
        "data": [ // coordinates of the simple polygon, as [x,y] tuples
          [
            630.0,
            4544.0
          ],
          [
            66.0,
            4351.0
          ],
        ...
        ]
      }
    },
    ...
  ],
  "strip_height": 20000.0 // size of the fixed dimension
}
```

More detailed documentation on the JSON structure can be found on [docs.rs](https://docs.rs/jagua-rs/latest/jagua_rs/io/index.html) or on [GitHub Pages](https://jeroengar.github.io/jagua-rs/jagua_rs/io/index.html).
