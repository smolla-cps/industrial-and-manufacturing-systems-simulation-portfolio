# FlexSim Statistics Collector — Guided Models

The tutorial focuses on the main features of the FlexSim Statistics Collector. It covers event-based data collection, table construction, row and column logic, labels, tracked variables, timer events, row management, and dashboard charts for analyzing simulation results.

## Official Tutorial

FlexSim — Tutorial 2: The Statistics Collector:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_additionaltools_tutorial2statscollector_statscollectoroverview_html

## Tutorial Sequence

### 2.1 — Build an Average Content Collector

This model introduces the basic structure of a Statistics Collector and uses it to measure the average content of several stations.

The collector listens to model events, creates rows for station objects, stores station references, calculates continuously changing average-content values, and displays the collected results in a dashboard bar chart.

**Concepts practiced**
- Statistics Collector setup
- Events and event sampling
- On Reset events
- Row values
- Statistics Collector tables
- Rows and columns
- Row Add Value
- `data` entity
- `data.rowValue`
- Object IDs
- Station groups
- Multiple row values
- Average-content statistics
- Update when accessed
- Dashboard charts
- Bar charts
- Connecting collector tables to charts

This stage establishes the basic event-table-chart workflow used throughout the Statistics Collector tutorial.

---

### 2.2 — Build an Output Collector

This model records the output of multiple stations and demonstrates how events can update specific table columns.

The collector listens to the stations' output-change events, identifies the station that fired the event, records its current output, and uses an On Reset event to establish a consistent display order.

**Concepts practiced**
- Station output statistics
- Group-based event listening
- On Output Change events
- Event parameters
- `data.newValue`
- `current`
- Event-to-column connections
- Integer storage type
- On Reset events
- Group-member row values
- Consistent row ordering
- Output tables
- Dashboard table charts

This stage introduces event parameters and shows how one collector can respond to events from multiple objects in a group.

---

### 2.3 — Content Over Time

This model collects the changing content of a Process Flow activity and records the values over time.

The collector listens to the `Get Station` activity's content-change event, creates a new row for each change, records the model date/time and activity content, finishes each row, and displays the history using a stair-step time plot.

**Concepts practiced**
- Collecting data from Process Flow
- Process Flow activity events
- On Content Change
- Event object row values
- `data.newValue`
- Model date/time
- Time columns
- Content columns
- Finishing rows
- Historical observations
- Dashboard time plots
- Stair-step plots
- Time-series visualization

This stage demonstrates how finished rows can preserve a history of values rather than continuously updating one active row.

---

### 2.4 — Orders In Progress

This model measures the number of orders currently in progress from order arrival through fulfillment.

The collector listens to Process Flow entry events, uses a `Delta` label to add or subtract from the current count, and maintains an `OrdersInProgress` value that changes as orders enter and leave the process.

**Concepts practiced**
- Work-in-progress measurements
- Process Flow activity events
- On Entry events
- Additional event labels
- `Delta` labels
- Increment Data Value
- Incrementing and decrementing statistics
- Event-to-column connections
- On Reset initialization
- Integer data
- Orders-in-progress tracking
- Dashboard table charts

This stage demonstrates how a Statistics Collector can maintain a running count using multiple events and additional event labels.

---

### 2.5 — Orders By Size

This model measures order throughput by the number of items contained in each order.

The collector uses the `OrderSize` label from Process Flow tokens as the row value, filters orders using an event condition, increments output by order size, sorts the table by size, and displays the results in a dashboard chart.

**Concepts practiced**
- Token labels
- `OrderSize`
- Event conditions
- `data.token.OrderSize`
- Row-value filtering
- Conditional data collection
- Output counters
- Increment Data Value
- Integer columns
- Row sorting
- Static categorical row values
- Throughput by order size
- Dashboard bar charts

This stage demonstrates how event conditions and categorical row values can be used to separate statistics into meaningful groups.

---

### 2.6 — Pick Time By Type

This model records the time required for an operator to complete each item pick.

A pick begins when the operator enters the `Travel to Item` activity and ends after the `Unload Item` activity. A row label stores the start time, and the final pick duration is calculated from the difference between the current model time and that stored value.

**Concepts practiced**
- Pick-time measurement
- Start and end events
- Travel to Item
- Unload Item
- Token-based row values
- Row labels
- `PickStartTime`
- On Row Adding triggers
- `Model.time`
- Duration calculations
- `Model.time - data.row.PickStartTime`
- Type columns
- PickTime columns
- Finishing rows
- Memory-efficient row management
- Dashboard box plots
- Comparing distributions by item type

