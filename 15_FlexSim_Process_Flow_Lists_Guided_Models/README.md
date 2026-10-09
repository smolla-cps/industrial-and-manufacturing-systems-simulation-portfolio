# FlexSim Process Flow Lists — Guided Models

The model sequence focuses on list-based logic in FlexSim Process Flow. It progresses from global-list queries and sorting to partitioned lists, query-based matching, inventory and order lists, storage assignment, global-table-driven list logic, and a double-list crane model.

## Tutorial Sequence

### 1 — Global List with WHERE and ORDER BY

This model introduces a global item list and demonstrates how list entries can be selected using SQL-style query expressions.

One pull condition selects items with `Type = 1`, while another uses a different condition together with `ORDER BY Type DESC` to control which eligible item is selected first.

**Concepts practiced**
- Global lists
- Item lists
- Push to List
- Pull from List
- List entries
- Back orders
- `WHERE` conditions
- `ORDER BY`
- Type-based filtering
- Descending sort order
- Query-based list selection
- Global list references

This stage establishes the basic use of filtering and sorting when pulling entries from a global list.

---

### 2 — Global List with Multiple Query Conditions

This model extends global-list querying to several item types and more complex conditions.

Different pulls search for Type 1, Type 2, and Type 3 entries. Another query combines entry age with type conditions, allowing older items or selected types to become eligible for pulling.

**Concepts practiced**
- Global item lists
- Multiple Pull from List conditions
- `WHERE Type = 1`
- `WHERE Type = 2`
- `WHERE Type = 3`
- Entry-age conditions
- Compound query expressions
- `OR` conditions
- List back orders
- Type-based list matching
- Query-driven selection rules

This stage demonstrates how a single global list can support several pull rules for different item categories and waiting-time conditions.

---

### 3 — Process Flow List Using Partition ID

This model introduces a Process Flow list that separates list entries and pullers using partition IDs.

Tokens receive `EntryType` and `PullerType` values. Push and Pull from List activities use these values so that entries and pullers can interact through matching list partitions.

**Concepts practiced**
- Process Flow lists
- Partition IDs
- Push to List
- Pull from List
- List partitions
- `EntryType`
- `PullerType`
- Assign Labels
- Inter-Arrival Source
- Delay activities
- Max Wait Timer
- Back orders
- Token-based list values
- Partition-based matching

This stage demonstrates how partition IDs can separate different categories of list entries within one Process Flow list.

---

### 4 — Process Flow List Using a Query

This model performs similar entry-to-puller matching with a list query rather than relying only on partition IDs.

The Pull from List activity uses the condition `WHERE EntryType = puller.PullerType`, allowing the puller's label to determine which list entry is eligible.

**Concepts practiced**
- Process Flow lists
- Query-based matching
- `WHERE EntryType = puller.PullerType`
- Puller references
- Entry labels
- Puller labels
- Push to List
- Pull from List
- Assign Labels
- Back-order behavior
- Dynamic list queries
- Token-to-token matching

This stage compares label-based query matching with partition-based list organization.

---

### 5 — Inventory List Model

This model applies list logic to an inventory-and-order workflow.

Inventory tokens are pushed to an `Inventory` list. Pick tokens then search the list for available inventory, allowing the Process Flow to coordinate inventory availability with customer-pick requests.

**Concepts practiced**
- Inventory lists
- Inventory Flow
- Pick Flow
- Schedule Source
- Push to List
- Pull from List
- Available-inventory search
- Back orders
- Inventory tokens
- Pick tokens
- Pick completion
- Shipping flow
- List-based order fulfillment

This stage applies Process Flow lists to a basic inventory-matching problem.

---

### 6 — Extended Inventory List Model

This model extends the inventory-list workflow with 3D object creation, picking delay, object destruction, and task-sequence activities.

The Process Flow retains the inventory and order-list logic while adding physical item handling and transportation-related behavior.

**Concepts practiced**
- Inventory lists
- Push to List
- Pull from List
- Back-order content
- Create Object
- Destroy Object
- Picking delays
- Create Task Sequence
- Load activities
- Unload activities
- Inventory-object references
- Order fulfillment
- Process Flow statistics
- Back-order tracking over time

This stage connects list-based matching with physical item creation and task execution.

---

### 7 — Extended Inventory and Storage List Model

This model extends the inventory system into a storage environment with rack and slot logic.

The model includes storage objects and item-to-slot assignment behavior. Item and slot types are used to determine storage eligibility, while list logic continues to coordinate inventory and order processing.

**Concepts practiced**
- Process Flow lists
- Inventory matching
- Storage systems
- Pallet racks
- Drive-in racks
- Push-back racks
- Gravity-flow racks
- Floor storage
- Slot assignment
- `ItemType`
- `SlotType`
- Item-to-slot compatibility
- Batch activities
- Move Object
- Create Task Sequence
- Load and Unload activities
- Back-order tracking

