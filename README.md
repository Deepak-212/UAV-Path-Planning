# UAV Path Planning in Dynamic 3D Environments

This repository contains a Python-based framework for UAV path planning in constrained 3D airspaces. The implementation focuses on a Space-Time A\* algorithm capable of navigating both static obstacles and dynamic, time-dependent entities.

## Project Overview

Path planning for Unmanned Aerial Vehicles (UAVs) requires temporal coordination in addition to spatial awareness. This project transitions from a traditional 3D A\* search to a 4D Space-Time search $(x, y, z, t)$ to ensure safe navigation in environments where obstacles change position over time.

### Technical Features

  * **Voxel-Based Environment:** A modular 3D grid system for mapping complex airspaces and no-fly zones.
  * \**Space-Time A* Search:\*\* An expanded search algorithm that treats time as a fourth dimension, allowing for "Wait" actions to avoid moving obstacles.
  * **Multi-UAV Coordination:** Prioritized planning for multiple agents to prevent mid-air collisions.
  * **Energy-Aware Cost Function:** Trajectory optimization that penalizes vertical ascent to simulate realistic battery constraints.
  * **CSP-Based Scheduling:** Staggered departure times to optimize traffic flow and reduce congestion at mission start.

## Software Architecture

The system utilizes an object-oriented design for modularity:

  * **GridEnvironment:** Manages spatial occupancy and boundary conditions.
  * **DynamicObstacle:** Models moving threats with time-dependent position functions.
  * **Path Planning Module:** Contains the core search logic for both static 3D and dynamic 4D domains.
  * **Visualization Module:** Generates 3D plots and animated outputs for mission review.

## Installation

This project is optimized for Google Colab or local Python 3.x environments.

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/Deepak-212/UAV-Path-Planning.git
    cd UAV-Path-Planning
    ```

2.  **Install dependencies:**

    ```bash
    pip install numpy matplotlib scipy
    ```

## Implementation Details

### Baseline Static Case

The baseline implementation establishes core spatial search logic. It optimizes paths based on Euclidean distance while accounting for vertical movement penalties ($+0.5 \times \Delta z$).

### Dynamic Space-Time Case

The dynamic implementation expands the search space to $(x, y, z, t)$. This allows the UAV to evaluate the safety of a coordinate not just by its position, but by whether a dynamic obstacle will occupy that space at a specific time step.

## Simulation Results

The following animation demonstrates the coordinated mission planning for multiple UAVs. The paths are calculated to avoid both the static environment blocks and the trajectories of other agents.


## Contributors (Team A)

  * Deepak G
  * Adeetya Uppal
  * Magizhan V
  * Sudeep Prajapati

## License

This project is developed for academic purposes as part of the Aerospace and Mechanical Engineering curriculum.
