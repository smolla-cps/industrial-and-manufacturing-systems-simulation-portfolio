# FlexSim Experimenter — Guided Models

The tutorial focuses on FlexSim's Experimenter tool for evaluating alternative model configurations. It covers scenario-based experiments, model parameters, performance measures, replications, result analysis, and optimization using FlexSim's OptQuest-based optimizer.

## Official Tutorial

FlexSim — Tutorial 3: Experimenter:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_additionaltools_tutorial3experimenter_experimenteroverview_html

## Tutorial Sequence

### 3.1 — Experiment Job

This model introduces the Experimenter through a simple material-handling system with one operator, two processors, a source, a sink, and a dispatcher.

The goal is to evaluate how different processor locations affect system throughput. Model parameters control the X positions of the two processors, while a performance measure records throughput at the sink. Several predefined scenarios are then run with multiple replications and compared using the Experimenter results.

**Concepts practiced**
- FlexSim Experimenter
- Experiment Jobs
- Scenario-based experimentation
- 3D model setup
- Source, Processor, Sink, Dispatcher, and Operator objects
- Use Transport logic
- Stochastic processing times
- Model Parameter Table
- Parameter lower and upper bounds
- Parameter-driven object positions
- `Location.X`
- Processor-location experiments
- Performance Measure Table
- Sink input as a performance measure
- Scenario design
- Multiple scenarios
- Multiple replications
- Experiment stop time
- Parallel scenario execution on multi-core systems
- Results database
- Performance Measure Results
- Replications Plot
- Frequency Histogram
- Correlation Plot
- Data Summary
- Raw Data
- Throughput comparison

This stage demonstrates how Experiment Jobs can compare explicitly defined model configurations and identify the best-performing scenario from repeated simulation runs.

---

### 3.2 — Optimization Job

This model extends the Experimenter workflow by replacing manually defined scenarios with an Optimization Job.

The optimizer automatically generates parameter values for the two processor locations, runs the model for each candidate scenario, evaluates the selected performance measure, ranks the results, and uses previous results to guide the search toward better scenarios.

**Concepts practiced**
- Optimization Jobs
- FlexSim Optimizer
- OptQuest optimization engine
- Automatic scenario generation
- Parameter search
- Objective functions
- Performance-measure objectives
- Stop Time
- Wall Time
- Maximum iterations
- Parameter bounds
- Optimization iterations
- Scenario evaluation
- Objective calculation
- Scenario ranking
- Iterative search
- Multi-core optimization
- Optimization status chart
- Best-scenario identification
- Local-optimum exploration
- Random search points
- Parameter-result visualization
- Comparing `Parameter1` and `Parameter2`
- Simulation-based optimization

This stage demonstrates how the optimizer can search automatically through many parameter combinations instead of requiring each scenario to be specified manually.

## Recommended Folder Structure

```text
13_FlexSim_Experimenter_Guided_Models/
├── README.md
├── requirements.txt
├── 3.1_Experiment_Job.fsm
└── 3.2_Optimization_Job.fsm
```

## How to Use the Models

1. Install Autodesk FlexSim.
2. Open the `.fsm` models in numerical order.
3. Reset the model before each simulation run.
4. Run Model 3.1 first to understand the relationship between model parameters, performance measures, scenarios, and replications.
5. Open the Experimenter and compare the results of the predefined scenarios.
6. Review the available result views, including replication plots, histograms, summaries, and raw data.
7. Run Model 3.2 to observe how the optimizer automatically generates and evaluates parameter combinations.
8. Use the optimization results chart to identify the best scenario and examine the associated parameter values.
9. Compare the manual scenario approach in the Experiment Job with the automatic search used in the Optimization Job.

## Skills Demonstrated

- Discrete-event simulation
- FlexSim Experimenter
- Scenario analysis
- What-if analysis
- Model parameters
- Parameter bounds
- Performance measures
- Simulation replications
- Experimental design
- Results analysis
- Throughput evaluation
- Simulation-based optimization
- Objective functions
- Iterative optimization
- OptQuest-based optimization
- Parameter search
- Multi-scenario comparison
- Result visualization
- Decision support using simulation

## Learning Progression

```text
Base Simulation Model
        ↓
Model Parameters
        ↓
Performance Measures
        ↓
Experiment Scenarios
        ↓
Multiple Replications
        ↓
Scenario Comparison
        ↓
Optimization Job
        ↓
Automatic Parameter Search
        ↓
Objective Evaluation
        ↓
Best-Scenario Identification
```

The sequence moves from manually comparing predefined scenarios to automatically searching for better parameter combinations using simulation-based optimization.

Official tutorial:

https://help.autodesk.com/view/FLEXSIMIN/2027/ENU/?guid=FlexSim_User_Manual_tutorials_additionaltools_tutorial3experimenter_experimenteroverview_html
