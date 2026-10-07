# FlexSim Process Flow Instances — Guided Models

The tutorial focuses on Process Flow instances and scalable simulation logic in FlexSim. It begins with a sticker-machine workstation and its roll-refill logic, compares copy-and-paste cloning with Process Flow instances, and then demonstrates how one object Process Flow can control multiple sticker-machine systems and update all attached instances simultaneously.

## Official Tutorial

FlexSim — Tutorial 4: Process Flow Instances:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial4instances_instancesoverview_html

## Tutorial Sequence

### 4.1 — Build the 3D Model and Process Flow

This model establishes the sticker-machine system that is used throughout the tutorial.

The system includes a production line, a sticker machine, sticker-roll storage, and a roll operator. Process Flow logic tracks two sticker rolls, reduces the remaining sticker quantity as products are processed, and creates a task sequence for the operator when a new roll is required.

**Concepts practiced**
- 3D production-line modeling
- Source, Queue, Processor, Sink, and Operator objects
- Sticker-machine and roll-storage logic
- General Process Flow
- Schedule Source
- Shared lists
- `Sticker Rolls in Use` list
- `rollQuantity` labels
- Push to List
- Pull from List
- Create Task Sequence
- Travel task activities
- Finish Task Sequence
- Event-Triggered Source
- Custom Code
- Stop and resume machine logic
- Max Wait Timer
- SELECT queries
- Connector rankings
- Operator-based roll replacement
- Interaction between roll-refill and roll-usage logic

This stage establishes the base model and Process Flow logic that will later be cloned and converted into instance-based logic.

---

### 4.2 — Create Clones Using Copy and Paste

This model expands the system by duplicating the sticker-machine objects and their Process Flow logic using copy and paste.

The copied system requires several Process Flow references and object links to be updated manually so that the second sticker machine uses its own lists, events, destinations, and Custom Code references.

**Concepts practiced**
- Copying multiple 3D objects
- Copying Process Flow logic
- Plane objects as 3D containers
- Container shapes in Process Flow
- Organizing cloned systems visually
- Duplicating lists and activities
- Updating copied list references
- Updating task-sequence destinations
- Updating Event-Triggered Source references
- Updating Custom Code object references
- Testing cloned systems
- Comparing duplicated Process Flow logic
- Limitations of copy-and-paste scaling

This stage demonstrates why direct duplication can become difficult to maintain when a simulation contains many similar systems.

---

### 4.3 — Create Clones Using Process Flow Instances

This model replaces repeated Process Flow copies with an object Process Flow that can run separate instances for multiple sticker machines.

A common Process Flow acts as the template. Each attached sticker machine runs its own instance of the logic while local assets and the `current` keyword allow activities to reference the correct machine dynamically.

**Concepts practiced**
- Object Process Flow
- Process Flow instances
- Attached objects
- Fixed-resource Process Flow logic
- Global versus local assets
- Local lists
- `current` instance-object reference
- Dynamic object references
- Reusable Process Flow templates
- Instance-specific events
- Instance-specific task destinations
- Viewing individual Process Flow instances
- Viewing instance-specific list entries
- Scaling from one instance to multiple instances
- Creating multiple sticker-machine systems
- Comparing instance-based logic with copy-and-paste logic

The model is expanded to eight sticker-machine systems to demonstrate how Process Flow instances simplify repeated model logic.

---

### 4.4 — Change Instances Simultaneously

This model extends the shared object Process Flow and demonstrates how modifications to the main logic are inherited by all attached instances.

Sticker rolls are represented as 3D flow items. The rolls are transported by the RollOperator, installed on sticker machines, and visually shrink as their sticker quantity decreases.

**Concepts practiced**
- Updating all Process Flow instances through shared logic
- Sticker-roll flow items
- Additional Source objects
- Global lists
- `Rolls in Storage` list
- Local and global list interaction
- Create Object
- Destroy Object
- Move Object
- Load task activities
- Task Sequence Delay
- Dynamic lists
- `rollNumber` labels
- `rollObject` labels
- `rollQuantity` labels
- `rollSize` labels
- Change Visual activities
- Dynamic location, rotation, and size changes
- `getlabel()` logic
- Pushed and pulled token references
- Animated roll installation and depletion
- Shared RollOperator logic
- Simultaneous updates across attached instances
- Bottleneck observation in a multi-machine system

This stage demonstrates the main maintenance advantage of Process Flow instances: one change to the object Process Flow can update the behavior of all attached sticker-machine systems.

## Recommended Folder Structure

```text
09_FlexSim_Process_Flow_Instances_Guided_Models/
├── README.md
├── requirements.txt
├── 4.1_Build_the_3D_Model_and_Process_Flow.fsm
├── 4.2_Create_Clones_Using_Copy_and_Paste.fsm
├── 4.3_Create_Clones_Using_Process_Flow_Instances.fsm
└── 4.4_Change_Instances_Simultaneously.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 4.1 first to understand the sticker-machine, roll-refill, and roll-usage logic.
5. Run Model 4.2 to observe the manual changes required when cloning both 3D objects and Process Flow logic with copy and paste.
6. Run Model 4.3 to compare the same cloning problem using an object Process Flow and Process Flow instances.
7. View individual instances and their local list entries while the simulation is running.
8. Run Model 4.4 to observe how changes made to the shared Process Flow logic affect all attached sticker-machine instances.
9. Compare the maintainability and scalability of copy-and-paste logic with instance-based logic.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim 3D modeling
- FlexSim Process Flow
- Process Flow instances
- Object Process Flow
- Fixed-resource Process Flow
- Global and local assets
- Dynamic object references
- `current` instance-object logic
- Shared and local lists
- Task sequences
- Operator task assignment
- Event-triggered logic
- Custom Code
- List queries
- Clone management
- Scalable simulation architecture
- Dynamic visual changes
- Object creation and destruction
- Multi-machine systems
- Simulation-model maintainability

## Learning Progression

```text
Base Sticker-Machine System
        ↓
Roll Refill + Roll Usage Logic
        ↓
Copy-and-Paste Cloning
        ↓
Manual Reference Updates
        ↓
Object Process Flow
        ↓
Process Flow Instances
        ↓
Local Assets + current
        ↓
Eight Sticker-Machine Instances
        ↓
Shared Logic Modification
        ↓
Simultaneous Instance Updates
```

The sequence moves from a single sticker-machine system to a scalable instance-based model in which one Process Flow definition controls multiple attached systems.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial4instances_instancesoverview_html
