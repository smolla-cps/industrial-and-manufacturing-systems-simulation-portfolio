# Industrial and Manufacturing Systems Simulation Portfolio

A structured portfolio of FlexSim models covering discrete-event simulation, Process Flow, conveyors, AGVs, warehouse operations, experimentation, statistics, emulation, and reinforcement learning integration.

**Repository:** [https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio)

## Portfolio Contents

| No. | Folder | Main Topics |
|---:|---|---|
| 01 | [FlexSim Basics Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/01_FlexSim_Basics_Guided_Models) | Basic 3D modeling, fixed resources, object connections, processing logic, introductory Process Flow |
| 02 | [FlexSim Task Logic Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/02_FlexSim_Task_Logic_Guided_Models) | Task executers, transportation logic, operator-based material movement, task logic |
| 03 | [FlexSim Coordinated Tasks Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/03_FlexSim_Coordinated_Tasks_Guided_Models) | Coordinated task logic, multiple task executers, synchronized operations |
| 04 | [FlexSim Conditional Tasks Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/04_FlexSim_Conditional_Tasks_Guided_Models) | Conditional tasks, arrays, subflows, nested subflows, dynamic destination selection |
| 05 | [FlexSim AGV Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/05_FlexSim_AGV_Guided_Models) | AGV paths, control points, Process Flow control, elevators, custom AGV settings |
| 06 | [FlexSim Shared Assets Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/06_FlexSim_Shared_Assets_Guided_Models) | Lists, resources, zones, shared assets, task coordination |
| 07 | [FlexSim Task Sequences Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/07_FlexSim_Task_Sequences_Guided_Models) | Task sequences, reusable subflows, Process Flow instances, customized operator tasks |
| 08 | [FlexSim Sub Process Flows Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/08_FlexSim_Sub_Process_Flows_Guided_Models) | Parent-child tokens, Run Sub Flow, conditional subflows, multiple Finish activities |
| 09 | [FlexSim Process Flow Instances Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/09_FlexSim_Process_Flow_Instances_Guided_Models) | Object Process Flow, reusable instances, local assets, dynamic references |
| 10 | [FlexSim Custom Objects Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/10_FlexSim_Custom_Objects_Guided_Models) | Custom fixed-resource logic, custom task-executer behavior, event-driven Process Flow |
| 11 | [FlexSim Conveyors Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/11_FlexSim_Conveyors_Guided_Models) | Sorting, merging, slug building, gap control, Merge Controllers, power-and-free conveyors |
| 12 | [FlexSim Statistics Collector Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/12_FlexSim_Statistics_Collector_Guided_Models) | Statistics Collector, event-based data collection, tracked variables, timer events, dashboard charts |
| 13 | [FlexSim Experimenter Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/13_FlexSim_Experimenter_Guided_Models) | Scenario analysis, model parameters, performance measures, replications, optimization |
| 14 | [FlexSim Advanced Task Sequences and Subflows Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/14_FlexSim_Advanced_Task_Sequences_and_Subflows_Guided_Models) | Advanced task sequences, synchronized operators, subflows, series processors, batch transport |
| 15 | [FlexSim Process Flow Lists Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/15_FlexSim_Process_Flow_Lists_Guided_Models) | Global lists, Process Flow lists, WHERE/ORDER BY queries, partitions, inventory and storage logic |
| 16 | [FlexSim Process Flow Zones Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/16_FlexSim_Process_Flow_Zones_Guided_Models) | Zones, partitions, subsets, calculations, constraints, rack and conveyor-zone logic |
| 17 | [FlexSim Basic Emulation Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/17_FlexSim_Basic_Emulation_Guided_Models) | PLC-style control, photo eyes, conveyor motors, variables, area-restriction logic |
| 18 | [FlexSim Advanced Conveyor Control Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/18_FlexSim_Advanced_Conveyor_Control_Guided_Models) | Advanced conveyor control, reversible conveyors, synchronization, order routing, slug building, merge control |
| 19 | [FlexSim Advanced AGV Systems Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/19_FlexSim_Advanced_AGV_Systems_Guided_Models) | AGV API, NextWorkPoint, work forwarding, parking, battery tracking, pickup/drop-off logic, trailers |
| 20 | [FlexSim Warehouse Operations Guided Models](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/20_FlexSim_Warehouse_Operations_Guided_Models) | Warehouse layout, Storage System, inventory, inbound/outbound flow, A* navigation, picking rules, order generation, performance |
| 21 | [FlexSim Changeover Times RL PPO](https://github.com/smolla-cps/industrial-and-manufacturing-systems-simulation-portfolio/tree/main/21_FlexSim_Changeover_Times_RL_PPO) | FlexSim-Python integration, Gymnasium environment, PPO training, policy testing, inference |

## Main Tools and Methods

- **Simulation:** FlexSim, discrete-event simulation, Process Flow
- **Material handling:** conveyors, AGVs, task executers, routing, parking, merging, batching
- **Warehouse modeling:** Storage System, racks, slot labels, A* navigation, picking and order processing
- **Data and analysis:** Global Tables, Excel import, Statistics Collector, Experimenter, SQL-style queries
- **Programming and AI:** FlexScript, Python, Gymnasium, Stable-Baselines3, PPO

## Recommended Order

Start with folders **01–04** for FlexSim fundamentals and task logic, continue through **05–17** for Process Flow, AGVs, conveyors, statistics, experimentation, lists, zones, and emulation, then use **18–20** for advanced conveyor, AGV, and warehouse systems. Folder **21** contains the FlexSim–reinforcement learning integration project.

Each folder contains its own `README.md` with the model sequence, concepts practiced, folder structure, and usage notes.
