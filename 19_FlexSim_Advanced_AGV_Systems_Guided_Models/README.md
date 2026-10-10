# FlexSim Advanced AGV Systems — Guided Models

The training sequence focuses on advanced AGV modeling using FlexSim AGV templates and Process Flow. It progresses from basic AGV transport to pathway networks, control points, instanced Process Flows, AGV API-based routing, list-based control, work forwarding, parking strategies, battery tracking, dynamic pickup and drop-off logic, and trailer-based transport.

## Training Sequence

### Phase 1 — Basic AGV Transport

This model introduces an AGV as a task executer in a basic transport system.

A source creates flow items, a queue sends them to two processors, and the AGV transports the items using standard task-sequence behavior and the Default Navigator.

**Concepts practiced**
- AGV as a TaskExecuter
- Standard object task sequences
- Default Navigator
- Source, Queue, Processor, and Sink objects
- Round-robin routing
- Travel, Load, and Unload behavior
- Basic material transport

This phase establishes the baseline AGV behavior before a dedicated AGV network is added.

---

### Phase 2 — AGV Pathway Network

This model replaces simple navigation with an AGV pathway network.

A one-way loop connects the queue and processors. Control Points connect the 3D objects to the AGV pathway system, and AGV Network Properties govern travel behavior.

**Concepts practiced**
- AGV pathway objects
- Straight and curved paths
- Join Paths
- Control Points
- Location and traveler connections
- One-way AGV loops
- AGV Network Properties
- AGV Navigator
- Path-based task execution

This phase introduces structured AGV navigation and control-point-based routing.

---

### Phase 3a — Instanced AGV Control Flow

This model introduces an instanced Process Flow attached to an AGV.

A token represents the attached AGV and repeatedly creates task sequences that move the AGV around the loop. At each control point, the AGV performs a short delay representing work.

**Concepts practiced**
- Instanced Process Flow
- Object Process Flow
- Attached-object behavior
- `current` object reference
- Create Task Sequence
- Travel and Delay activities
- Finish Task Sequence
- Repeating AGV control loops

This phase moves AGV behavior from standard object logic into reusable instance-based Process Flow logic.

---

### Phase 3b — Control Point Connections

This model expands the control loop by using AGV control-point connection types.

The AGV determines its current control point and uses connection relationships to identify the next work point on the route.

**Concepts practiced**
- AGV connection types
- `NextWorkPoint`
- Control-point relationships
- AGV API
- `AGV(current).currentCP`
- `AGV.Connections()`
- Dynamic next-stop logic
- Assign Labels
- Task-sequence routing

This phase introduces API-driven routing through the AGV control-point network.

---

### Phase 3c — Extended Control Point Connections

This model continues the control-point routing logic and expands the use of AGV connection relationships.

**Concepts practiced**
- Control-point connection logic
- AGV API expressions
- Dynamic routing
- Current-control-point references
- Next-work-point selection
- Instanced AGV behavior
- Reusable control loops

This phase further develops control-point-based AGV navigation.

---

### Phase 3d — List-Based Control Loop

This model introduces a list to manage available next control points.

The AGV identifies its current location and pulls an eligible next control point from a list before creating the travel task sequence.

**Concepts practiced**
- Process Flow lists
- Control-point lists
- Pull from List
- Available-control-point selection
- List-based AGV routing
- AGV instance flows
- Task-sequence creation
- Dynamic route selection

This phase shifts route selection from direct connection lookup to list-based control.

---

### Phase 3e — Re-push Control Point

This model extends the list-based control loop by pushing the selected control point back onto the list after use.

**Concepts practiced**
- Push to List
- Pull from List
- Re-pushing control points
- Reusable list entries
- Control-point availability
- Repeating AGV work loops
- List-based routing

This phase completes the progression from connection-based routing to reusable list-managed control points.

---

### Phase 4a — AGV Work Management

This model brings flow-item transport back into the custom AGV control loop.

Items are pushed to a global list, incoming work is managed through Process Flow, and the AGV checks for work while moving through its `NextWorkPoint` loop.

**Concepts practiced**
- Global item lists
- AGV work management
- Work scanning
- Resource shared assets
- Push to List
- Pull from List
- Work partitioning
- Item location labels
- Loading and unloading logic
- NextWorkPoint loop
- Custom AGV task execution

This phase integrates material transport with the custom AGV routing framework.

---

### Phase 4b — Updated 3D Work System

This model extends the Phase 4 system with updated 3D objects and multiple AGVs.

**Concepts practiced**
- Multi-AGV systems
- Updated 3D transport layout
- Global work lists
- Work assignment
- Loading and unloading
- Control-point routing
- Multiple task executers
- Scalable AGV Process Flow logic

This phase prepares the model for the AGV template examples.

---

### AGV Template 1 — Work Forwarding

This model introduces the prebuilt AGV template with Work Forwarding.

Work Forwarding allows work to be signaled to AGVs from locations other than the AGV's current control point.

**Concepts practiced**
- Prebuilt AGV templates
- Work Forwarding
- Work-forwarding control-point connections
- Remote work signaling
- AGV work-loop integration
- Dynamic work discovery

