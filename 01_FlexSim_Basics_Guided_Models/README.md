# FlexSim Basics — Guided Models

This folder contains a sequence of FlexSim models that I built by following the official **Autodesk FlexSim 2027 Basics Tutorial**. The models document my hands-on practice with 3D discrete-event simulation, simulation data collection, Process Flow modeling, and integration between Process Flow and 3D objects.


## Official Tutorial

Autodesk FlexSim 2027 — FlexSim Basics Tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_flexsimbasics_basicsoverview_html

## Tutorial Sequence

The official Basics Tutorial progresses through four connected tasks:

### 1.1 — Build a 3D Model

A customer-service simulation is constructed using FlexSim's 3D modeling environment.

**Concepts practiced**
- Creating and arranging 3D simulation objects
- Source, Queue, Processor, and Sink objects
- Connecting objects and defining item flow
- Customer arrivals and queueing
- Global item lists
- Waiting-time logic
- Statistical distributions for arrivals and service times
- Running and testing a discrete-event simulation model

**Model:** `1.1_Build a 3D Model.fsm`

### 1.2 — Get Data from the 3D Model

The 3D model is extended with data collection and visualization tools so that model performance can be measured and interpreted.

**Concepts practiced**
- Dashboards
- Charts and tables
- Statistics collectors
- Queue-content tracking
- Customer waiting-time statistics
- Throughput measurement
- Happy vs. unhappy customer counts
- Service-desk utilization
- Simulation-output analysis

**Model:** `1.2 Get Data from the 3D Model.fsm`

### 1.3 — Build a Process Flow Model

The same customer-service system is represented using FlexSim Process Flow, providing a more logic-oriented representation of the simulation.

**Concepts practiced**
- General Process Flow
- Tokens and activities
- Inter-Arrival Source
- Acquire Resource and Release Resource
- Delay activities
- Shared resources
- Maximum waiting-time logic
- Process Flow statistics
- Comparing Process Flow and 3D modeling approaches

**Model:** `1.3 Build a Process Flow Model.fsm`

### 1.4 — Link the Models

The Process Flow logic is connected to the 3D model so that Process Flow controls the behavior of the visual simulation. An additional service desk is also introduced to examine how added capacity changes system performance.

**Concepts practiced**
- Linking Process Flow with 3D objects
- Token labels and object references
- Object groups
- Multiple service desks and workers
- Task executers
- Travel activities
- Split and Synchronize activities
- Resource acquisition and release
- Coordinating customers and service workers
- Evaluating the effect of additional resources

**Model:** `1.4 Link the Models.fsm`

## Files

```text
FlexSim_Basics_Guided_Models/
├── README.md
├── requirements.txt
├── 1.1_Build a 3D Model.fsm
├── 1.2 Get Data from the 3D Model.fsm
├── 1.3 Build a Process Flow Model.fsm
└── 1.4 Link the Models.fsm
```

## How to Run the Models

1. Install Autodesk FlexSim.
2. Open the desired `.fsm` file in FlexSim.
3. Reset the model before a new simulation run.
4. Run the model and observe the 3D view, Process Flow, dashboards, or statistics available for that stage of the tutorial.
5. Open the models in numerical order to see how the same system develops from a basic 3D model into an integrated 3D + Process Flow model.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim 3D modeling
- Process Flow modeling
- Queue and resource modeling
- Statistical input modeling
- Simulation data collection
- Dashboard and performance-metric development
- Resource-utilization analysis
- 3D and Process Flow integration

## Attribution

The model structure and learning exercises in this folder follow the official **Autodesk FlexSim 2027 Basics Tutorial**. The `.fsm` files in this folder are my implementations created while completing those guided exercises.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_flexsimbasics_basicsoverview_html
