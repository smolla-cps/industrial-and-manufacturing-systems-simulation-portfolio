# FlexSim Process Flow Zones — Guided Models

The model sequence focuses on zone-based logic and related material-handling behavior in FlexSim. It begins with conveyor restricted-area control and rack handling, then moves into Process Flow Zone activities for customized statistics, subsets, partitions, calculations, constraints, and conveyor-zone restrictions.

## Tutorial Sequence

### 1 — Restricted Area in Conveyor

This model demonstrates restricted-area control on a conveyor system.

Decision-point logic acquires a restricted area before an item enters it. If the area is already occupied, the item is stopped and placed into a request queue. When the area is released, the next waiting item can resume.

**Concepts practiced**
- Conveyor systems
- Decision Points
- Restricted-area logic
- Acquire Restricted Area
- Release Restricted Area
- Request queues
- Stopping and resuming conveyor items
- Area ownership
- Area claimers
- Conveyor flow control
- Mutual-exclusion behavior

This stage introduces controlled access to a shared conveyor section.

---

### 2 — Rack Introduction

This model introduces rack and storage-system behavior together with conveyors.

The model contains a source, conveyors, transfers, and a rack storage object. It provides a basic example of moving flow items from conveyor transport into rack storage.

**Concepts practiced**
- Rack objects
- Storage systems
- Storage slots
- Storage levels and bays
- Conveyor-to-rack flow
- Entry transfers
- Exit transfers
- Source objects
- Slot assignment
- Storage capacity
- Rack visualization

This stage establishes the basic rack structure used in later storage examples.

---

### 3 — Item Sorting into the Rack

This model extends the rack example by assigning items to storage locations according to item and slot types.

The rack uses a slot-assignment condition that matches `slot.SlotType` with `item.Type`, allowing different item types to be directed to compatible storage slots.

**Concepts practiced**
- Item sorting
- Item `Type`
- Slot `SlotType`
- Slot-assignment conditions
- Type-based storage matching
- Rack storage
- Conveyor routing
- Curved and straight conveyors
- Entry transfers
- Storage-system logic

This stage demonstrates rule-based item placement inside a rack.

---

### 4 — Dwell Time and Rack Output Port

This model extends the rack system with item dwell-time behavior and rack output routing.

The system includes multiple conveyor segments, rack storage, an additional entry transfer, and a downstream sink. It demonstrates how stored items can remain in the rack before leaving through the rack's output side and continuing through the conveyor system.

**Concepts practiced**
- Rack dwell time
- Minimum stay time
- Rack output behavior
- Output routing
- Storage slots
- Item-type and slot-type matching
- Entry and exit transfers
- Conveyor-to-rack integration
- Rack-to-conveyor flow
- Downstream sink routing

This stage adds time-based storage and outbound rack flow.

---

### 5 — Getting Familiar with the Conveyor Library

This model provides broader practice with FlexSim's conveyor and storage libraries.

The model includes straight and curved conveyors, entry and exit transfers, a rack, a source, a sink, and several conveyor routing elements.

**Concepts practiced**
- Straight conveyors
- Curved conveyors
- Conveyor systems
- Entry transfers
- Exit transfers
- Decision Points
- Conveyor routing
- Rack integration
- Source and sink objects
- Item-type routing
- Storage-system objects
- Conveyor-library components

This stage builds familiarity with the conveyor objects used in the later zone examples.

---

### 6 — Zone Partitions, Subsets, and Calculations

This model introduces the Process Flow Zone activity for customized statistics collection.

Tokens enter and exit a zone while carrying labels such as `PartitionID` and `Weight`. The zone defines subsets and calculations that measure content for selected partitions and weight ranges.

**Concepts practiced**
- Process Flow Zone
- Enter Zone
- Exit Zone
- Zone partitions
- `PartitionID`
- Token `Weight`
- Zone subsets
- Subset criteria
- Zone calculations
- `COUNT(*)`
- `SUM(Weight)`
- Partition-based statistics
- SQL-style zone queries
- Content over time
- Customized statistics collection

Example calculations include:
- `PartitionID = 1 OR PartitionID = 3`
- `Weight >= 35`
- `(Weight >= 15 AND Weight <= 35) AND PartitionID = 2`

This stage introduces partitioned and filtered statistics inside a Process Flow Zone.

---

### 7 — Zone Subset Constraints

This model extends the previous zone example with constraint logic.

The zone retains partition and subset calculations while adding constraint structures that can limit or control token behavior according to zone conditions.