This stage adds storage-location logic to the list-based inventory workflow.

---

### 8 — Pallet and Parts List Model

This model uses a Process Flow list to coordinate line-side parts with pallets moving through a conveyor-based process.

The logic stops a pallet, determines the required part or pallet type, pulls matching parts from the list, performs the required movement, and then resumes the pallet.

**Concepts practiced**
- Parts lists
- Pallet process logic
- Event-Triggered Source
- Assign Labels
- `PartType`
- `PalletTokenType`
- Pull from List
- Type-based list selection
- Decide activities
- Custom Code
- Stop and resume conveyor items
- Batch activities
- Move Object
- Back orders
- Pallet-part matching

This stage demonstrates list-based material matching within an event-driven pallet process.

---

### 9 — Pallet and Parts List Model Using a Global Table

This model extends pallet-part matching by using a global table to define pallet configurations.

The pallet type is used to look up configuration data from the `Palltet Configs` global table. The Process Flow then pulls Type 1, Type 2, and Type 3 parts from the line-side parts list according to the required configuration.

**Concepts practiced**
- Process Flow lists
- Global tables
- Global-table lookup
- Pallet configurations
- Pallet types
- Part quantities
- `WHERE Type == 1`
- `WHERE Type == 2`
- `WHERE Type == 3`
- Pull from List
- Event-triggered pallet logic
- Move Object
- Delay activities
- Line-side parts
- Data-driven list logic

This stage demonstrates how external configuration data can control list pulls and material requirements.

---

### 10 — Double-List Crane Model

This model uses two Process Flow lists to coordinate plate selection and destination-queue selection for a crane.

One list stores plates and uses a query that considers type, moves required from the top of a stack, and queue size. A second list stores queues and selects a destination other than the origin queue, prioritizing the least-full eligible queue.

**Concepts practiced**
- Multiple Process Flow lists
- Plate list
- Queue list
- Crane task logic
- Pull from List
- Complex `WHERE` conditions
- Multi-field `ORDER BY`
- Type matching
- Moves-from-top priority
- Queue-size priority
- Less-full queue selection
- Origin-queue exclusion
- Assign Labels
- Conditional Decide
- Create Task Sequence
- Load and Unload tasks
- Rehandling stacked items
- Crane-based material movement

This stage combines two interacting lists with query-based selection rules to support more complex material-handling decisions.

## Recommended Folder Structure

```text
15_FlexSim_Process_Flow_Lists_Guided_Models/
├── README.md
├── requirements.txt
├── 1_Global_List_WHERE_and_ORDER_BY.fsm
├── 2_Global_List_Multiple_Queries.fsm
├── 3_Process_Flow_List_Using_Partition_ID.fsm
├── 4_Process_Flow_List_Using_Query.fsm
├── 5_Process_Flow_Inventory_List.fsm
├── 6_Process_Flow_Inventory_List_Extended.fsm
├── 7_Process_Flow_Inventory_and_Storage_List_Extended.fsm
├── 8_Process_Flow_Pallet_and_Parts_List.fsm
├── 9_Process_Flow_Pallet_and_Parts_List_Using_Global_Table.fsm
└── 10_Process_Flow_Double_List_Crane.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Begin with Models 1–4 to study global lists, `WHERE` queries, `ORDER BY`, partition IDs, and dynamic pull conditions.
5. Use Models 5–7 to study list-based inventory matching, back orders, physical item handling, and storage assignment.
6. Run Models 8–9 to study pallet-part matching and the use of a global table to control list requirements.
7. Run Model 10 to study two interacting lists and multi-criteria query logic for crane-based material handling.
8. Keep the Process Flow and list views open while the models run to observe list entries, back orders, and pull behavior.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim Process Flow
- Global lists
- Process Flow lists
- Push to List
- Pull from List
- List partitions
- Partition IDs
- Back orders
- SQL-style list queries
- `WHERE` conditions
- `ORDER BY`
- Multi-criteria selection
- Token labels
- Inventory matching
- Order fulfillment
- Storage assignment
- Global tables
- Event-triggered logic
- Custom Code
- Task sequences
- Batch activities
- Material-handling logic
- Crane coordination
- Data-driven simulation logic

## Learning Progression

```text
Global List
        ↓
WHERE Filtering
        ↓
ORDER BY Sorting
        ↓
Multiple Query Conditions
        ↓
Partition IDs
        ↓
Dynamic Puller-Based Queries
        ↓
Inventory + Order Matching
        ↓
Back Orders + Physical Item Handling
        ↓
Storage Assignment
        ↓
Pallet-Part Matching
        ↓
Global-Table-Driven List Logic
        ↓
Double Lists + Crane Selection Logic
```

The sequence moves from basic list filtering and sorting to list-based inventory, storage, pallet configuration, and multi-list material-handling logic.
