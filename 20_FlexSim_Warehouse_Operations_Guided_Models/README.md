# FlexSim Warehouse Operations — Guided Models

The training sequence focuses on warehouse simulation using FlexSim. It develops one warehouse model across multiple chapters, beginning with data management and storage layout, then adding initial inventory, inbound product handling, order generation, picking rules, randomized orders, and model-execution improvements.

## Training Sequence

### Chapter 1 — Simple Data Management and Model Layout

This model establishes the warehouse layout and supporting data structure.

External warehouse data is imported into Global Tables, a drawing is used as the model background, rack objects are positioned according to the layout, and Object Property Tables are used to manage object properties efficiently.

**Concepts practiced**
- Global Tables
- Excel Import/Export interface
- External warehouse data
- Model backgrounds
- DWG/DXF layout references
- Rack objects
- Warehouse layout construction
- Object Property Tables
- Protected object properties
- Bulk object-property editing

This chapter establishes the physical warehouse model and the data structure used by the later chapters.

---

### Chapter 2.1 — Address Schemes

This model introduces Storage System address schemes for warehouse racks.

Address schemes provide structured storage addresses across rack objects so that inventory data can be mapped to specific warehouse locations.

**Concepts practiced**
- Storage System
- Rack address schemes
- Zone, aisle, bay, level, and slot addressing
- Storage-location identification
- Rack mapping
- Data-driven storage locations

---

### Chapter 2.2 — Slot Labels and Color Palette

This model adds custom slot labels and visual SKU identification.

Slot labels store warehouse-specific information, while a Color Palette uses SKU data to visually distinguish storage locations.

**Concepts practiced**
- Slot Labels
- SKU labels
- Storage System Properties
- Color Palettes
- Slot painting
- Data-driven visualization
- Storage-location attributes

---

### Chapter 2.3 — Initial Inventory

This model creates the initial warehouse inventory from data.

A Process Flow uses a startup token, subflow logic, and Find Slot activities to create and place items into rack locations according to the warehouse address scheme.

**Concepts practiced**
- Initial inventory generation
- Scheduled Source
- Startup Process Flow
- Subflows
- Find Slot
- Multiple slot queries
- Flow-item creation
- Address-based inventory placement
- Storage System API
- `Storage.Slot`
- `.as()` class casting
- Slot-to-storage-object references

This chapter completes the initial warehouse state before inbound and outbound operations begin.

---

### Chapter 3.1 — Inbound Product

This model introduces scheduled inbound inventory.

A Date/Time Source creates product arrivals, and Find Slot logic searches first for a slot containing the same SKU and then for an empty slot when a matching location is unavailable.

**Concepts practiced**
- Date/Time Source
- Scheduled inbound arrivals
- Inbound inventory
- Multiple Find Slot queries
- Same-SKU storage preference
- Empty-slot fallback
- `slot.slotItems`
- `slot.hasSpace()`
- Storage-location allocation

---

### Chapter 3.2 — Work List and Milestone Lists

This model adds list-based work management for inbound material.

Items that have an assigned storage slot are pushed to a work list. Additional lists act as process milestones so waiting work and work in progress can be monitored separately.

**Concepts practiced**
- Global Lists
- Work lists
- Push to List
- Pull from List
- Work availability
- Milestone lists
- Work-in-progress tracking
- Waiting-time tracking
- Process-status monitoring
- List-based task coordination

---

### Chapter 3.3 — Instance Flow

This model creates an instanced Process Flow for warehouse pickers.

Each picker receives its own Process Flow instance, pulls available work, creates a task sequence, travels to the item, loads it, moves to the assigned storage location, and unloads it.

**Concepts practiced**
- Instanced Process Flow
- Picker behavior
- `current` object reference
- Task sequences
- Travel
- Load
- Unload
- Create Task Sequence
- Finish Task Sequence
- Work-list integration
- Reusable task-executer logic

---

### Chapter 3.4 — A* Navigation

This model adds A* navigation for warehouse task executers.

The A* system allows pickers to calculate point-to-point paths through the warehouse while avoiding rack structures and other barriers.

**Concepts practiced**
- A* Navigation
- A* grid
- Grid spacing
- Barriers
- Dividers
- Preferred Paths
- Bridges
- Mandatory Paths
- Travel thresholds
- Dynamic pathfinding
- Traveler conflict avoidance
- Warehouse aisle navigation

This chapter completes the inbound storage workflow with task-executer navigation.

---

### Chapter 4.1 — Table Query

This model introduces historical order generation using `Table.query()`.

Order-history data is reorganized into an aggregated order table so that each order is represented by one row while preserving the source rows belonging to that order.

**Concepts practiced**
- `Table.query()`
- SQL-style table queries
- `SELECT`
- `AS`
- `FROM`
- `GROUP BY`
- `ARRAY_AGG()`
- `ROW_NUMBER`
- Aggregated order data
- `.cloneTo()`
- Historical order processing

---

