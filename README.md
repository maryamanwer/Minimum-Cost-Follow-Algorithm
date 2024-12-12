# Minimum-Cost Flow Problem - Random Graph Generation and Algorithm Analysis

## Project Overview
This project involves generating random source-sink networks, analyzing their properties, and testing four graph algorithms:
1. Successive Shortest Path Algorithm (SSP)
2. Capacity Scaling Algorithm (CS)
3. Cycle-Canceling Algorithm (CC)
4. Hybrid Algorithm

The goal is to compare the performance of these algorithms on networks with varying characteristics.

## Features
- Generate random Euclidean directed graphs with customizable parameters.
- Compute graph characteristics like edge count, in/out degrees, and average degree.
- Determine maximum flow (`f_max`) using the Ford-Fulkerson method.
- Test algorithms for flow optimization on pre-generated graphs and newly simulated graphs.
- Save results in CSV format for analysis.

## Files
- `graph_1.txt` to `graph_8.txt`: Graph data in ASCII EDGES format.
- `table1_graph_characteristics.csv`: Graph characteristics of pre-generated graphs.
- `table2_algorithm_performance.csv`: Algorithm performance on pre-generated graphs.
- `table1_graph_characteristics_new.csv`: Graph characteristics of the new graph.
- `table2_algorithm_performance_new.csv`: Algorithm performance on the new graph.

## Requirements
- Python 3.8+
- Libraries: `random`, `math`, `time`, `csv`, `pandas` (for analysis).

## Usage

### Step 1: Generate Graphs
Graphs are generated using the `generate_random_graph` function. Parameters like the number of nodes (`n`), edge density (`r`), and edge weights (`uppercap`, `uppercost`) can be customized.

### Step 2: Analyze Graph Characteristics
Use the `calculate_graph_characteristics` function to compute properties like:
- Total edges (`E`)
- Maximum in-degree (`Delta_in`) and out-degree (`Delta_out`)
- Average degree (`Avg_degree`)

### Step 3: Run Algorithms
The algorithms available are:
- **Successive Shortest Path**: `successive_shortest_path(graph, source, sink, demand)`
- **Capacity Scaling**: `capacity_scaling(graph, source, sink, demand)`
- **Cycle-Canceling**: `cycle_canceling(graph, source, sink, demand)`
- **Hybrid Algorithm**: Combines SSP and CS for efficiency.

### Step 4: Save Results
Results are saved in `table1_graph_characteristics.csv` and `table2_algorithm_performance.csv`. For new simulations, the results are saved in `*_new.csv`.

### Step 5: Analyze Results
Use tools like pandas or Excel to analyze the saved CSV files.

## Simulation II
- Change graph parameters (`n`, `r`, `uppercap`, `uppercost`) to highlight algorithm differences.
- Generate a new graph, run the algorithms, and save results.

### Example
```python
# Generate a new graph with custom parameters
new_params = {"n": 300, "r": 0.1, "uppercap": 128, "uppercost": 100}
new_graph = generate_random_graph(**new_params)
source, sink = 0, max(new_graph.keys())
demand = 0.95 * max_flow

# Run algorithms
for alg_name, alg_func in algorithms.items():
    alg_func(new_graph, source, sink, demand)
