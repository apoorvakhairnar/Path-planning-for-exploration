# Path Planning for Exploration

Path-planning benchmark and experiment codebase comparing multiple classical planners for autonomous exploration scenarios.

This repository was created as part of a conference paper study.  
Paper link: https://asmedigitalcollection.asme.org/IMECE/proceedings/IMECE2023/87639/V006T07A069/1195927

## Features

- Comparative evaluation of:
  - A* (`astar.py`)
  - RRT (`rrt.py`)
  - RRT* (`rrtstar.py`)
  - Probabilistic RRT / pRRT (`pRRTNew.py`)
  - Artificial Potential Field / APF (`apf.py`)
- Multi-goal sequential exploration experiment driver (`pathplanning.py`)
- Trajectory plotting and CSV export for planner outputs

## Repository Structure

- `pathplanning.py` — main experiment script that runs all planners over a predefined scenario
- `astar.py` — A* grid planner implementation
- `rrt.py` — Rapidly-exploring Random Tree (RRT) planner
- `rrtstar.py` — RRT* planner
- `pRRTNew.py` — probabilistic RRT variant
- `apf.py` — Artificial Potential Field planner

## Installation

1. Clone the repository.
2. Create and activate a Python environment (recommended).
3. Install dependencies:

```bash
pip install numpy matplotlib pandas
```

## Getting Started

Run the full comparative experiment:

```bash
python pathplanning.py
```

This script iterates through predefined start/goal pairs, executes all planners, and writes per-planner summary CSV files.

## Usage Notes

- The scripts save trajectory CSVs/figures into planner-specific subfolders (for example: `Astar/Outdoor_0_05`, `RRT/Outdoor_0_05`, `RRTstar/Outdoor_0_05`, `pRRT/Outdoor_0_05`, `APF/Outdoor_0_05`).
- Ensure those output directories exist before running, or update the save paths in scripts.
- Some plotting code references a local absolute image path (e.g., `C:/D/ABHYAAS/Coding/imagesx10/env1.png`). Update or remove those references for your environment.

## Example Workflow

1. Adjust scenario settings (start/goal positions and obstacles) in `pathplanning.py`.
2. Run `python pathplanning.py`.
3. Review generated CSVs and plots for trajectory quality and computation-time comparison.

## Contributors

- Apoorva Khairnar
- Shathushan Sivashangaran
- Azim Eskandarian

## Contributing

Contributions are not welcome.
