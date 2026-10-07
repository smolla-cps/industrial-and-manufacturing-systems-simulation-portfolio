# FlexSim Sub Process Flows — Guided Models

The tutorial focuses on building and using sub flows in FlexSim Process Flow. It begins with a basic sub flow that overrides processor processing times using parent and child tokens, then extends the logic with product-type decisions, multiple Finish activities, return values, and visual changes.

## Official Tutorial

FlexSim — Tutorial 3: Sub Process Flows:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial3subprocessflows_subprocessflowsoverview_html

## Tutorial Sequence

### 3.1 — Build a Basic Sub Flow

This model introduces the basic structure of a Process Flow sub flow and uses it to dynamically control processor processing times.

The process alternates between three fast-processing items and two slow-processing items. A parent token controls the processing-time pattern while Run Sub Flow activities create child tokens that wait for the processor's Process Time event and return the required processing time.

**Concepts practiced**
- Process Flow sub flows
- Start and Finish sub flow activities
- Run Sub Flow
- Parent and child tokens
- Independent, child, and sibling token concepts
- Parent-label access
- `processTime` label
- Schedule Source
- Assign Labels
- Wait for Event
- Processor Process Time event
- Event-listening activities
- Override Return Value
- Dynamic processing-time control
- Fast and slow processing patterns
- Return values from Finish activities
- Linking Process Flow logic to a 3D Processor
- Reusable self-contained process logic

This stage establishes how a sub flow can be triggered from a main Process Flow and return a value that changes 3D model behavior.

---

### 3.2 — Add Multiple Finish Activities

This model modifies the basic sub flow so that the processor's processing time depends on the type of flow item being processed.

A `productType` label identifies fast and slow items. A Decide activity routes tokens to different branches, each with its own Change Visual and Finish activity. Product Type 1 items receive the fast processing time and are colored red, while Product Type 2 items receive the slow processing time and are colored blue.

**Concepts practiced**
- Multiple Finish activities
- Decide activities
- Conditional token routing
- `productType` labels
- Label Matching/Assignment
- `MyItem` references
- Event data
- Connector rankings
- Change Visual activities
- Dynamic flow-item color changes
- Product-dependent processing times
- Static Finish return values
- Multiple return paths from a sub flow
- Product Type 1 and Product Type 2 logic
- Linking event-triggered tokens to flow items
- Conditional sub-flow behavior

This stage demonstrates how a sub flow can branch into multiple outcomes and return different values based on token data.

## Recommended Folder Structure

```text
08_FlexSim_Sub_Process_Flows_Guided_Models/
├── README.md
├── requirements.txt
├── 3.1_Build_a_Basic_Sub_Flow.fsm
└── 3.2_Add_Multiple_Finish_Activities.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 3.1 first to observe the repeating pattern of three fast-processing items followed by two slow-processing items.
5. Watch the parent token and child tokens move through the main Process Flow and sub flow.
6. Run Model 3.2 to observe how `productType` controls both processing time and flow-item color.
7. Compare the single-Finish sub flow in Model 3.1 with the multiple-Finish conditional structure in Model 3.2.
8. Review the Wait for Event and Finish activities to see how the sub flow returns the processor's processing time.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim Process Flow
- Sub process flows
- Parent and child tokens
- Run Sub Flow activities
- Token-label access
- Event-driven logic
- Wait for Event
- Return-value overrides
- Processor process-time control
- Conditional routing
- Decide activities
- Multiple Finish activities
- Label assignment and matching
- Dynamic flow-item references
- Visual-state changes
- Reusable process logic
- Linking Process Flow with 3D objects

## Learning Progression

```text
Basic Sub Flow
        ↓
Parent + Child Tokens
        ↓
Run Sub Flow
        ↓
Wait for Processor Event
        ↓
Override Return Value
        ↓
Product-Type Labels
        ↓
Decide Logic
        ↓
Multiple Finish Activities
        ↓
Conditional Processing Time + Visual Changes
```

The sequence moves from a basic reusable sub flow to conditional sub-flow logic with multiple return paths and product-dependent behavior.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_processflow_tutorial3subprocessflows_subprocessflowsoverview_html
