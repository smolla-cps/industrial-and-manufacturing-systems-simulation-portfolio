# FlexSim Conditional Tasks — Guided Models

This folder contains FlexSim models that I built while following the official **FlexSim Tutorial 3 — Conditional Tasks**.

The tutorial focuses on building transportation tasks that respond to changing conditions during a simulation run. It introduces sub flows, arrays, nested sub flows, conditional decision logic, and FlexScript expressions for dynamically selecting destinations based on queue capacity.

## Official Tutorial

FlexSim — Tutorial 3: Conditional Tasks:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_tasklogic_tutorial3conditionaltasks_conditionaltasksoverview_html

## Tutorial Sequence

### 3.1 — Use Sub Flows and Arrays

This model introduces sub flows and array-based labels to manage transportation of multiple flow items with one operator.

The operator pulls several items from a list, stores references to those items in an array, loads them through a loading sub flow, and unloads them through a separate unloading sub flow.

**Concepts practiced**
- 3D modeling with Source, Queue, Processor, Sink, and Operator objects
- Object groups
- General Process Flow
- Event-Triggered Source
- Push to List and Pull from List
- Resource shared assets
- Operator acquisition
- Process Flow variables
- Array-based token labels
- `GroupOfItems` array
- Array indexing
- Array length
- `creationRank`
- Run Sub Flow activities
- Start and Finish sub flow activities
- Parent and child tokens
- Loading sub flow
- Unloading sub flow
- Transporting multiple items in one operator cycle
- Token labels for operator, item, queue, and destination references
- FlexScript expressions for arrays and group size

This stage builds the foundation for handling groups of items and reusable task logic through sub flows.

**Suggested model filename:** `3.1_Use_Sub_Flows_and_Arrays.fsm`

---

### 3.2 — Add Conditional Tasks

This model extends the previous system by adding multiple unloading destinations with different queue capacities.

The operator evaluates the available space at each destination and changes the unloading destination dynamically during the model run. If one queue is full, the logic checks the next destination. If all destination queues are full, the operator waits until space becomes available.

**Concepts practiced**
- Conditional task logic
- Multiple destination queues
- Queue maximum-capacity constraints
- Destination groups
- Using object groups as arrays
- Group indexing
- Nested sub flows
- Conditional Decide activities
- Dynamic destination selection
- Connector rankings
- Destination-number labels
- Incrementing labels
- Wait for Event
- Monitoring queue exit events
- Checking current queue content
- Checking maximum queue capacity
- Array `.length`
- Array `.pop()`
- Dynamic FlexScript expressions
- Repeating sub flows based on model conditions
- Looping through multiple possible destinations
- Capacity-based unloading logic

The unloading logic uses nested sub flows and Decide activities to test each destination dynamically. The model compares current queue content with maximum capacity, attempts another destination when necessary, and waits for a queue-space event when all destinations are full.

**Suggested model filename:** `3.2_Add_Conditional_Tasks.fsm`

## Recommended Folder Structure

```text
04_FlexSim_Conditional_Tasks_Guided_Models/
├── README.md
├── requirements.txt
├── 3.1_Use_Sub_Flows_and_Arrays.fsm
└── 3.2_Add_Conditional_Tasks.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 3.1 first to observe how arrays and sub flows are used to transport multiple flow items.
5. Run Model 3.2 and observe how the unloading destination changes according to queue capacity.
6. Watch the Process Flow while the simulation runs to see how tokens move through the conditional logic.
7. Pay attention to the Decide, Run Sub Flow, and Wait for Event activities in Model 3.2.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim 3D modeling
- Process Flow
- Task executers and operators
- Lists and resource shared assets
- Sub flows
- Nested sub flows
- Parent and child tokens
- Arrays and array indexing
- Object groups as arrays
- Process Flow variables
- Conditional routing
- Dynamic task logic
- Queue-capacity constraints
- Event-based logic
- FlexScript expressions
- Dynamic destination selection
- Multi-item transportation logic

## Learning Progression

```text
List-Based Item Transport
        ↓
Array-Based Item Grouping
        ↓
Loading and Unloading Sub Flows
        ↓
Multiple Destination Queues
        ↓
Nested Sub Flows
        ↓
Conditional Decide Logic
        ↓
Capacity-Based Dynamic Destination Selection
```

The sequence shows how a basic multi-item transportation process can be extended into a dynamic task system that responds to changing queue capacities during the simulation.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_tasklogic_tutorial3conditionaltasks_conditionaltasksoverview_html
