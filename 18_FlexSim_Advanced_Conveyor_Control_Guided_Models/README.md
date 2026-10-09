# FlexSim Advanced Conveyor Control — Guided Models

The training sequence focuses on advanced conveyor control using FlexSim Process Flow. It uses a larger material-handling model to combine lists, event listening, object groups, scheduled sources, reversible conveyors, synchronization, subflows, arrays, photo-eye logic, slug building, and Merge Controller behavior.

## Training Sequence

### Phase 1 — Processing-Lane Assignment

This model introduces a conveyor system in which arriving flow items must be assigned to one of several side processing lanes.

Each processing lane can contain only one flow item at a time. If no lane is available, the item waits until a lane becomes available. Decision Points signal item requests, while a Process Flow list coordinates available lanes and waiting flow items.

**Concepts practiced**
- Conveyor routing
- Decision Points
- Processing lanes
- Process Flow lists
- Push to List
- Pull from List
- Back orders
- Scheduled Source
- Object groups
- Event listening
- Custom Code
- Conveyor send logic
- Stop and resume behavior
- Lane-availability management
- Destination selection with lists
- API access to conveyor objects

This phase establishes list-based coordination between conveyor items and processing lanes.

---

### Phase 2 — Buffer Lanes and Reversible Conveyors

This model extends the processing-lane system by adding buffer lanes.

Each buffer lane can hold one waiting flow item and is paired with a corresponding processing lane. After processing, completed items return to the main conveyor and continue toward the sink.

**Concepts practiced**
- Buffer lanes
- Reversible conveyors
- Negative conveyor speed
- Conveyor direction changes
- List queries
- List partitions
- Puller-based queries
- List Max Wait Timer
- Breathe activity
- Event sequencing
- Release Token
- Labels for list priority
- Re-routing processed items
- Buffer-to-processing-lane matching
- Stop and resume conveyor items

This phase demonstrates how reversible conveyor logic, queries, partitions, and event timing can be combined with the Phase 1 list-based routing structure.

---

### Phase 3 — Synchronized Processing Lanes

This model adds synchronization across the processing lanes.

All four processing stations must finish before their flow items are released back to the main conveyor. Event listening detects completion, and a Synchronize activity holds the associated tokens until every required process is finished.

**Concepts practiced**
- Synchronize activity
- Multi-lane synchronization
- Event listening
- Processing-completion events
- Holding tokens until all processes finish
- Partition IDs in synchronization
- Custom Code
- Stop and resume items
- Connector-name routing
- Coordinated conveyor release

This phase introduces coordinated release behavior across multiple processing lanes.

---

### Phase 4 — Order-Based Collection Lanes

This model changes the arrival pattern from simple item arrivals to scheduled orders.

Flow items receive order numbers and are routed to one of three collection lanes after processing. Each lane can collect items for up to two order numbers at a time. If the collection lanes are full, items recirculate on a looped conveyor.

**Concepts practiced**
- Date/Time Source
- Scheduled order arrivals
- Excel Importer
- Table-based arrival data
- Order IDs
- Color palettes
- Subflows
- Parent-child token relationships
- Arrays
- Create Tokens
- List queries
- `SELECT ... WHERE ... ORDER BY`
- `WHERE ... IN`
- Order-to-lane assignment
- Collection-lane capacity
- Recirculation
- Stop and resume tokens
- Photo-eye monitoring
- List entries that remain on the list
- Capacity-management logic

This phase combines scheduled data, order labels, reusable subflows, arrays, and list-based lane assignment.

---

### Phase 4 — Alternate Capacity

This model is an alternate Phase 4 configuration focused on collection-lane capacity handling.

It provides another approach to controlling whether a collection lane can accept additional flow items while keeping the same order-based conveyor structure.

**Concepts practiced**
- Collection-lane capacity
- Alternate capacity logic
- Order-based routing
- Recirculation
- Lane availability
- Process Flow control
- Conveyor decision logic

This version is useful for comparing different ways to represent lane capacity within the same Phase 4 system.

---

### Phase 4 — Zone-Based Presorting

This Phase 4 variation uses a zone-based presorting strategy so that each collection lane receives one order before receiving a second order.

The model changes the lane-assignment strategy while preserving the broader Phase 4 order-routing and capacity structure.

**Concepts practiced**
- Zone-based control
- Presorting
- Collection-lane balancing
- Order assignment
- Lane eligibility
- Process Flow routing
- Order distribution across lanes
- Capacity-aware lane selection

This variation demonstrates an alternative assignment strategy intended to distribute orders across the available collection lanes before adding another order to the same lane.

---

### Phase 5 — Slug Building and Merge Control

This model extends the collection-lane system with slug-building conveyors and a controlled merge.

Each collection lane builds a slug of five flow items. A Merge Controller coordinates the release order of the slugs so that the lanes perform a sawtooth merge.

**Concepts practiced**
- Slug-building conveyors
- Slug Builder settings
- Item-count release criteria
- Fill-percent criteria
- Maximum slug count
- Time-elapsed release criteria
- Slug release speed
- Merge Controller
- Merge-lane release strategies
- Sawtooth merging
- Coordinated lane release
- Collection-lane discharge control

This phase completes the sequence by adding grouped release and merge-control behavior to the advanced conveyor model.

## Recommended Folder Structure

```text
18_FlexSim_Advanced_Conveyor_Control_Guided_Models/
├── README.md
├── requirements.txt
├── Part_1_Phase_1.fsm
├── Part_1_Phase_2.fsm
├── Part_1_Phase_3.fsm
├── Part_1_Phase_4.fsm
├── Part_1_Phase_4_Alternate_Capacity.fsm
├── Part_1_Phase_4_Zone_Presort.fsm
└── Part_1_Phase_5.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in phase order.
3. Reset each model before a new simulation run.
4. Start with Phase 1 to understand list-based processing-lane assignment.
5. Continue to Phase 2 to study buffer lanes, reversible conveyor logic, list partitions, and timing control.
6. Run Phase 3 to observe synchronization across multiple processing lanes.
7. Run the main Phase 4 model before the two Phase 4 alternatives.
8. Compare the standard Phase 4 model with the alternate-capacity and zone-presort versions.
9. Run Phase 5 to observe slug building and Merge Controller behavior.
10. Keep the 3D model, Process Flow, and relevant list views open while the simulation runs.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim conveyor modeling
- Advanced Process Flow
- Decision Points
- Process Flow lists
- List queries and partitions
- Back-order logic
- Event listening
- Scheduled and Date/Time sources
- Object groups
- Custom Code
- Reversible conveyors
- Breathe activity
- Release Token
- Synchronize activity
- Subflows
- Arrays
- Excel-based schedule import
- Order-based routing
- Recirculation
- Photo-eye logic
- Capacity management
- Zone-based presorting
- Slug building
- Merge Controller
- Sawtooth merging
- Material-handling control strategies

## Learning Progression

```text
Processing-Lane Assignment
        ↓
Lists + Event Listening
        ↓
Buffer Lanes + Reversible Conveyors
        ↓
Queries + Partitions + Breathe
        ↓
Multi-Lane Synchronization
        ↓
Scheduled Orders + Excel Data
        ↓
Subflows + Arrays + SELECT Queries
        ↓
Collection-Lane Capacity
        ↓
Alternate Capacity / Zone Presorting
        ↓
Slug Building
        ↓
Merge Controller + Sawtooth Merge
```

The sequence moves from list-based conveyor routing to coordinated, data-driven conveyor control with synchronization, order assignment, capacity logic, and controlled merging.
