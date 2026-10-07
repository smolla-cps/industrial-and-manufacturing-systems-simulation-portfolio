# FlexSim Custom Objects — Guided Models

The tutorial focuses on using FlexSim Process Flow to create custom logic for 3D objects. It begins with a custom fixed resource that receives, processes, and releases items in batches, then extends the model with a custom task executer that changes its behavior based on whether work is available.

## Official Tutorial

FlexSim — Tutorial 5: Creating Logic for Custom Objects:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial5creatinglogic_customobjectsoverview_html

## Tutorial Sequence

### 5.1 — Create a Custom Fixed Resource

This model creates custom logic for a `BasicFR` fixed resource using an Object Process Flow.

The custom fixed resource receives three flow items, processes them as a batch, and releases them to the next downstream resource. The Process Flow explicitly controls receiving and releasing because the `BasicFR` object does not contain built-in item-flow logic.

**Concepts practiced**
- `BasicFR` custom fixed resources
- Object Process Flow
- Process Flow instances
- `current` instance-object reference
- Schedule Source
- Wait for Event
- Delay activities
- On Entry and On Exit events
- Receive Item logic
- Release Item logic
- Label Matching/Assignment
- `Item1`, `Item2`, and `Item3` labels
- Dynamic flow-item references
- Batch-processing logic
- Custom processing delays
- Change Visual activities
- Custom flow-item positioning
- FlexScript expressions such as `current.size.z`
- Event-handling behavior
- Breathe activities
- Preventing simultaneous item release
- Custom fixed-resource troubleshooting

This stage demonstrates how Process Flow can supply the receive, process, and release logic for a blank fixed-resource object.

---

### 5.2 — Create a Custom Task Executer

This model adds custom behavior to an operator through a Task Executer Process Flow.

After completing a task, the operator checks whether another task is available. If no task is available, the operator returns to the queue and waits for up to 10 seconds. If work still does not appear, the operator travels to a break room and remains there until another task becomes available.

**Concepts practiced**
- Task Executer Process Flow
- Operator-specific Process Flow logic
- Process Flow instances
- `current` instance-object reference
- Schedule Source
- Wait for Event
- `On Resource Available`
- `On Start Task`
- Label Matching/Assignment
- `nextTask` label
- Conditional Decide
- Conditional routing
- Travel activities
- Returning to a default work location
- Max Wait Timer
- Time-based idle logic
- Break-room routing
- Waiting for new work
- Looping Process Flow logic
- Dynamic task-executer behavior
- Scalable operator logic

This stage demonstrates how Process Flow can customize task-executer behavior without changing the operator's basic 3D object type.

## Recommended Folder Structure

```text
10_FlexSim_Custom_Objects_Guided_Models/
├── README.md
├── requirements.txt
├── 5.1_Create_a_Custom_Fixed_Resource.fsm
└── 5.2_Create_a_Custom_Task_Executer.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 5.1 first to observe how the `BasicFR` receives, processes, and releases items through Process Flow logic.
5. Review the Wait for Event, Receive Item, Release Item, Change Visual, and Breathe activities while the model is running.
6. Run Model 5.2 to observe how the operator changes behavior based on task availability.
7. Watch the operator return to the queue, wait for work, and move to the break room after the timeout.
8. Compare how Object Process Flow and Task Executer Process Flow are used to create different kinds of custom object behavior.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim Process Flow
- Custom fixed-resource logic
- Custom task-executer logic
- Object Process Flow
- Task Executer Process Flow
- Process Flow instances
- Event-driven modeling
- Wait for Event
- Receive and Release Item logic
- Label Matching/Assignment
- Conditional routing
- Max Wait Timer
- Travel logic
- Breathe activities
- Custom visual positioning
- Batch-processing logic
- Operator idle-state behavior
- Dynamic object references
- FlexScript expressions
- Simulation troubleshooting

## Learning Progression

```text
BasicFR Custom Fixed Resource
        ↓
Receive + Process + Release Logic
        ↓
Event-Based Item Handling
        ↓
Custom Item Positioning
        ↓
Breathe Activities
        ↓
Custom Task Executer
        ↓
Task-Availability Decision Logic
        ↓
Timed Waiting
        ↓
Break-Room Routing
```

The sequence moves from creating custom fixed-resource behavior to creating custom task-executer behavior using Process Flow.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial5creatinglogic_customobjectsoverview_html
