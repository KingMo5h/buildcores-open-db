# PC Component Viewer Sample

This sample demonstrates how to load various component data from the OpenDB and
visualize simple 3D representations using [Three.js](https://threejs.org/).
You can pick a PC case, GPU, CPU and RAM module from the OpenDB and the viewer
displays color coded placeholder meshes for each part.

## Running the Example

1. Start a local HTTP server in this directory (for example with Python):
   ```bash
   python3 -m http.server 8000
   ```
2. Open your browser at `http://localhost:8000/index.html`.

Use the dropdowns to select components. The viewer splits the layout into a 70%
3D viewer and a 30% control panel styled like a modern web page. When a part is
selected the panel shows basic information parsed from the component's JSON such
as GPU interface, CPU clocks and RAM type. Price information is shown if present
in the JSON but most entries do not include a price.

