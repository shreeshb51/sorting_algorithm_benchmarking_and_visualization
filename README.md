# Sorting Algorithm Benchmarking and Visualization Tool

## Overview
This project is a comprehensive benchmarking and visualization tool for comparing the performance of various sorting algorithms. It is designed to help students understand the behavior of sorting algorithms under different conditions (e.g., random, ascending, descending, and partially sorted data). The tool provides detailed metrics such as execution time, comparisons, and swaps/moves, along with visualizations to make the results easy to interpret.

---

## Features
1. **Supported Sorting Algorithms**:
   - Bubble Sort
   - Selection Sort
   - Insertion Sort
   - Merge Sort
   - Quick Sort (with median-of-three pivot selection)
   - Heap Sort
   - Timsort (Python's built-in `sorted()` function)

2. **Benchmarking**:
   - Measures execution time, comparisons, and swaps/moves for each algorithm.
   - Supports datasets of varying sizes and types (random, ascending, descending, partially sorted).

3. **Visualization**:
   - Bar charts comparing execution times across algorithms and datasets.
   - Log-scale support for better visualization of large performance differences.
   - Comparison and swap/move operation counts for detailed analysis.

4. **Interactive Mode**:
   - Allows users to configure benchmark parameters interactively (e.g., dataset size, algorithm selection).

5. **Command-Line Interface (CLI)**:
   - Supports command-line arguments for automation and scripting.

6. **Extensibility**:
   - Easy to add new sorting algorithms or datasets.
   - Modular design for maintainability and scalability.

---

## Installation
To use this project, you need Python 3.7 or later. Follow these steps to set up the environment:

1. **Install Dependencies**:
   The project requires the following Python libraries:
   - `numpy`
   - `matplotlib`
   - `argparse`

   Install them using `pip`:
   ```bash
   pip install numpy matplotlib
   ```

2. **Run the Project**:
   - Use the command-line interface or interactive mode to run benchmarks and generate visualizations.

---

## Usage

### Command-Line Interface
You can run the project with command-line arguments for automation. Here are the available options:

```bash
python sorting_algorithm_benchmarking_and_visualization.py --size 1000 --partial --log --save ./results
```

- `--size`: Dataset size (default: 1000).
- `--partial`: Include a partially sorted dataset.
- `--log`: Use logarithmic scale for time visualization.
- `--save`: Save visualizations to the specified directory.
- `--skip`: Skip specific algorithms (e.g., `--skip "Bubble Sort" "Selection Sort"`).

### Interactive Mode
If no command-line arguments are provided, the program will launch in interactive mode, prompting you for input:

```bash
python sorting_algorithm_benchmarking_and_visualization.py
```

Follow the on-screen instructions to configure the benchmark.

---

## Example Output

### Execution Times Table
```
Execution times (seconds):
----------------------------------------------------------------------------------------------------
Algorithm         Time Complexity   Space Complexity   Random       Ascending    Descending    Partially Sorted
Bubble Sort       O(n²)            O(1)               0.12345      0.00123      0.23456       0.04567
Merge Sort        O(n log n)       O(n)               0.01234      0.01023      0.01145       0.01234
Quick Sort        O(n log n)       O(log n)           0.00987      0.00876      0.00912       0.00945
Timsort (Python)  O(n log n)       O(n)               0.00567      0.00456      0.00512       0.00534
```

### Visualizations
1. **Time Comparison Chart**:
   - Bar chart comparing execution times for all algorithms and datasets.
   - Supports log scale for better visualization of large differences.

2. **Operation Counts**:
   - Bar charts showing the number of comparisons and swaps/moves for each algorithm.

---

## Adding New Algorithms
To add a new sorting algorithm:
1. Create a new class in the `algorithms/` directory that inherits from `SortingAlgorithm`.
2. Implement the required methods (`name`, `time_complexity`, `space_complexity`, and `sort`).
3. Update the `SortingBenchmark` class to include the new algorithm.

Example:
```python
class NewSort(SortingAlgorithm):
    @property
    def name(self) -> str:
        return "New Sort"

    @property
    def time_complexity(self) -> str:
        return "O(n log n)"

    @property
    def space_complexity(self) -> str:
        return "O(1)"

    def sort(self, arr: List[float]) -> List[float]:
        # Implement the sorting logic here
        return sorted_arr
```

---

## Contributing
Contributions are welcome! If you'd like to contribute:
1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Submit a pull request with a detailed description of your changes.

---

## Acknowledgments
- Inspired by classic sorting algorithm analysis and visualization tools.
- Built with Python's `numpy` and `matplotlib` libraries for numerical computation and visualization.

---
