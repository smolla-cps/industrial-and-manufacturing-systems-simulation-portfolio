[README.md](https://github.com/user-attachments/files/33291347/README.md)
# Industrial and Manufacturing Systems Simulation Portfolio

This repository presents a structured collection of FlexSim simulation models covering simulation fundamentals, Process Flow logic, task sequences, lists, zones, conveyors, AGV systems, warehouse operations, experimentation, statistics, emulation, and reinforcement learning integration.

The folders are arranged in a progressive sequence, beginning with basic FlexSim modeling and moving toward advanced material-handling systems, warehouse simulation, and simulation-based reinforcement learning.

## Portfolio Structure

| Folder | Focus |
|---|---|
| `01_FlexSim_Basics_Guided_Models` | FlexSim modeling fundamentals, basic 3D objects, connections, processing logic, and introductory Process Flow concepts |
| `02_FlexSim_Task_Logic_Guided_Models` | Task executers, transportation logic, task sequences, and operator-based material movement |
| `03_FlexSim_Coordinated_Tasks_Guided_Models` | Coordinated task logic, multiple task executers, and synchronized operations |
| `04_FlexSim_Conditional_Tasks_Guided_Models` | Conditional task logic, arrays, subflows, nested subflows, and dynamic destination selection |
| `05_FlexSim_AGV_Guided_Models` | AGV path networks, control points, Process Flow-based AGV control, elevators, and custom AGV settings |
| `06_FlexSim_Shared_Assets_Guided_Models` | Process Flow lists, resources, zones, task coordination, and shared-asset logic |
| `07_FlexSim_Task_Sequences_Guided_Models` | Reusable task sequences, subflows, Process Flow instances, and customized operator tasks |
| `08_FlexSim_Sub_Process_Flows_Guided_Models` | Parent-child tokens, Run Sub Flow, conditional subflows, and multiple Finish activities |
| `09_FlexSim_Process_Flow_Instances_Guided_Models` | Object Process Flow, reusable instances, local assets, dynamic references, and scalable model logic |
| `10_FlexSim_Custom_Objects_Guided_Models` | Custom fixed-resource and task-executer behavior using Process Flow |
| `11_FlexSim_Conveyors_Guided_Models` | Conveyor sorting, merging, slug building, gap control, Merge Controllers, and power-and-free systems |
| `12_FlexSim_Statistics_Collector_Guided_Models` | Event-based data collection, Statistics Collector tables, tracked variables, timer events, and dashboard charts |
| `13_FlexSim_Experimenter_Guided_Models` | Scenario analysis, simulation replications, performance measures, Experimenter, and optimization |
| `14_FlexSim_Advanced_Task_Sequences_and_Subflows_Guided_Models` | Advanced task sequences, synchronized operators, reusable subflows, series processors, and batch transport |
| `15_FlexSim_Process_Flow_Lists_Guided_Models` | Global and Process Flow lists, queries, partitions, inventory matching, storage logic, and crane coordination |
| `16_FlexSim_Process_Flow_Zones_Guided_Models` | Process Flow Zones, partitions, subsets, calculations, constraints, rack systems, and conveyor restrictions |
| `17_FlexSim_Basic_Emulation_Guided_Models` | PLC-style control logic, photo-eye sensors, conveyor motors, variables, and area-restriction logic |
| `18_FlexSim_Advanced_Conveyor_Control_Guided_Models` | Advanced conveyor control, reversible conveyors, synchronization, order-based routing, recirculation, slug building, and merge control |
| `19_FlexSim_Advanced_AGV_Systems_Guided_Models` | Advanced AGV templates, AGV API, NextWorkPoint logic, work forwarding, parking, battery tracking, and trailer-based transport |
| `20_FlexSim_Warehouse_Operations_Guided_Models` | Warehouse layout, Storage System, inventory, inbound and outbound flows, A* navigation, picking rules, order generation, and model performance |
| `21_FlexSim_Changeover_Times_RL_PPO` | FlexSim–Python integration, Gymnasium environment, PPO training, model inference, and reinforcement learning |

## Repository Organization

```text
industrial-and-manufacturing-systems-simulation-portfolio/
├── 01_FlexSim_Basics_Guided_Models/
├── 02_FlexSim_Task_Logic_Guided_Models/
├── 03_FlexSim_Coordinated_Tasks_Guided_Models/
├── 04_FlexSim_Conditional_Tasks_Guided_Models/
├── 05_FlexSim_AGV_Guided_Models/
├── 06_FlexSim_Shared_Assets_Guided_Models/
├── 07_FlexSim_Task_Sequences_Guided_Models/
├── 08_FlexSim_Sub_Process_Flows_Guided_Models/
├── 09_FlexSim_Process_Flow_Instances_Guided_Models/
├── 10_FlexSim_Custom_Objects_Guided_Models/
├── 11_FlexSim_Conveyors_Guided_Models/
├── 12_FlexSim_Statistics_Collector_Guided_Models/
├── 13_FlexSim_Experimenter_Guided_Models/
├── 14_FlexSim_Advanced_Task_Sequences_and_Subflows_Guided_Models/
├── 15_FlexSim_Process_Flow_Lists_Guided_Models/
├── 16_FlexSim_Process_Flow_Zones_Guided_Models/
├── 17_FlexSim_Basic_Emulation_Guided_Models/
├── 18_FlexSim_Advanced_Conveyor_Control_Guided_Models/
├── 19_FlexSim_Advanced_AGV_Systems_Guided_Models/
├── 20_FlexSim_Warehouse_Operations_Guided_Models/
├── 21_FlexSim_Changeover_Times_RL_PPO/
└── README.md
```

Each folder includes its own documentation describing the model sequence, concepts practiced, recommended file structure, and usage requirements.

## Main Technical Areas

### Discrete-Event Simulation

The portfolio covers the construction and control of manufacturing, material-handling, and warehouse systems using FlexSim 3D objects and Process Flow.

### Process Flow

Models use Process Flow for:
- task sequences
- subflows
- object and instanced flows
- conditional routing
- lists and resource shared assets
- zones
- event-triggered logic
- token labels
- synchronization
- custom control logic

### Material Handling

Material-handling models include:
- conveyors
- operators
- AGVs
- AGV control points
- reversible conveyors
- conveyor merging
- slug building
- parking and charging logic
- multi-floor AGV transport
- trailer-based AGV transport

### Warehouse Simulation

Warehouse models include:
- rack and Storage System modeling
- address schemes
- slot labels
- initial inventory
- inbound storage
- historical and randomized order generation
- picker work lists
- FIFO/LIFO handling
- picker roles
- A* navigation
- query-based work assignment
- execution-speed improvement

### Data, Statistics, and Experimentation

The portfolio also includes:
- Global Tables
- Excel-based data import
- SQL-style queries
- `Table.query()`
- `GROUP BY`
- `ARRAY_AGG()`
- `JOIN`
- Statistics Collector
- dashboard charts
- performance measures
- simulation replications
- scenario analysis
- optimization
- Performance Profiler

### Reinforcement Learning Integration

The reinforcement learning project connects FlexSim with Python through a custom Gymnasium environment and uses Stable-Baselines3 PPO for policy training and inference.

## How to Explore the Portfolio

1. Start with folders `01`–`04` for FlexSim fundamentals and task logic.
2. Continue with folders `05`–`10` for AGVs, shared assets, task sequences, subflows, instances, and custom objects.
3. Use folders `11`–`17` for conveyors, statistics, experimentation, lists, zones, and emulation.
4. Use folders `18`–`20` for advanced conveyor, AGV, and warehouse systems.
5. Open folder `21` for the FlexSim–reinforcement learning integration project.
6. Read the `README.md` inside each folder before opening the model files.

## Skills Demonstrated

- Discrete-event simulation
- Industrial and manufacturing systems modeling
- FlexSim 3D modeling
- FlexSim Process Flow
- Task sequences
- Subflows
- Process Flow instances
- Lists, resources, and zones
- Conveyor-system modeling
- AGV-system modeling
- Warehouse simulation
- Storage System modeling
- A* navigation
- PLC-style emulation
- Event-driven control
- FlexScript
- SQL-style queries
- Data-driven simulation
- Statistics collection
- Scenario analysis
- Simulation-based optimization
- Model performance analysis
- Python integration
- Gymnasium
- Stable-Baselines3
- Proximal Policy Optimization
- Reinforcement learning

## Learning Progression

```text
FlexSim Fundamentals
        ↓
Task Logic + Coordinated Tasks
        ↓
Conditional Logic + Subflows
        ↓
AGVs + Shared Assets
        ↓
Task Sequences + Process Flow Instances
        ↓
Conveyors + Statistics + Experimentation
        ↓
Lists + Zones + Emulation
        ↓
Advanced Conveyor Control
        ↓
Advanced AGV Systems
        ↓
Warehouse Operations
        ↓
FlexSim + Reinforcement Learning
```

The portfolio progresses from core simulation modeling to advanced material-handling control, warehouse-system logic, data-driven simulation, experimentation, and reinforcement learning integration.
