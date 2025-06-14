
# PC Component Viewer Sample

This sample demonstrates how to load various component data from the OpenDB and
visualize simple 3D representations using [Three.js](https://threejs.org/).
You can pick a PC case, GPU, CPU and RAM module from the OpenDB and the viewer
displays color coded placeholder meshes for each part.
=======
# PC Case Viewer Sample

This sample demonstrates how to load case data from the OpenDB and visualize
the case dimensions using [Three.js](https://threejs.org/).


## Running the Example

1. Start a local HTTP server in this directory (for example with Python):
   ```bash
   python3 -m http.server 8000
   ```
2. Open your browser at `http://localhost:8000/index.html`.


Use the dropdowns to select components. The viewer splits the layout into a 70%
3D viewer and a 30% control panel styled like a modern web page. When a part is
chosen its details such as PCIe interface, memory type or case dimensions are
shown beneath the dropdown. Price is displayed when present in the JSON data.
=======
Use the dropdown to select a PC case. The viewer displays a simple 3D box
representing the case's dimensions.


