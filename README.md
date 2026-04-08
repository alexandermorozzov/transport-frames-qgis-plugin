# Transport Frames QGIS Plugin

This plugin adds `transport_frames` workflows to QGIS Processing.
It helps configure a Python runtime and run graph, frame, grading, and indicator calculations directly in QGIS.

### What the plugin does

- Prepares and uses a Python environment for `transport_frames` (managed/custom mode).
- Builds road-network and intermodal graphs.
- Builds a weighted transport frame.
- Grades territories against the transport frame.
- Computes accessibility, connectivity, length, and density indicators.

### Where to find tools

- `Processing Toolbox -> Transport Frames`
- Algorithm groups:
- `1 - Environment`
- `2 - Graph`
- `3 - Frame`
- `4 - Grade`
- `5 - Indicators`

### Algorithms by group

#### 1 - Environment

- `Setup Python Environment`: creates/updates a `venv` in the active QGIS profile, installs the package, and switches to managed mode.
- `Environment Status`: shows current runtime mode and stored Python paths.

#### 2 - Graph

- `Get Drive Graph`: builds a road graph from an `OSM relation ID` or territory boundary.
- `Add Roads`: inserts new roads into an existing drive graph (`reg` is required).
- `Get Intermodal Graph`: builds an intermodal graph (public transport + walk links).

#### 3 - Frame

- `Get Weighted Frame`: builds a weighted transport frame from the input graph and supporting layers.

#### 4 - Grade

- `Grade Territory`: calculates territory grades based on the weighted transport frame.

#### 5 - Indicators

- `Get Roads Length`: total road length by polygons.
- `Get Roads Density`: road density by polygons.
- `Get Roads Length by Type`: road lengths by `reg` classes.
- `Get Railways Length`: railway length by polygons.
- `Get Connectivity`: connectivity indicator (median travel time).
- `Get Service Count`: number of services inside polygons.
- `Get Service Accessibility`: service accessibility (minutes).
- `Get Service Count for Territory`: number of services for selected territories.
- `Get Service Accessibility for Territory`: service accessibility for selected territories.

### Requirements

- QGIS 3.x (metadata minimum: `3.0`).
- Python `3.11+` for environment setup.

### Quick start

1. Run `Setup Python Environment` and install `transport_frames` into the managed environment.
2. Verify runtime mode with `Environment Status`.
3. Build a graph (`Get Drive Graph` or `Get Intermodal Graph`).
4. Run `Frame`, `Grade`, and required `Indicators`.

### Repositories

- Plugin: https://github.com/alexandermorozzov/transport-frames-qgis-plugin
- Upstream library (`transport_frames`): https://github.com/alexandermorozzov/tf
