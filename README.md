# README.md

## Project Overview

This project focuses on finite element analysis of geological models, particularly simulating the complex processes of crustal deformation. With the help of PyLith software, we have successfully constructed a fine mesh model and executed a series of simulation steps to explore the dynamic behavior mining-induced rupture. Through this README, you will be able to understand the model configuration and processing methods.

## Project File Organization

- `mesh.exo`: Contains the completed fine mesh model file.
- `step00.cfg`: PyLith configuration file for precise control of simulation startup and execution.
- `fault_slipweakening.spatialdb`: Defines key parameters used in the simulation, such as friction coefficient.

## Analysis Parameters

Our current analysis relies on the mechanical parameters specified in Table 1 and Table 2. With the help of PyLith 2.2.2, we are able to precisely simulate the dynamic behavior mining-induced rupture

### Mechanical Parameters Used in the Simulation:

#### Table 1: Parameters implemented in the numerical simulation

| Parameter | Value | Parameter | Value |  
| --- | --- | --- | --- |  
| Fault dip angle, φ (°) | 30 | Depth, h (m) | 0-1600 |  
| Background stress ratio, rb | 2.0 | Mining distance, Dm (m) | -60 and +60 |  
| Cohesion stress, C (MPa) | 0 | Mining level, (m) | 1000 |  
| Dip angle of the coal seam, (°) | 0 | Panel width, (m) | 200 |  
| Static friction coefficient, μs | 0.7 | Mining thickness, (m) | 10 |  
| Dynamic friction coefficient, μd | 0.6 | |  |


#### Table 2: Heterogeneity of coal seam roof and floor layers in the numerical model

| Layer | Thickness (m) | Young's modulus E (GPa) | Poisson's ratio ν | Shear modulus G (GPa) | Density ρ (kg/m³) | Vp (km/s) | Vs (km/s) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Overlying strata | 975 | 15 | 0.25 | 6.0 | 2400 | 2.739 | 1.581 |
| Roof | Mudstone | 20 | 3.8 | 0.18 | 1.6 | 2200 | 1.369 | 0.853 |
| Coal | Coal | 10 | 2.0 | 0.27 | 0.8 | 1300 | 1.387 | 0.784 |
| Floor | Sandstone | 20 | 8.3 | 0.15 | 3.6 | 2700 | 1.802 | 1.155 |
| Underlying strata | 475 | 15 | 0.25 | 6.0 | 2400 | 2.739 | 1.581 |

## Running Guide

1. Refer to the official PyLith documentation to ensure the correct installation of PyLith version 2.2.2.
2. In the project root directory, start the simulation process with the following command:

```bash
pylith step00.cfg
```

After the simulation is complete, all results will be output to the `output` folder.

## Result Output and Viewing

After the simulation ends, you can find the following `.xmf` formatted result files in the `output` folder:

- `fault_traction.xmf`
- `model-all-disp.xmf`

These files record various data during the simulation process in detail, and you can use software like ParaView for viewing and analysis.

### Result Viewing Method:

- Open the ParaView software.
- Import `.xmf` files to view the simulation results.
- Utilize ParaView's rich toolset, such as slicing, isosurfacing, etc., to showcase the simulation data in all directions.
- If further data processing is required, you can use ParaView's Filter function to export the data in CSV format, providing convenience for subsequent in-depth analysis, such as calculating slip distrib
