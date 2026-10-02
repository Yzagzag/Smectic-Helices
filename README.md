# Smectic Filaments, Ribbons, and Helices

This repository provides Python code and Jupyter notebooks for constructing and visualizing director fields in filamentous smectic materials, including single filaments, ribbons, and double-helical structures.

The modeled director fields are generated from prescribed geometries using local tangent planes along filament centerlines. These local director configurations are mapped into a global three-dimensional coordinate system, interpolated onto regular grids, and can be passed to LCPOM to simulate polarized optical microscopy textures for comparison with experimental observations.

<p align="center">
  <img
    src="Smectic-Filaments.png"
    alt="Simulated single filament optical textures"
    width="800"
  />
  <img
    src="Smectic-Ribbons.png"
    alt="Simulated conjoined filament ribbon optical textures"
    width="800"
  />
</p>

## Features

- **Director Field Generation**
  - Single smectic filament geometries
  - Smectic ribbon geometries
  - Double-helical filament geometries
  - Three-dimensional director field construction from local cross-sectional director configurations

- **Local Tangent-Plane Construction**
  - Analytical calculation of filament centerlines and tangent vectors
  - Construction of local orthonormal coordinate frames
  - Mapping of local director fields into the global coordinate system

- **Director Field Interpolation**
  - Conversion of scattered director data into regularly sampled three-dimensional fields
  - Nearest-neighbor and spatial interpolation tools for visualization and optical simulations

- **Optical Texture Simulation**
  - Integration with LCPOM
  - Simulation of polarized-light propagation through three-dimensional director fields
  - Reconstruction of simulated optical microscopy textures

- **Visualization**
  - Three-dimensional visualization of filament and helix geometries
  - Director-field visualization
  - Cross-sectional and tilted-plane visualization
  - Generation of graphics and animations for inspecting modeled director configurations

## Repository Structure

    Smectic-Helices/
    │
    ├── README.md
    │
    ├── Smectic_Filaments.ipynb
    ├── Smectic_Ribbons.ipynb
    ├── Smectic-Double-Coil-Generation.ipynb
    │
    ├── Smectic-Filaments.png
    ├── Smectic-Ribbons.png
    │
    ├── Graphics/
    │   ├── Graphics_3D.ipynb
    │   ├── director_raw.npz
    │   ├── Interpolated_director_Lx400_Ly400_Lz400.npz
    │   └── helix.png
    │
    ├── lc-pom/
    │   ├── LCPOM_Usage.ipynb
    │   └── params.py
    │
    └── old_versions/

## Main Notebooks

**Smectic_Filaments.ipynb**

Generates director fields for individual filament geometries and provides tools for inspecting the resulting director configurations.

**Smectic_Ribbons.ipynb**

Constructs director fields for conjoined filamentous ribbon geometries.

**Smectic-Double-Coil-Generation.ipynb**

Generates the three-dimensional geometry and director field of a double-helical smectic filament structure using local tangent-plane cross sections.

**Graphics/Graphics_3D.ipynb**

Provides visualization and interpolation tools for examining the generated three-dimensional director fields, including planar slices and helix geometry.

**lc-pom/LCPOM_Usage.ipynb**

Provides an example workflow for passing generated director fields to LCPOM and calculating simulated polarized optical microscopy textures.

## Data Files

To work, the `Graphics` directory should contain director-field data generated from the double-helix model.

**director_raw.npz**

Contains the scattered three-dimensional director-field data generated directly from the filament geometry.

Typical arrays include:

    final_points
    final_vectors

where `final_points` contains the spatial coordinates and `final_vectors` contains the corresponding director orientations.

**Interpolated_director_Lx400_Ly400_Lz400.npz**

Contains the director field interpolated onto a regular three-dimensional grid for visualization and optical calculations.

## Prerequisites

- Python 3.8 or higher
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook or JupyterLab
- LCPOM: https://github.com/depablogroup/lc-pom

The relevant LCPOM workflow and parameter file used with this repository are included in the `lc-pom` directory.

## Installation

Clone the repository:

    git clone https://github.com/yzagzag/Smectic_Helices.git
    cd Smectic_Helices

Install the required Python packages if necessary:

    pip install numpy scipy matplotlib jupyter

Then start JupyterLab:

    jupyter lab

## Usage

A typical workflow is:

1. Open one of the geometry-generation notebooks:

       Smectic_Filaments.ipynb
       Smectic_Ribbons.ipynb
       Smectic-Double-Coil-Generation.ipynb

2. Define the desired geometric and director-field parameters.

3. Generate the local director configurations and map them into the global three-dimensional geometry.

4. Save the resulting director field as scattered or interpolated data.

5. Use `Graphics/Graphics_3D.ipynb` to inspect the resulting three-dimensional director field.

6. Use `lc-pom/LCPOM_Usage.ipynb` to calculate simulated polarized optical microscopy textures.

## Customization

The notebooks can be modified to explore different geometries and optical conditions.

Examples include:

- Filament radius
- Helix radius
- Helical pitch
- Number of turns
- Filament spacing
- Local director configuration
- Spatial grid resolution
- Interpolation parameters
- Slice-plane orientation
- Polarizer and analyzer angles used in LCPOM

## LCPOM

Optical simulations are performed using the LCPOM package developed by the de Pablo group:

https://github.com/depablogroup/lc-pom

LCPOM propagates polarized light through a three-dimensional liquid-crystal director field and can be used to generate simulated polarized optical microscopy textures from the director configurations produced in this repository.

## Contact

Yvonne Zagzag

University of Luxembourg

Email: yvonne.zagzag@uni.lu
