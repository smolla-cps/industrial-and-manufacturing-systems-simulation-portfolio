# FlexSim Task Logic — Guided Models


The tutorial compares several ways to create and manage tasks for task executers in FlexSim. The sequence starts with standard 3D object logic, then moves to Process Flow task sequences, list-based task logic, and global-list-based task assignment.


## Official Tutorial

Autodesk FlexSim 2027 — Task Logic Tools Tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_tasklogic_tutorial1tasklogictools_tasklogictoolsoverview_html

## Tutorial Sequence

### 1.1 — Tasks Using Standard 3D Logic

This model introduces transportation and operator task logic using the standard logic available directly on FlexSim 3D objects.

**Concepts practiced**
- Source, Queue, Processor, Sink, Operator, and Dispatcher objects
- Standard 3D transportation logic
- Port and center-port connections
- Assigning transport tasks to operators
- Dispatcher-based task assignment
- Multiple operators
- Multiple processors
- Operator-assisted processor setup
- FIFO task behavior
- Task priorities
- Task preemption

This stage is useful for understanding the strengths and limitations of standard 3D task logic before moving to Process Flow.

**Suggested model filename:** `1.1_Tasks_Using_Standard_3D_Logic.fsm`

---

### 1.2 — Tasks Using Process Flow

This model recreates task logic using Process Flow and task-sequence activities.

**Concepts practiced**
- General Process Flow
- Event-Triggered Source
- Create Task Sequence
- Load and Unload task activities
- Dispatcher assignment
- Token labels
- Linking 3D-model events with Process Flow
- Task Sequence execution
- Adding custom intermediate tasks
- Travel tasks
- Task Sequence Delay
- Building more visible and customizable task logic

An intermediate scanning task is added to demonstrate how Process Flow can represent custom task steps more easily than standard 3D logic.

**Suggested model filename:** `1.2_Tasks_Using_Process_Flow.fsm`

---

### 1.3 — Tasks Using Lists

This model extends the Process Flow approach by using lists to manage transportation requests and task assignment.

**Concepts practiced**
- Local lists in Process Flow
- Push to List and Pull from List
- Multiple token flows
- Processor groups
- Event-triggered task requests
- Task sequences
- Token labels
- List fields
- Sorting and querying list entries
- Rush-order labels
- Task prioritization
- Priority-based item selection
- Task sequencing and timing behavior

This stage demonstrates how lists can be used to sort, filter, and prioritize tasks using custom criteria.

**Suggested model filename:** `1.3_Tasks_Using_Lists.fsm`

---

### 1.4 — Tasks Using Global Lists

This model uses a global task-sequence list so that task sequences can be created in Process Flow and pulled directly by task executers in the 3D model.

**Concepts practiced**
- Global Task Sequence Lists
- Creating task sequences before execution
- Pushing task sequences to a global list
- Operators pulling task sequences when available
- Linking Process Flow lists to Toolbox global lists
- On Resource Available triggers
- Task Sequence priorities
- Rush-order priority logic
- Standard logic and Process Flow integration
- Bottleneck troubleshooting
- Wait Until Complete behavior
- Multiple processors
- Resource acquisition and release
- Priority and preemption interaction

This stage demonstrates a more flexible task-assignment structure in which Process Flow builds task sequences and operators obtain available work from a shared global list.

**Suggested model filename:** `1.4_Tasks_Using_Global_Lists.fsm`

## Recommended Folder Structure

```text
02_FlexSim_Task_Logic_Guided_Models/
├── README.md
├── requirements.txt
├── models/
├── 1.1_Tasks_Using_Standard_3D_Logic.fsm
├── 1.2_Tasks_Using_Process_Flow.fsm
├── 1.3_Tasks_Using_Lists.fsm
└── 1.4_Tasks_Using_Global_Lists.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim 2027.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run the simulation and observe both the 3D model and Process Flow logic where applicable.
5. Compare how task assignment changes across standard logic, Process Flow, local lists, and global lists.
6. Review operator behavior, task priorities, list entries, and bottlenecks while the models run.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim 3D modeling
- Task executers and operators
- Dispatcher logic
- Transportation-task modeling
- Process Flow
- Task sequences
- Local and global lists
- Token labels
- Priority and preemption
- Task assignment and dispatching
- Resource coordination
- Troubleshooting task-flow bottlenecks
- Simulation logic comparison

## Learning Progression

```text
Standard 3D Task Logic
        ↓
Process Flow Task Sequences
        ↓
List-Based Task Logic
        ↓
Global List + Task Sequence Logic
```

The sequence documents a progression from simple built-in task logic toward more flexible and customizable task-assignment methods.

