# FlexSim Conveyors — Guided Models

The tutorial focuses on conveyor-system modeling in FlexSim. It covers sorting, merging, slug building, gap control, Process Flow integration, and power-and-free conveyor behavior.

## Official Tutorial

FlexSim — Tutorial 1: Conveyors:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_additionaltools_tutorial1conveyors_conveyorsoverview_html

## Tutorial Sequence

### 1.1 — Sorting Systems

This model introduces three conveyor-sorting methods: conditional sorting, destination-based sorting, and sorting to downstream fixed resources.

The model first diverts a percentage of flow items using a true/false condition. It then assigns a `ProductType` label and routes items to conveyor lanes based on port ranking. The final section sends items to downstream fixed resources using decision points and exit transfers.

**Concepts practiced**
- Straight conveyors
- Conveyor transfers
- Decision Points
- Conditional sorting
- `On Arrival` triggers
- `Send Item` logic
- Bernoulli distribution
- Product-type labels
- `ProductType`
- Destination-based routing
- Output-port rankings
- `current.outObjects[]`
- Dynamic object color
- `Color.byNumber()`
- Fixed-resource sorting
- Exit transfers
- Product-type-based routing
- Conveyor route finding

This stage establishes the main conveyor routing and sorting methods used in later models.

---

### 1.2 — Merging, Area Restriction, and Slug Building

This model extends the sorting system with merging conveyors and controlled release logic.

The model first combines several infeed lanes into one merging conveyor. Area restriction is then used to control access to the merge. The diverting lanes are later converted into slug-building conveyors, and a Merge Controller coordinates slug releases using a round-robin strategy.

**Concepts practiced**
- Merging conveyors
- Multiple infeed lanes
- Merging-lane layout
- Area restriction
- Acquire Area
- Release Area
- Decision Points
- Restricted-area control
- Slug-building conveyors
- Slug Builder settings
- Item-count release criteria
- Slug accumulation
- Merge Controller
- Round-robin release strategy
- Lane Clear Table
- Coordinated slug release
- Merge-jam prevention
- Throughput-oriented conveyor control

This stage demonstrates how to manage competing conveyor lanes and coordinate grouped item releases into a shared downstream conveyor.

---

### 1.3 — Adding and Removing Gaps

This model focuses on controlling spacing between flow items and improving conveyor throughput.

The model removes unwanted gaps by changing conveyor geometry and transfer behavior, improves slug-release timing using additional decision points, adds fixed and variable gaps with area restriction, and finally uses a Gap-Optimizing Merge Controller Process Flow template.

**Concepts practiced**
- Conveyor gapping
- Inline transfers
- Side transfers
- Join Conveyors tool
- Conveyor angle adjustment
- Transfer types
- Custom transfer properties
- `SlugTransfer`
- Maximum transfer angle
- Additional Decision Points
- Merge Controller sensors
- Round Robin If Available
- Lane Clear Table
- Photo eyes
- Fixed item gaps
- Area restriction for gapping
- Acquire Area and Release Area
- Variable flow-item sizes
- Variable gap sizes
- Time to Convey Item X Size
- Gap-Optimizing Merge Controller template
- Object Process Flow
- Process Flow instances
- Process Flow variables
- Target merge gap
- Throughput improvement

This stage demonstrates several methods for reducing unnecessary gaps, creating controlled spacing, and improving merge performance.

---

### 1.4 — Power and Free Systems

This model converts the conveyor system into a simplified power-and-free conveyor system.

The conveyor network is raised above the floor, connected to a common motor, and configured for fixed-interval movement. Decision points simulate painting operations, while large flow items are translated below the conveyor to resemble suspended loads.

**Concepts practiced**
- Power-and-free conveyor systems
- Overhead conveyor modeling
- Fixed Interval Movement
- Conveyor motors
- Shared motor connections
- Conveyor elevation changes
- Decision Points
- Stop Item and Delay
- On Continue triggers
- Item-color changes
- Product-type-based painting
- Conveyor speed settings
- Conveyor width changes
- Conveyor visualization
- Dog interval movement
- Large flow items
- Cylinder flow items
- Translate Item
- Suspended-load positioning
- `item.size.z`
- Slower heavy-load transport
- Power-and-free system simplification

This stage demonstrates how standard conveyors can be configured to represent the operating behavior of a power-and-free material-handling system.

## Recommended Folder Structure

```text
11_FlexSim_Conveyors_Guided_Models/
├── README.md
├── requirements.txt
├── 1.1_Sorting_Systems.fsm
├── 1.2_Merging_Area_Restriction_and_Slug_Building.fsm
├── 1.3_Adding_and_Removing_Gaps.fsm
└── 1.4_Power_and_Free_Systems.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 1.1 to study conditional, destination-based, and fixed-resource sorting.
5. Run Model 1.2 to observe merging, area restriction, slug building, and Merge Controller behavior.
6. Run Model 1.3 to compare different methods for reducing and creating gaps and to observe the Process Flow merge-control template.
7. Run Model 1.4 to observe fixed-interval movement, motor-driven conveyors, delayed painting operations, and suspended loads.
8. Compare how routing, merging, gapping, and conveyor behavior change across the tutorial sequence.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim conveyor modeling
- Conveyor routing
- Decision Points
- Conditional sorting
- Destination-based sorting
- Fixed-resource sorting
- Product-type labels
- Merging systems
- Area restriction
- Slug building
- Merge Controllers
- Lane Clear Tables
- Conveyor gapping
- Photo-eye logic
- Transfer configuration
- Process Flow integration
- Gap optimization
- Power-and-free conveyor modeling
- Fixed-interval movement
- Motor-driven conveyor systems
- Material-handling simulation

## Learning Progression

```text
Conveyor Sorting
        ↓
Decision-Point Routing
        ↓
Merging Multiple Lanes
        ↓
Area Restriction
        ↓
Slug Building
        ↓
Merge Controller
        ↓
Gap Removal + Gap Creation
        ↓
Process Flow Merge Optimization
        ↓
Power-and-Free Conveyor System
```

The sequence moves from basic conveyor sorting to coordinated merging, gapping control, Process Flow integration, and power-and-free conveyor behavior.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_additionaltools_tutorial1conveyors_conveyorsoverview_html