---

### AGV Template 2 — Basic Parking

This model introduces basic AGV parking using Park Point connections together with Work Forwarding.

**Concepts practiced**
- AGV parking
- Park Points
- Work Forwarding
- Parking-location assignment
- Idle AGV management
- Reactivation for new work

---

### AGV Template 3 — Heuristic Parking

This model introduces a more advanced parking heuristic with battery tracking.

The parking logic compares active transport demand with the total capacity of active AGVs. An AGV can park when enough active capacity remains, and parked AGVs can be reactivated when demand increases.

**Concepts practiced**
- Heuristic parking
- Active-item demand
- Active-AGV capacity
- AGV reactivation
- Battery tracking
- `BatteryRechargeThreshold`
- `BatteryResumeThreshold`
- Process Flow variables
- Charging behavior
- List-based parking management

---

### AGV Template 4 — Advanced

This model extends the AGV template with more advanced pickup and drop-off control.

Control-point connection types and lists are used to support multiple dynamic pickup and drop-off locations.

**Concepts practiced**
- Advanced AGV template
- Pickup Points
- Dropoff Points
- Control-point connection types
- Dynamic pickup and drop-off locations
- Lists
- Multi-location transport logic
- Advanced AGV routing

---

### AGV Trailers — For-Loop Version

This model extends the AGV template to support trailers.

The AGV tows two trailers with four-item capacity each. Trailer creation, attachment, loading, unloading, and capacity management are handled through Process Flow, AGV API methods, list logic, and FlexScript `for` loops.

**Concepts practiced**
- AGV trailers
- Trailer creation and attachment
- `AGV.attachTrailer()`
- `AGV.coupleTrain()`
- `AGV.detachTrailer()`
- `AGV.uncoupleTrain()`
- Trailer lists
- Trailer capacity management
- Move Object
- Loading into trailers
- Unloading from trailers
- `Table.query()`
- FlexScript `for` loops
- Summing trailer contents
- User commands
- AGV template customization

This model demonstrates how the prebuilt AGV template can be extended when the standard AGV capacity logic does not account for trailer contents.

## Recommended Folder Structure

```text
19_FlexSim_Advanced_AGV_Systems_Guided_Models/
├── README.md
├── requirements.txt
├── AGV_Part_1_Phase_1.fsm
├── AGV_Part_1_Phase_2.fsm
├── AGV_Part_1_Phase_3a.fsm
├── AGV_Part_1_Phase_3b_Control_Point_Connections.fsm
├── AGV_Part_1_Phase_3c_Control_Point_Connections.fsm
├── AGV_Part_1_Phase_3d_List_Based_Control_Loop.fsm
├── AGV_Part_1_Phase_3e_Repush_Control_Point.fsm
├── AGV_Part_1_Phase_4a.fsm
├── AGV_Part_1_Phase_4b_Updated_3D.fsm
├── AGV_Template_1_Work_Forwarding.fsm
├── AGV_Template_2_Basic_Parking.fsm
├── AGV_Template_3_Heuristic_Parking.fsm
├── AGV_Template_4_Advanced.fsm
└── AGV_Adding_Trailers_For_Loop_Version.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in sequence.
3. Reset each model before a new simulation run.
4. Start with Phases 1–2 to review basic AGV transport, pathways, control points, and AGV network behavior.
5. Continue through Phases 3a–3e to study instanced Process Flow, AGV API routing, control-point connections, and list-based control.
6. Run Phases 4a–4b to observe how transport work is integrated into the custom AGV control loop.
7. Open AGV Templates 1–4 in order to compare Work Forwarding, Basic Parking, Heuristic Parking, and the Advanced template.
8. Run the trailer model last to study template customization, trailer loading, capacity calculation, and FlexScript `for` loops.
9. Keep the 3D model, Process Flow, AGV network, and list views open while the models run.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim AGV modeling
- AGV pathways
- Control Points
- AGV Network Properties
- AGV Navigator
- Instanced Process Flow
- Task sequences
- AGV API
- NextWorkPoint logic
- Global and Process Flow lists
- Work management
- Work Forwarding
- AGV parking
- Heuristic parking
- Battery tracking
- Process Flow variables
- Dynamic pickup and drop-off points
- Trailer-based AGV transport
- Table queries
- FlexScript `for` loops
- User commands
- AGV template customization
- Multi-AGV material-handling systems

## Learning Progression

```text
Basic AGV Transport
        ↓
AGV Pathway Network
        ↓
Control Points + AGV Navigator
        ↓
Instanced AGV Process Flow
        ↓
AGV API + NextWorkPoint
        ↓
List-Based Control Loop
        ↓
AGV Work Management
        ↓
Work Forwarding
        ↓
Basic Parking
        ↓
Heuristic Parking + Battery Tracking
        ↓
Dynamic Pickup / Drop-Off
        ↓
Trailer-Based AGV Transport
        ↓
AGV Template Customization
```

The sequence moves from basic AGV transportation to advanced fleet behavior using template-based work management, parking, battery logic, dynamic routing, and trailer customization.
