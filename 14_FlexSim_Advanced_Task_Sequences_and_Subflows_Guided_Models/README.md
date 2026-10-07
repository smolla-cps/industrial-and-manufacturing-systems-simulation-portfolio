# FlexSim Advanced Task Sequences and Subflows — Guided Models

The tutorial sequence focuses on advanced Process Flow modeling with reusable subflows and task sequences. It progresses from a basic main Process Flow calling a subflow to object-based task sequences, coordinated multi-operator logic, sequential processor transportation, and batch transportation.

## Tutorial Sequence

### 1 — Subflow Introduction with Main Process Flow

This model introduces a reusable subflow called from a main Process Flow.

The main logic creates tokens and sends work into the subflow. The subflow uses Start and Finish activities together with resource acquisition, delays, and release logic before returning control to the main flow.

**Concepts practiced**
- Main Process Flow
- Subflows
- Run Sub Flow
- Start and Finish activities
- Inter-Arrival Source
- Delay activities
- Resource shared assets
- Acquire Resource
- Release Resource
- Token movement between a parent flow and a subflow
- Reusable Process Flow logic
- Sink activities

This stage establishes the basic structure for separating reusable logic from the main Process Flow.

---

### 2 — Object Subflow Introduction with a Task Sequence

This model introduces task-sequence activities inside an object-linked subflow.

The 3D system contains a source, queue, processors, sink, and operator. The subflow creates a task sequence for the operator and defines the travel, loading, unloading, and completion steps required to transport a flow item.

**Concepts practiced**
- Object-linked subflows
- Task sequences
- Create Task Sequence
- Travel tasks
- Load tasks
- Unload tasks
- Finish Task Sequence
- Operator task execution
- Source, Queue, Processor, and Sink objects
- Linking 3D object logic with Process Flow
- Reusable transportation logic

This stage connects subflow design with task-executer behavior in the 3D model.

---

### 3 — Object Subflow with Extended Task Sequence

This model extends the object-subflow task sequence with an additional travel step and a delay activity.

The added logic demonstrates how task sequences can be expanded with intermediate work while keeping the transportation process inside the same reusable subflow.

**Concepts practiced**
- Extended task sequences
- Additional Travel activities
- Delay activities
- Intermediate operator work
- Create Task Sequence
- Load and Unload tasks
- Finish Task Sequence
- Reusable object-subflow logic
- Task-sequence customization

This stage shows how additional task logic can be inserted into an existing object subflow.

---

### 4 — Object Subflow Task Sequence Refinement

This model continues the object-subflow task-sequence structure and refines the same operator transportation workflow.

The model retains the core Start, Create Task Sequence, Travel, Load, Delay, Unload, Finish Task Sequence, and Finish activities while developing the task-sequence configuration further.

**Concepts practiced**
- Object subflows
- Task-sequence refinement
- Start and Finish activities
- Create Task Sequence
- Multiple Travel activities
- Load and Unload tasks
- Delay activities
- Operator transportation logic
- Reusable task-sequence structure

This stage provides another iteration of the task-sequence model before coordinated multi-operator logic is introduced.

---

### 5 — Object Subflow Task Sequence Refinement 2

This model continues the same object-subflow and task-sequence framework as a later refinement of the transportation logic.

The model uses the same core task-sequence activity set while providing another configuration for practicing reusable operator-control logic.

**Concepts practiced**
- Object-subflow modeling
- Task-sequence configuration
- Create Task Sequence
- Travel activities
- Load and Unload tasks
- Delay activities
- Finish Task Sequence
- Operator-controlled transportation
- Reusable Process Flow design

This stage completes the single-task-sequence progression before synchronization is added.

---

### 6 — Object Subflow with Synchronized Task Sequences

This model introduces coordinated task sequences for multiple operators.

The subflow contains separate primary-operator and helper-operator flows. A Split activity creates parallel control paths, and Synchronize activities coordinate the operators at important stages such as arrival at the queue, completion of loading, arrival at the destination, and completion of unloading.

**Concepts practiced**
- Multi-operator task sequences
- Primary and helper operator flows
- Split activities
- Parallel token flows
- Multiple Create Task Sequence activities
- Synchronize activities
- Coordinated travel
- Coordinated loading
- Coordinated unloading
- Multiple operators
- Multiple queues
- Task-sequence synchronization
- Finish Task Sequence

This stage introduces explicit synchronization between task executers working on the same transportation process.

---

### 7 — Synchronized Task Sequences with Resource Logic

This model extends the synchronized multi-operator system with resource acquisition and release logic.

The coordinated task flow includes a task-executer team resource, operator grouping, decision logic, labels, and additional task-sequence activities while preserving the Split and Synchronize structure.

**Concepts practiced**
- Coordinated task-executer teams
- Resource shared assets
- Acquire Resource
- Release Resource
- Operator groups
- Assign Labels
- Decide activities
- Multiple task sequences
- Split activities
- Synchronize activities
- Parallel operator flows
- Resource-controlled coordination
- Multi-operator transportation logic

