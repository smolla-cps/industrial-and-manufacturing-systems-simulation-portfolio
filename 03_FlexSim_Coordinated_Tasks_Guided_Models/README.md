# FlexSim Coordinated Tasks — Guided Models

This folder contains FlexSim models that I built while following the official **FlexSim Tutorial 2 — Coordinated Tasks**.

The tutorial focuses on task coordination in Process Flow. It begins with a standard transportation-task model and then extends that model so two operators can work together on the same heavy-box transportation task.

> **Note:** These are guided learning models based on the official FlexSim tutorial. They are included in this portfolio to document my FlexSim training and hands-on modeling practice and are not presented as independently designed projects.

## Official Tutorial

FlexSim — Tutorial 2: Coordinated Tasks:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_tasklogic_tutorial2coordinatedtasks_coordinatedtasksoverview_html

## Tutorial Sequence

### 2.1 — Create Standard Loading Tasks

This model reviews how to build standard transportation tasks in Process Flow before introducing coordinated tasks.

Two operators transport boxes from a queue to two processors. The Process Flow controls box creation, processor and operator acquisition, task-sequence creation, loading, unloading, resource release, and completion logic.

**Concepts practiced**
- 3D object modeling with queues, operators, processors, and a sink
- Object groups for operators and processors
- General Process Flow
- Resource shared assets
- Inter-Arrival Source
- Create Object
- Acquire Resource
- Create Task Sequence
- Load and Unload task activities
- Finish Task Sequence
- Release Resource
- Wait for Event
- Token labels for boxes, processors, and operators
- Linking Process Flow logic with 3D objects
- Waiting for processor completion before releasing a resource
- Standard operator transportation logic

This stage provides the baseline task logic that is later extended into coordinated multi-operator tasks.

**Suggested model filename:** `2.1_Create_Standard_Loading_Tasks.fsm`

---

### 2.2 — Create Coordinated Loading Tasks

This model extends the standard loading system so that heavy boxes require two operators to work together.

Boxes are assigned a weight. Standard boxes continue through the normal transportation logic, while heavy boxes are visually changed, moved to a separate queue, and handled using coordinated task logic.

**Concepts practiced**
- Assigning labels to simulation objects
- Uniform statistical distribution for box weight
- Conditional Decide logic
- Standard vs. heavy item routing
- Change Visual activities
- Moving objects between queues
- Parallel Process Flow tracks
- Main and assisting operators
- Split coordination activity
- Synchronize coordination activities
- Coordinated task sequences
- Separate task sequences for multiple operators
- Connector rankings
- Shared resource acquisition
- Coordinated loading and transportation
- Coordinated arrival at the destination
- Resource release after synchronized work
- Multi-operator task logic

The coordinated logic uses a **Split** activity to create separate task-control tokens for the main and assisting operators. Multiple **Synchronize** activities are then used to make the operators wait for each other at important points in the task, including arrival at the heavy-box queue, loading completion, arrival at the processor, and final release.

**Suggested model filename:** `2.2_Create_Coordinated_Loading_Tasks.fsm`

## Recommended Folder Structure

```text
03_FlexSim_Coordinated_Tasks_Guided_Models/
├── README.md
├── requirements.txt
├── models/
│   ├── 2.1_Create_Standard_Loading_Tasks.fsm
│   └── 2.2_Create_Coordinated_Loading_Tasks.fsm
└── images/
    ├── 2.1_Standard_Loading_Tasks.png
    └── 2.2_Coordinated_Loading_Tasks.png
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 2.1 first to observe standard transportation-task behavior.
5. Run Model 2.2 and compare how heavy boxes are routed into coordinated task logic.
6. Observe both the 3D model and Process Flow while the simulation runs.
7. Pay attention to the Split and Synchronize activities in Model 2.2 to see how two operators are coordinated.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim 3D modeling
- Process Flow
- Task executers and operators
- Resource groups
- Resource acquisition and release
- Task sequences
- Token labels
- Conditional routing
- Statistical input logic
- Object visualization changes
- Multi-operator transportation
- Coordinated task logic
- Split and Synchronize activities
- Parallel task flows
- Event-based process control
- Resource coordination

## Learning Progression

```text
Standard Loading Tasks
        ↓
Resource + Task Sequence Logic
        ↓
Heavy-Box Identification
        ↓
Parallel Operator Task Flows
        ↓
Split + Synchronize Coordination
        ↓
Coordinated Two-Operator Transport
```

The sequence shows how a standard single-operator transportation task can be extended into a coordinated task that requires multiple operators to complete the same job together.

## Attribution

The modeling exercises and tutorial sequence in this folder follow the official **FlexSim Tutorial 2 — Coordinated Tasks**. The `.fsm` files are my implementations created while completing those guided exercises.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_tasklogic_tutorial2coordinatedtasks_coordinatedtasksoverview_html
