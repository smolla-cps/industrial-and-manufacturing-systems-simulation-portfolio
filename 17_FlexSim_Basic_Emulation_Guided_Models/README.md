# FlexSim Basic Emulation — Guided Models

The tutorial sequence focuses on building PLC-style control logic in FlexSim using Process Flow emulation tools. It begins with a single conveyor controlled by a photo eye and motor, then extends the system to two converging conveyors that communicate through photo-eye variables to enforce an area restriction.

## Tutorial Sequence

### 1 — Build Basic PLC Ladder Logic

This model introduces the basic structure of an emulation project in FlexSim.

A source feeds items onto a conveyor controlled by a motor. A photo eye acts as a sensor. When an item covers the photo eye, the sensor variable writes a value to the internal emulation connection. Process Flow then stops the conveyor motor, holds the item for five seconds, and restarts the motor.

**Concepts practiced**
- FlexSim emulation
- Simulated PLC logic
- General Process Flow
- Conveyor systems
- Source, Processor, and Sink objects
- Conveyor motors
- Photo eyes
- Sensor variables
- Control variables
- Server-connection variables
- Internal OPC DA connection
- OPC DA Sensor Tag
- OPC DA Control Tag
- Associated 3D objects
- Variable shared assets
- Write events
- On Cover and On Uncover events
- Stop Object
- Resume Object
- Event-Triggered Source
- Set Variable
- Delay activities
- Event-value matching
- Process Flow-based conveyor control

The control sequence is:

```text
Photo Eye Covered
        ↓
Sensor Variable Changes
        ↓
Set Motor = 0
        ↓
Stop Conveyor
        ↓
Delay 5 Seconds
        ↓
Set Motor = 1
        ↓
Resume Conveyor
```

This stage establishes the basic input-output relationship between simulated PLC sensors, controls, and Process Flow logic.

---

### 2 — Add Area Restriction PLC Logic

This model extends the basic emulation system to two conveyor lines that intersect.

Each conveyor has photo eyes before and after the shared area. When an item approaches the intersection, the Process Flow checks the state of the other conveyor's photo eye. If the restricted area is occupied, the approaching conveyor stops. When the area becomes clear, the motor restarts and the item proceeds.

**Concepts practiced**
- Two-conveyor emulation
- Converging conveyor lines
- Multiple conveyor motors
- Multiple photo-eye sensors
- Shared restricted areas
- Get Variable
- Set Variable
- Variable-to-variable communication
- `PhotoEyeState` token labels
- Conditional Decide
- Wait for Event
- Match-value logic
- On Change events
- Sensor-state checking
- Motor stop and resume logic
- Internal emulation variables
- OPC DA variable links
- Input and output organization
- Copying and adapting Process Flow logic
- Area-clear signaling
- Interlocking conveyor logic
- PLC-style mutual exclusion

The area-control logic follows this pattern:

```text
Item Reaches Entry Photo Eye
        ↓
Read Other Conveyor's Photo Eye
        ↓
Is Shared Area Clear?
      /       \
    Yes        No
     ↓          ↓
 Proceed    Motor = 0
                ↓
          Wait Until Clear
                ↓
           Motor = 1
                ↓
             Proceed
```

The exit photo eye signals when the shared area becomes clear so the waiting conveyor can resume.

This stage demonstrates how multiple sensor and control variables can work together to reproduce PLC-style interlocking logic for a shared material-handling area.

## Recommended Folder Structure

```text
17_FlexSim_Basic_Emulation_Guided_Models/
├── README.md
├── requirements.txt
├── 1_Build_Basic_PLC_Ladder_Logic.fsm
└── 2_Add_Area_Restriction_PLC_Logic.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 1 first to study the relationship between the photo-eye sensor, motor control variable, internal connection, and Process Flow logic.
5. Watch the conveyor stop when the photo eye is covered and resume after the five-second delay.
6. Run Model 2 to observe how two conveyor lines coordinate access to the shared intersection.
7. Watch the photo-eye variables and Process Flow tokens while items approach the restricted area.
8. Compare the basic single-conveyor control logic with the multi-conveyor interlocking logic.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim emulation
- PLC-style control logic
- Conveyor modeling
- Photo-eye sensors
- Conveyor motor control
- Process Flow
- Variable shared assets
- Internal OPC DA connections
- Sensor and control tags
- Event-triggered logic
- Set Variable
- Get Variable
- Conditional Decide
- Wait for Event
- Token labels
- Input/output logic
- Area restriction
- Conveyor interlocking
- Material-flow control
- PLC logic prototyping

## Learning Progression

```text
Basic Conveyor Model
        ↓
Photo-Eye Sensor
        ↓
Motor Control Variable
        ↓
Internal OPC DA Connection
        ↓
Event-Triggered PLC Logic
        ↓
Stop + Delay + Resume
        ↓
Second Conveyor
        ↓
Multiple Photo Eyes
        ↓
Get Variable + Conditional Decide
        ↓
Wait for Area-Clear Event
        ↓
PLC-Style Area Restriction
```

The sequence moves from a basic simulated PLC input-output loop to coordinated conveyor interlocking based on shared sensor states.