This stage combines synchronized task sequences with resource-management logic.

---

### 8 — Task Sequence for Series Processors

This model applies a task sequence to a series-processing system.

A token is created when an item arrives at the queue. The operator transports the same item through several processors in sequence. Each processor is represented as a Process Flow resource, and the task sequence acquires the processor, unloads the item, waits for processing to complete, loads the same item again, releases the processor, and continues to the next station.

**Concepts practiced**
- Event-Triggered Source
- Queue-arrival events
- Series processors
- Processor resources
- Acquire Resource
- Release Resource
- Create Task Sequence
- Repeated Travel tasks
- Repeated Load and Unload tasks
- Wait for Event
- Waiting for process completion
- Transporting the same item through multiple processors
- Sequential resource usage
- Final transport to a sink

This stage demonstrates a complete task sequence that coordinates transportation and processing across a multi-stage system.

---

### 9 — Simple 3D Model with a Subflow

This model uses a main Process Flow and reusable subflow logic to control a multi-phase 3D processing system.

Products are assigned `ProductID` and `ResourceID` labels and routed through combinations of inspection, painting, curing, cutting, and polishing resources. Run Sub Flow activities reuse the processing logic across different product routes.

**Concepts practiced**
- Main Process Flow and subflows
- Run Sub Flow
- Product labels
- `ProductID`
- `ResourceID`
- Assign Labels
- Decide activities
- Conditional routing
- Resource acquisition and release
- Inspection resources
- Painting resources
- Curing resources
- Cutting resources
- Polishing resources
- Processing delays
- Multi-phase processing
- Reusable processing logic
- Linking Process Flow to a 3D system

This stage applies subflows to a larger processing model with multiple products and resource paths.

---

### 10 — Operator Carrying a Batch with Subflow and Task Sequence

This model combines batch logic, a subflow, resource control, and a task sequence for operator transportation.

Tokens are grouped with a Batch activity, an operator resource is acquired, and a task sequence controls travel, loading, unloading, and completion of the batch movement.

**Concepts practiced**
- Batch activities
- Batch size and batch quantity
- Subflows
- Run Sub Flow
- Operator resources
- Acquire Resource
- Release Resource
- Create Task Sequence
- Travel tasks
- Load and Unload tasks
- Finish Task Sequence
- Event-triggered logic
- Grouped item transportation
- Combining batching with task sequences

This stage combines several Process Flow tools into one operator-based batch transportation model.

## Recommended Folder Structure

```text
14_FlexSim_Advanced_Task_Sequences_and_Subflows_Guided_Models/
├── README.md
├── requirements.txt
├── 1_Subflow_Introduction_with_Main_Process_Flow.fsm
├── 2_Object_Subflow_Introduction_Task_Sequence.fsm
├── 3_Object_Subflow_Introduction_Task_Sequence_2.fsm
├── 4_Object_Subflow_Introduction_Task_Sequence_3.fsm
├── 5_Object_Subflow_Introduction_Task_Sequence_4.fsm
├── 6_Object_Subflow_with_Synchronize_Task_Sequence.fsm
├── 7_Object_Subflow_with_Synchronize_Task_Sequence_2.fsm
├── 8_Task_Sequence_Model_for_Series_Processors.fsm
├── 9_Simple_3D_with_a_Subflow.fsm
└── 10_Operator_Carrying_Batch_Subflow_Batch_Task_Sequence.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Begin with Models 1–5 to study the progression from a basic subflow to reusable object-based task sequences.
5. Use Models 6–7 to study parallel operator flows, Split activities, synchronization, and resource-controlled coordination.
6. Run Model 8 to follow one item through a sequence of processor resources using a complete transportation task sequence.
7. Run Model 9 to study reusable subflow logic in a multi-phase processing system.
8. Run Model 10 to observe how batching, subflows, resources, and task sequences can be combined in one transportation model.
9. Keep the Process Flow view open while each model runs to follow token movement and task-sequence execution.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim Process Flow
- Main Process Flow design
- Subflows
- Object subflows
- Run Sub Flow
- Task sequences
- Create Task Sequence
- Travel, Load, and Unload tasks
- Finish Task Sequence
- Operator task execution
- Resource acquisition and release
- Parallel token flows
- Split activities
- Synchronize activities
- Multi-operator coordination
- Event-triggered logic
- Wait for Event
- Series-processing logic
- Conditional routing
- Token labels
- Batch activities
- Multi-item transportation
- Reusable simulation logic

## Learning Progression

```text
Main Process Flow
        ↓
Basic Subflow
        ↓
Object Subflow
        ↓
Task Sequence
        ↓
Extended Task Sequence
        ↓
Parallel Operator Flows
        ↓
Split + Synchronize
        ↓
Resource-Controlled Coordination
        ↓
Series-Processor Task Sequence
        ↓
Multi-Phase Subflow Model
        ↓
Batch + Subflow + Task Sequence
```

The sequence moves from basic reusable Process Flow logic to coordinated task sequences that combine multiple operators, resources, processing stages, and batched transportation.