### Chapter 4.2 — Table Reader

This model creates a Process Flow table reader.

A single reader token moves through the aggregated order table and creates order tokens one row at a time, providing a lean alternative to creating a large scheduled source.

**Concepts practiced**
- Table-reader logic
- Reader tokens
- Order tokens
- Looping Process Flow
- Table-row iteration
- Create Tokens
- Data-driven token creation
- Historical order scheduling

---

### Chapter 4.3 — Find Slot and More Slot Labels

This model expands Storage System labeling so that different warehouse areas can be included or excluded from storage and order queries.

**Concepts practiced**
- Additional Slot Labels
- Storage-area classification
- Query inclusion and exclusion
- Inbound rack identification
- Outbound rack identification
- Find Slot
- Find Item
- Storage System filtering

---

### Chapter 4.4 — Complete Order Processing Flow

This model integrates historical order generation with item allocation and picker work.

Order tokens are generated from the aggregated order data, required items are found in the Storage System, and the selected items are pushed to the picker work list.

**Concepts practiced**
- Complete order-processing workflow
- Historical order data
- Order tokens
- SKU-level order structure
- Find Item
- Item allocation
- Outbound item marking
- Work-list integration
- Picker-task generation
- Inbound and outbound job types

---

### Chapter 4.5 — Simple JobType Processing

This model introduces a simple distinction between inbound and outbound work.

Job-type labels allow the picker flow to identify whether a task represents incoming storage work or an outbound order-picking task.

**Concepts practiced**
- `JobType`
- Inbound work
- Outbound work
- Job classification
- Label-based routing
- Shared picker flow
- Work-list queries

This chapter completes a warehouse order-processing flow driven by historical data.

---

### Chapter 5.1 — Picker Flow Structure and New List Fields

This model expands picker logic and adds custom list fields.

The work list includes data that supports more informed job selection, including travel distance over the A* network.

**Concepts practiced**
- Custom List Fields
- Picker flow structure
- A* travel distance
- `distancetotravel()`
- Job prioritization
- Distance-based sorting
- Work-list customization
- Multi-item carrying logic

---

### Chapter 5.2 — LIFO/FIFO SKUs

This model introduces different handling times for FIFO and LIFO SKUs.

A query checks SKU data to determine the required pick method, and different loading-time distributions are applied according to the SKU's FIFO/LIFO classification.

**Concepts practiced**
- FIFO
- LIFO
- SKU handling rules
- `Table.query()`
- Values by Case
- Conditional load times
- Query-driven object behavior
- Abstraction of storage-handling differences

---

### Chapter 5.3 — Picker Roles and Labels

This model assigns different operational roles to warehouse pickers.

Picker labels identify roles such as inbound-only, customer pickup, shipping, and hybrid work. Each role can use a different work-list query.

**Concepts practiced**
- Picker roles
- Operator labels
- Role-based work assignment
- Inbound-only role
- Customer-pickup role
- Shipping role
- Hybrid role
- Instanced picker logic
- Query selection by role

---

### Chapter 5.4 — JOIN Query

This model adds information from multiple data tables using a SQL-style JOIN.

Order history and order-type information are merged into the aggregated order data through a shared Order ID.

**Concepts practiced**
- SQL-style `JOIN`
- Table relationships
- Shared keys
- Order ID matching
- Data merging
- Aggregated order enrichment
- `Table.query()`
- Multi-table data management

---

### Chapter 5.5 — Role Queries and OrderType Field

This model connects picker roles with order-type information.

Process Flow variables and labels are used to assign role-specific list queries, allowing different picker types to select different categories of warehouse work.

**Concepts practiced**
- Process Flow variables
- `getprocessflowvar()`
- Picker-query labels
- Role-specific queries
- `OrderType`
- Dynamic Pull from List logic
- Data-driven work assignment

---

### Chapter 5.6 — Hybridized Inbound

This model combines inbound and outbound work within a more flexible picker-control structure.

The picker flow can evaluate job type, role, capacity, destination, and other information when selecting work.

**Concepts practiced**
- Hybrid picker behavior
- Inbound and outbound integration
- Picker capacity
- Multiple-item handling
- Role-based selection
- Conditional list queries
- Job-type prioritization
- Destination-aware assignment

This chapter develops more realistic warehouse picking rules and worker roles.

---

### Chapter 6 — Random Orders

This model replaces historical order arrivals with randomly generated orders.

Random values determine order arrival times, number of SKUs per order, number of picks, and other order properties while preserving the same downstream picking logic.

**Concepts practiced**
- Random order generation
- Random arrival times
- Random number of SKUs
- Random number of picks
- Empirical distributions
- Activity statistics
- Sampler expressions
- Dynamic labels
- Removing temporary labels
- Future-state modeling
- Modeling without historical order data

This chapter provides an alternative when historical order information is unavailable or when testing future warehouse conditions.

---

### Chapter 7.1 — Model Execution Speed

This model focuses on identifying computationally expensive parts of the warehouse simulation.

