# FlexSim Task Sequences — Guided Models

The tutorial focuses on creating task sequences in FlexSim Process Flow and linking them to 3D models. It begins with a basic loading and unloading task sequence shared by two operators, then extends that logic with custom cleaning tasks, shared resources, and dynamic Process Flow references.

## Official Tutorial

FlexSim — Tutorial 2: Task Sequences:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial2tasksequences_tasksequencesoverview_html

## Tutorial Sequence

### 2.1 — Build a Basic Task Sequence

This model introduces a basic task sequence in Process Flow for two operators working with two processors.

A reusable sub flow controls loading and unloading tasks. The same sub flow is used by both operators through separate Process Flow instances, while token labels provide dynamic references to the current flow item, destination, operator, and related 3D objects.

**Concepts practiced**
- Process Flow task sequences
- Sub flows
- Process Flow instances
- Per-instance Process Flow logic
- Start and Finish sub flow activities
- Load and Unload task activities
- Linking Process Flow to 3D objects
- `Use Task Sequence Sub Flow`
- Dynamic token labels
- `item` label
- `toObject` label
- `fromObject` label
- Dynamic 3D object references
- `current` instance-object reference
- Operator-specific task execution
- Reusable task-sequence logic
- Viewing Process Flow instances during a simulation run

This stage establishes a reusable task-sequence structure that can control multiple task executers through separate Process Flow instances.

---

### 2.2 — Customize the Task Sequence

This model extends the basic transportation sequence by adding custom work after each transported item.

After completing the normal load and unload tasks, the operator travels to a supply closet, acquires cleaning supplies, returns to the processor, cleans it, returns the supplies, and then completes the sub flow. Custom Code activities temporarily close and reopen the processor input while cleaning is performed.

**Concepts practiced**
- Custom task sequences
- Extending an existing sub flow
- Custom Code activities
- Closing and opening processor input ports
- `closeinput` and `openinput`
- Dynamic references using `token.fromObject`
- Travel task activities
- Shared resources
- Acquire Resource
- Release Resource
- Global shared resources
- Cleaning-supply resource logic
- Task Sequence Delay
- Operator travel to intermediate locations
- Processor cleaning logic
- Resource contention between Process Flow instances
- Combining transportation and service tasks
- Testing custom task-sequence behavior

This stage demonstrates how Process Flow can extend standard transportation logic with additional task-executer behavior and shared-resource requirements.

## Recommended Folder Structure

```text
07_FlexSim_Task_Sequences_Guided_Models/
├── README.md
├── requirements.txt
├── 2.1_Build_a_Basic_Task_Sequence.fsm
└── 2.2_Customize_the_Task_Sequence.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 2.1 first to observe the basic loading and unloading task sequence used by both operators.
5. Open the Process Flow instances during the simulation to see how each operator runs its own instance of the same sub flow.
6. Run Model 2.2 to observe the additional cleaning tasks added after the transportation sequence.
7. Watch how the shared cleaning-supplies resource affects the two operator instances.
8. Compare the basic transportation logic with the customized task sequence.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim Process Flow
- Task sequences
- Sub flows
- Process Flow instances
- Reusable process logic
- Dynamic token labels
- Dynamic 3D object references
- Task executers and operators
- Load and unload activities
- Travel activities
- Shared resources
- Resource acquisition and release
- Custom Code activities
- Processor control logic
- Intermediate operator tasks
- Instance-specific execution
- Linking Process Flow with 3D models

## Learning Progression

```text
Basic Task Sequence
        ↓
Reusable Sub Flow
        ↓
Dynamic Token Labels
        ↓
Process Flow Instances
        ↓
Custom Task Activities
        ↓
Shared Cleaning Resource
        ↓
Processor Cleaning Logic
        ↓
Extended Operator Task Sequence
```

The sequence moves from a basic reusable transportation sub flow to a customized task sequence with shared resources, intermediate travel, processor control, and additional operator work.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial2tasksequences_tasksequencesoverview_html
