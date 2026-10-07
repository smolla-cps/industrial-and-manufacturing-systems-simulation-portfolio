# FlexSim Automatic Guided Vehicles (AGVs) — Guided Models

The tutorial focuses on both basic and advanced techniques for building AGV transportation systems in FlexSim. It progresses from standard 3D AGV logic to Process Flow control, multi-floor elevator transport, and custom AGV loading and unloading settings.

## Official Tutorial

FlexSim — Tutorial 4: Automatic Guided Vehicles (AGVs):

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_tasklogic_tutorial4agvs_agvoverview_html

## Tutorial Sequence

### 4.1 — AGVs Using Standard 3D Logic

This model introduces the basic structure of an AGV transportation network using standard 3D logic.

The model uses AGV paths, control points, fixed resources, and task executers to move flow items between processing and drop-off locations. A second AGV and dispatcher are then added to demonstrate multi-AGV task assignment and basic congestion behavior.

**Concepts practiced**
- AGV straight paths
- Joining AGV paths
- Path direction and closed-loop networks
- AGV control points
- Traveler AGV connections
- Location connections
- Queue, Processor, Sink, and TaskExecuter objects
- Standard 3D transportation logic
- Port and center-port connections
- DeliverySchedule Process Flow
- Schedule Source
- Create Object
- Use Transport logic
- Multiple AGVs
- Dispatcher-based AGV assignment
- Basic AGV deadlock behavior

This stage establishes the basic AGV network, transportation logic, and multi-AGV control structure before introducing the AGV Process Flow template.

---

### 4.2 — AGVs Using Process Flow

This model replaces much of the standard AGV control logic with FlexSim's Advanced AGV Process Flow template.

The system introduces an automatically managed AGV work list, Next Work Point loops, pickup areas, drop-off areas, park points, and control-point sensitivity settings.

**Concepts practiced**
- Advanced AGV Process Flow template
- Attaching AGVs to Process Flow instances
- `AGVWork` global list
- Next Work Point loops
- Pickup areas
- Pickup control points
- Drop-off areas
- Drop-off control points
- Global item lists
- `ItemsReadyForDelivery`
- Push to Item List
- Pull from Item List
- Many-to-many item routing
- Multiple AGVs in Process Flow
- AGV park points
- Battery charging behavior
- Two-way park paths
- Control-point deallocation
- Control-point sensitivity
- Reducing AGV waiting and deadlock

This stage shifts the AGV system from standard task assignment to Process Flow-based AGV control and adds more scalable routing and parking behavior.

---

### 4.3 — Using Elevators With AGVs

This model extends the AGV system to multiple floors and introduces elevator-based AGV transportation.

Different flow-item types are created and routed using `LoadType` labels. Upper-floor destination logic is added, followed by elevator redirect points, elevator entrance points, floor-height labels, and a second elevator controlled through a dispatcher.

**Concepts practiced**
- Custom flow items
- Medical supplies, clean laundry, dirty laundry, and waste
- Delivery schedules
- `LoadType` labels
- Alternating delivery arrivals
- Multiple-floor AGV layouts
- Upper-floor Next Work Point loops
- Global-list routing by item type
- List queries
- Two-way inter-floor AGV paths
- AGV Elevator Process Flow template
- Elevator objects
- Elevator redirect control points
- Elevator floor control points
- `floorZ` labels
- Multi-floor AGV transport
- Multiple elevators
- Elevator dispatcher
- Dynamic elevator assignment

This stage demonstrates how AGVs can move between multiple floor networks while routing different loads to different destinations.

---

### 4.4 — Custom AGV Settings

This model adds more detailed operating logic by creating custom schedules for dirty laundry and waste and by assigning different loading and unloading times to each flow-item type.

A global table is used to store the load and unload times, and the AGVs reference that table according to each item's `LoadType` label.

**Concepts practiced**
- Additional delivery schedules
- Recurring Process Flow logic
- Destination labels
- Exponential collection-time distributions
- Dirty-laundry and waste generation
- Global item-list routing
- LoadType-based filtering
- Loading-dock destination logic
- Global tables
- `ItemLoadTypes` table
- Custom AGV load times
- Custom AGV unload times
- Global table lookup
- FlexScript table references
- Item-specific AGV handling times

This stage adds item-dependent operating times and demonstrates how global tables can be used to parameterize AGV behavior.

## Recommended Folder Structure

```text
05_FlexSim_AGV_Guided_Models/
├── README.md
├── requirements.txt
├── 4.1_AGVs_Using_Standard_3D_Logic.fsm
├── 4.2_AGVs_Using_Process_Flow.fsm
├── 4.3_Using_Elevators_With_AGVs.fsm
└── 4.4_Custom_AGV_Settings.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 4.1 first to understand the basic AGV network, control points, and standard transportation logic.
5. Run Model 4.2 to observe how the Advanced AGV Process Flow template manages AGV work, pickup areas, drop-off areas, park points, and control-point behavior.
6. Run Model 4.3 to study multi-floor AGV movement and elevator logic.
7. Run Model 4.4 to observe how different flow-item types receive different loading and unloading times through global-table lookup.
8. Compare the progression from standard 3D AGV logic to more scalable Process Flow-based control.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim AGV modeling
- AGV path-network design
- Control-point logic
- Task executers
- Dispatcher logic
- Process Flow
- AGV Process Flow templates
- Global lists
- Pickup and drop-off routing
- Park-point logic
- Multi-AGV coordination
- Congestion and deadlock behavior
- Multi-floor AGV systems
- Elevator integration
- LoadType-based routing
- Global tables
- FlexScript expressions
- Custom loading and unloading times
- Parameterized AGV behavior

## Learning Progression

```text
Standard AGV Network
        ↓
Control Points + Transportation Logic
        ↓
Multiple AGVs + Dispatcher
        ↓
AGV Process Flow Template
        ↓
Pickup, Drop-Off, and Park Points
        ↓
Multi-Floor AGV Routing
        ↓
Elevator-Based AGV Transport
        ↓
Custom Load and Unload Settings
```

The sequence moves from a basic AGV network to a more configurable system with Process Flow control, multiple AGVs, elevator transport, global-list routing, and item-specific operating parameters.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_tasklogic_tutorial4agvs_agvoverview_html