The Performance Profiler is used to locate high-cost model logic before performance improvements are applied.

**Concepts practiced**
- Performance Profiler
- Simulation execution speed
- Performance bottlenecks
- Event-hit counts
- Execution-time analysis
- Large-model diagnostics
- Computational efficiency

---

### Chapter 7.2 — Indexed Labels, Cached Queries, and Cached Paths

This model applies several performance-improvement techniques to the warehouse simulation.

Storage System indexed labels, cached list queries, and cached A* paths reduce repeated search and pathfinding work.

**Concepts practiced**
- Indexed Labels
- Cached Queries
- Cached A* paths
- Storage System performance
- List performance
- A* performance
- Query optimization
- Pathfinding optimization
- Model scalability
- Execution-efficiency improvement

This chapter demonstrates how the same warehouse logic can be implemented more efficiently for larger or longer simulation experiments.

## Recommended Folder Structure

```text
20_FlexSim_Warehouse_Operations_Guided_Models/
├── README.md
├── requirements.txt
├── Chapter_1_Simple_Data_and_Layout.fsm
├── Chapter_2_1_Address_Schemes.fsm
├── Chapter_2_2_Slot_Label_and_Color_Palette.fsm
├── Chapter_2_3_Initial_Inventory.fsm
├── Chapter_3_1_Inbound_Product.fsm
├── Chapter_3_2_Work_List_and_Milestone_Lists.fsm
├── Chapter_3_3_Instance_Flow.fsm
├── Chapter_3_4_AStar.fsm
├── Chapter_4_1_Table_Query.fsm
├── Chapter_4_2_Table_Reader.fsm
├── Chapter_4_3_Find_Slot_and_More_Slot_Labels.fsm
├── Chapter_4_4_Complete_Order_Processing_Flow.fsm
├── Chapter_4_5_Simple_JobType_Processing.fsm
├── Chapter_5_1_Picker_Flow_Structure_New_List_Fields.fsm
├── Chapter_5_2_LIFO_FIFO_SKUs.fsm
├── Chapter_5_3_Picker_Roles_Labels.fsm
├── Chapter_5_4_JOIN_Query.fsm
├── Chapter_5_5_Role_Queries_OrderType_Field.fsm
├── Chapter_5_6_Hybridized_Inbound.fsm
├── Chapter_6_Random_Orders.fsm
├── Chapter_7_1_Speed.fsm
└── Chapter_7_2_Speed_Indexed_Labels_Cached_Queries_Cached_Paths.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in chapter order because each chapter extends the warehouse model developed in the previous chapter.
3. Reset each model before a new simulation run.
4. Begin with Chapter 1 to understand the layout and warehouse data structure.
5. Continue through Chapter 2 to study Storage System addressing, slot labels, and initial inventory.
6. Use Chapter 3 to study inbound inventory, picker work lists, task sequences, instance flows, and A* navigation.
7. Use Chapter 4 to study historical-order data, table queries, order creation, Find Item logic, and outbound picking.
8. Use Chapter 5 to compare picker rules, FIFO/LIFO behavior, roles, custom list fields, and SQL-style JOIN logic.
9. Run Chapter 6 to compare randomized order generation with historical-data-driven orders.
10. Run Chapter 7 last to evaluate and improve the execution speed of the completed warehouse model.

## Skills Demonstrated

- Discrete-event simulation
- Warehouse simulation
- FlexSim Storage System
- Rack modeling
- Global Tables
- Excel data integration
- Address schemes
- Slot Labels
- Color Palettes
- Initial inventory
- Find Slot
- Find Item
- Storage System API
- Date/Time Source
- Process Flow
- Subflows
- Global Lists
- Work and milestone lists
- Instanced Process Flow
- Task sequences
- A* Navigation
- Historical order generation
- `Table.query()`
- SQL-style queries
- `GROUP BY`
- `ARRAY_AGG()`
- `JOIN`
- Picker work rules
- FIFO/LIFO handling
- Picker roles
- Process Flow variables
- Randomized orders
- Performance Profiler
- Indexed Labels
- Cached Queries
- Cached Paths
- Warehouse-model optimization

## Learning Progression

```text
Warehouse Layout + External Data
        ↓
Storage Address Schemes
        ↓
Slot Labels + Initial Inventory
        ↓
Inbound Product
        ↓
Work Lists + Picker Instance Flows
        ↓
A* Navigation
        ↓
Historical Order Data
        ↓
Table Queries + Table Reader
        ↓
Find Item + Order Processing
        ↓
Advanced Picker Rules
        ↓
FIFO/LIFO + Picker Roles
        ↓
JOIN Queries + Role-Based Work
        ↓
Randomized Orders
        ↓
Performance Profiling
        ↓
Indexed Labels + Cached Queries + Cached Paths
```

The sequence develops a warehouse model from layout and inventory initialization through inbound and outbound operations, picker-control strategies, order generation, and execution-speed improvements.