**Concepts practiced**
- Process Flow Zone
- Zone subsets
- Zone constraints
- Partition constraints
- Subset criteria
- Content calculations
- Weight-based conditions
- Partition-based conditions
- Queue-order enforcement
- Maximum-content logic
- Custom constraint checks
- Unmatched statistics
- Zone-based flow control

This stage demonstrates how zones can be used for both measurement and control.

---

### 8 — Zone Factory Model

This model combines several Zone features in one Process Flow example.

Tokens receive `Type`, `Weight`, and `DollarValue` labels. The zone uses subset criteria and calculations to measure selected token groups, total weight, total dollar value, expensive-item value, and type-based content.

**Concepts practiced**
- Process Flow Zone
- Enter Zone and Exit Zone
- Assign Labels
- `Type`
- `Weight`
- `DollarValue`
- Zone subsets
- Zone calculations
- Zone constraints
- Content calculations
- Total-weight calculations
- Total-dollar-value calculations
- Type-based filtering
- Weight-based filtering
- Dollar-value filtering
- Delay activities
- Decide activities
- Customized zone statistics

Example zone logic includes:
- `Weight >= 35`
- `Type = 1 OR Type = 3`
- `DollarValue >= 800`
- `SUM(Weight)`
- `SUM(DollarValue)`

This stage combines multiple Zone features in one larger exercise.

---

### 9 — Conveyor Zone Restrictions

This model combines conveyor events with a Process Flow Zone.

An event-triggered Process Flow listens for items at multiple conveyor locations. Item labels such as `Weight` and `Type` are assigned, items enter the zone, and the zone tracks aggregate weight while controlling item movement through the conveyor area.

**Concepts practiced**
- Conveyor systems
- Process Flow Zone
- Event-Triggered Source
- Decision Points
- Conveyor-item events
- Assign Labels
- Item `Weight`
- Item `Type`
- Enter Zone
- Exit Zone
- Zone calculations
- Total conveyor-zone weight
- Stop and resume conveyor items
- Wait for Event
- Zone constraints
- Conveyor-area restrictions
- Zone-based conveyor control

This stage connects Process Flow Zone logic directly to conveyor movement and restriction behavior.

## Recommended Folder Structure

```text
16_FlexSim_Process_Flow_Zones_Guided_Models/
├── README.md
├── requirements.txt
├── 1_Restricted_Area_in_Conveyor.fsm
├── 2_Rack_Introduction.fsm
├── 3_Item_Sorting_into_the_Rack.fsm
├── 4_Dwell_Time_and_Rack_Output_Port.fsm
├── 5_Getting_Familiar_with_Conveyor_Library.fsm
├── 6_Zone_Partitions_Subsets_and_Calculations.fsm
├── 7_Zone_Subset_Constraints.fsm
├── 8_Zone_Factory_Model.fsm
└── 9_Conveyor_Zone_Restrictions.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Begin with Models 1–5 to review conveyor restrictions, rack storage, item sorting, dwell-time behavior, and conveyor-library components.
5. Run Models 6–7 to study Process Flow Zone partitions, subsets, calculations, and constraints.
6. Run Model 8 to see several Zone features combined in one Process Flow example.
7. Run Model 9 to study how a Zone can interact directly with conveyor events and item movement.
8. Keep the Process Flow and relevant statistics views open while the Zone models run to observe token entry, exit, subset membership, and calculated values.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim conveyor modeling
- Rack and storage-system modeling
- Restricted-area control
- Item sorting
- Storage-slot matching
- Dwell-time logic
- Process Flow
- Process Flow Zones
- Enter Zone and Exit Zone
- Zone partitions
- Zone subsets
- Zone calculations
- Zone constraints
- SQL-style zone queries
- Token labels
- Customized statistics
- Aggregate weight calculations
- Event-triggered logic
- Conveyor-zone integration
- Material-flow control

## Learning Progression

```text
Conveyor Restricted Area
        ↓
Rack and Storage Basics
        ↓
Type-Based Rack Sorting
        ↓
Dwell Time + Rack Output
        ↓
Conveyor Library Practice
        ↓
Process Flow Zone
        ↓
Partitions + Subsets + Calculations
        ↓
Zone Constraints
        ↓
Combined Zone Features
        ↓
Conveyor + Zone Restrictions
```

The sequence moves from conveyor and storage fundamentals to Process Flow Zone logic for customized statistics and zone-based material-flow control.
