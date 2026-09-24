# Path Planning for Exploration

Path-planning benchmark and experiment codebase comparing multiple classical planners for autonomous exploration scenarios.

This repository was created as part of a conference paper study.  
Paper link: https://watermark02.silverchair.com/v006t07a069-imece2023-112606.pdf?token=AQECAHi208BE49Ooan9kkhW_Ercy7Dm3ZL_9Cf3qfKAc485ysgAAAyYwggMiBgkqhkiG9w0BBwagggMTMIIDDwIBADCCAwgGCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQMmKkqwb5tIr89QPwgAgEQgIIC2S0cL_UWbbrGZ706lBMp6lsQmrFeSxwqaaWxAl3YMI_7A5wT-fR1X7R2bbtqarJvbFbJ9hvEYJIqiq-pODIHzlyk2mlSld9_gruqc0YIePLM0mnl7BX8V1T9Lh8xbNmMP6rpzjBlHM4sQNiQ8gsLi51up2heE3-nlCETX4ASJUmXVfnr7QXdiRvoa0RDEwH1gSziW6G8y_1dmogEAwetPTAzGbUmpl6Y_0R8PBUmAPOQ-kbvW2-25G7SF2NZFBqGTgid4jebiJjaBNGW2VbJAzz-nN-v4G88KfMc4BO9u7WcmX7N9xgic0FJ4tkEit3OopRs5JzeEUTP3tv6oIWBsdoUB83WTAERFE96zwL53qkILhfKggYFTuJW1WAv5w9iJF4fy3DeF8kG_BpvHAIm1ZMs0QdBBdAHYMa00o6WByDZmcip6loIbY6eqlITvauUEw5hmbdIyZWRqa2Qm-yVO1n9Ln4J684nVMKaXkIV4cVh4tXBSUQCCIBNZ0WlT1TxPtRhELgtK61rBm-qYZyyzNJZCQlh0UwbRKTFGtCxeMB-VBbCaeBxT4_ZWYOTl06sCa7Fn5D05hKYZyJtiO30UROz7sIDPx43Q9nlmpoMtjSm56QDucHALf2itZRf3FhDSotb4j_fMqPMpo6ZkG4GGOjVPXOxh1aZIUaY_wLlYGAT0b4-Vj4aDYQGd5Gxauk_PBGUh9ieAcyRonea9Lei2NE-Rb8N5MLlcciH0N8CgrBjxic_Vb4h2kYXuth89a_amfdQPBD5tjyM_CLiwpJrk0czqjsRhOk-j6tcAmjj-sDWxeqVsCOpk2iaphX9s_7o_woxWvhOCVW2VU92_u_3G9fZJ8kiwGzhw8-MxfrF9vxizRslSOMpb_OoF9VLdTHRx5OoHw4_ZwOS3gsvvYBko81q_2_uY_Ur_Abv6wluxZAYur-L4zuMJrIEveAVnOhMMtlqalchzwhiHQ

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

## Contributing

Contributions are welcome. Please open an issue or pull request with:

- a clear problem statement,
- reproducible steps (if applicable),
- and a concise summary of changes.
