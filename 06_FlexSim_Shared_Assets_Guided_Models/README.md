# FlexSim Shared Assets — Guided Models

The tutorial focuses on the three main Process Flow shared assets in FlexSim: lists, resources, and zones. It progresses from building operator transportation logic with lists and resources, to using a resource's internal list for conditional task assignment, and finally to using a zone for statistical data collection.

## Official Tutorial

FlexSim — Tutorial 1: Using Shared Assets:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial1usingsharedassets_usingsharedassetsoverview_html

## Tutorial Sequence

### 1.1 — Use a List and a Resource

This model introduces shared assets by building a transportation task sequence for two operators.

A global item list tracks flow items waiting for transport, while a resource shared asset represents the available operators. Process Flow tokens use labels to connect transportation logic to flow items, operators, and destinations in the 3D model.

**Concepts practiced**
- Process Flow shared assets
- Lists
- Resources
- Global item lists
- `ItemsToTransport` list
- Operator groups
- Model parameters
- Parameter-controlled operator quantity
- Schedule Source
- Pull from List
- Create Tokens
- Independent tokens
- Acquire Resource
- Release Resource
- Create Task Sequence
- Load and Unload task activities
- Travel tasks
- Finish Task Sequence
- Back orders
- Token labels
- Flow-item references
- Operator references
- Destination labels
- Linking Process Flow shared assets to 3D objects

This stage establishes the basic relationship between lists, resources, labels, and task sequences in Process Flow.

---

### 1.2 — Make a Resource Act Like a List

This model extends the transportation system by using the resource shared asset's internal list to track operator travel and trigger water-break tasks.

The resource tracks each operator's total travel distance and distance traveled since the last water break. Operators who have traveled more than 100 meters are selected through a query and temporarily assigned to a water-break task sequence.

**Concepts practiced**
- Resource internal lists
- Resource list fields
- `lastDrinkTotalTravel`
- `totalTravel`
- TaskExecuter statistics
- `getvarnum()` expressions
- Conditional resource queries
- `WHERE` queries
- Distance-based operator selection
- Water-break task sequences
- Acquire Resource with query logic
- Create Task Sequence
- Travel to Object
- Task Sequence Delay
- Assign Labels
- Updating operator labels
- Releasing resources after alternate tasks
- Interrupting normal transportation work with custom logic

This stage demonstrates how a resource shared asset can store and query data in a way similar to a list.

---

### 1.3 — Add a Zone to Collect Data

This model introduces the third Process Flow shared asset: the zone.

Each flow item receives a randomly generated `Price` label. Tokens representing those flow items enter a zone while the items are in the system, allowing the zone to calculate the current total price of all active items.

**Concepts practiced**
- Zone shared assets
- Statistical data collection
- Flow-item labels
- `Price` label
- Uniform distributions
- Zone subsets
- Subset calculations
- `TotalPrice`
- `MyItem.Price`
- Event-Triggered Source
- Enter Zone
- Wait for Event
- Exit Zone
- Event-based token creation
- Label Assignment
- Label Matching
- Linking tokens to flow items
- Zone status and statistics
- Tracking current system-wide values
- Using zones for statistics and constraints

This stage shows how zones can collect statistics from tokens currently inside a defined section of Process Flow.

## Recommended Folder Structure

```text
06_FlexSim_Shared_Assets_Guided_Models/
├── README.md
├── requirements.txt
├── 1.1_Use_a_List_and_a_Resource.fsm
├── 1.2_Make_a_Resource_Act_Like_a_List.fsm
└── 1.3_Add_a_Zone_to_Collect_Data.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 1.1 first to observe how lists and resources are used to assign transportation tasks to operators.
5. Run Model 1.2 to observe how the resource's internal list tracks operator travel distance and triggers water-break tasks.
6. Run Model 1.3 to observe how a zone collects statistics for flow items currently active in the system.
7. Compare how lists, resources, and zones serve different roles within Process Flow.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim Process Flow
- Shared assets
- Lists
- Resources
- Zones
- Global lists
- Resource internal lists
- Process Flow variables and labels
- Task sequences
- Operator task assignment
- Conditional resource selection
- Back-order logic
- Event-triggered logic
- Label assignment and matching
- Statistical data collection
- Zone subset calculations
- FlexScript expressions
- Parameterized operator groups
- Linking Process Flow logic with 3D objects

## Learning Progression

```text
Lists + Resources
        ↓
Operator Transportation Task Sequences
        ↓
Labels + 3D Object References
        ↓
Resource Internal Lists
        ↓
Conditional Operator Selection
        ↓
Custom Water-Break Tasks
        ↓
Zones
        ↓
Statistical Data Collection
```

The sequence moves from basic shared-asset task coordination to conditional resource logic and zone-based statistical analysis.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial1usingsharedassets_usingsharedassetsoverview_html