This stage introduces row labels for storing temporary information associated with individual observations.

---

### 2.7 — Average Content By Type

This model calculates the average inventory content separately for each item type.

Rows are initialized from the product-type data, while storage-system entry and exit events modify a tracked `Content` value. The collector then calculates and displays the average content for each type.

**Concepts practiced**
- Average inventory by type
- On Reset events
- Global-table row values
- Product-type categories
- Storage System events
- On Slot Entry
- On Slot Exit
- Additional `Delta` labels
- Tracked Variable Row Labels
- On Row Adding triggers
- On Row Updating triggers
- Increment row label
- Continuous average calculations
- `AvgContent`
- Dashboard bar charts
- Type-based comparison

This stage demonstrates how tracked variables on row labels can calculate averages from values that change throughout the simulation.

---

### 2.8 — Content By Type Over Time

This model records inventory content by product type as it changes over time.

Storage-system entry and exit events create observations for each item type. Row labels preserve the previous content value, while `Delta` values increment or decrement content. The collected history is displayed as separate time-series lines for each type.

**Concepts practiced**
- Inventory content by type
- On Slot Entry and On Slot Exit
- `Delta` labels
- Item-type row values
- Time, Type, and Content columns
- Event-to-column connections
- Row labels
- On Row Updating triggers
- Keep value and labels for finished rows
- Persistent row-label values
- Increment and decrement logic
- Historical type-based data
- Dashboard time plots
- Color Split By
- Stair-step visualization

This stage combines finished rows with preserved row-label data to build a type-specific history over time.

---

### 2.9 — Output By Hour By Type

This model records the total output of each product type for each hour of simulation time.

The collector counts storage-system exits by type, uses timer events to close the current hourly rows and start new ones, and records hourly output in a time-series table and chart.

**Concepts practiced**
- Output by hour
- Output by product type
- Storage System On Slot Exit events
- Timer events
- Hourly intervals
- Additional `Delta` labels
- Global-table row values
- `collector.getAllRowValues()`
- Event ordering
- On Row Adding triggers
- On Row Updating triggers
- Output row labels
- Finishing active rows
- Restarting rows for the next hour
- Time, Type, and Output columns
- Dashboard time plots
- Color Split By
- Lines-and-points visualization

This stage demonstrates how timer events can divide simulation results into repeated time intervals for hourly reporting.

## Recommended Folder Structure

```text
12_FlexSim_Statistics_Collector_Guided_Models/
├── README.md
├── requirements.txt
├── 2.1_Build_an_Average_Content_Collector.fsm
├── 2.2_Build_an_Output_Collector.fsm
├── 2.3_Content_Over_Time.fsm
├── 2.4_Orders_In_Progress.fsm
├── 2.5_Orders_By_Size.fsm
├── 2.6_Pick_Time_By_Type.fsm
├── 2.7_Average_Content_By_Type.fsm
├── 2.8_Content_By_Type_Over_Time.fsm
└── 2.9_Output_By_Hour_By_Type.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 2.1 first to understand Statistics Collector events, rows, columns, and chart connections.
5. Continue through Models 2.2–2.5 to study event parameters, time-based records, running counts, event conditions, and row sorting.
6. Run Models 2.6–2.8 to study row labels, tracked variables, finished rows, and type-based statistics.
7. Run Model 2.9 to observe how timer events create repeated hourly statistics.
8. Open each Statistics Collector table and its associated dashboard chart while the simulation is running to compare the stored table data with the visualization.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim Statistics Collector
- Event-based data collection
- Statistics tables
- Row and column configuration
- Row values
- Event parameters
- Additional labels
- Row labels
- Tracked variables
- Event conditions
- Event-to-column connections
- Process Flow statistics
- Running counters
- Time-series data
- Categorical statistics
- Timer events
- Hourly aggregation
- Row sorting
- Finished-row management
- Dashboard visualization
- Bar charts
- Table charts
- Time plots
- Box plots
- Simulation performance analysis

## Learning Progression

```text
Basic Statistics Collector
        ↓
Events + Rows + Columns
        ↓
Station Output
        ↓
Content Over Time
        ↓
Running WIP Counts
        ↓
Conditional Statistics + Row Sorting
        ↓
Row Labels + Duration Measurement
        ↓
Tracked Variables + Averages
        ↓
Type-Based Time-Series Data
        ↓
Timer Events + Hourly Output
```

The sequence moves from basic event-driven data collection to more advanced statistics involving row labels, tracked variables, historical data, type-based analysis, and repeated time-interval reporting.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_additionaltools_tutorial2statscollector_statscollectoroverview_html
