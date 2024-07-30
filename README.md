# Envelope Material Optimizer _ thermal resistance and cost

## Overview

Welcome to the Envelope Material Optimizer! This project uses a genetic algorithm to optimize the selection of materials for building envelopes. 
The primary goal is to maximize the thermal resistance value of the envelope while minimizing costs, using a predefined material library and surface specifications.

## Features

- **Genetic Algorithm**: Employs evolutionary techniques to determine the optimal combination of materials.
- **Material Library**: Uses a JSON file containing material properties such as resistance values and costs.
- **Cost Efficiency**: Targets the highest possible resistance value within a given cost constraint.
- **Integrated Solution**: Directly integrates with existing material libraries and surface specifications for ease of use.
- **Fitness Function**: Evaluates solutions based on resistance value and cost, with penalties for exceeding target costs.

## Getting Started

### Prerequisites

- Python 3.x (Standard libraries used)

### Installation

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/munycc/Envelope-Material-Optimizer.git
    ```
2. **Navigate to the Project Directory**:
    ```bash
    cd Envelope-Material-Optimizer
    ```

### Usage

1. **Prepare Your Data**:
    - Place your `material_library.json` and `list_surfaces.json` files in the root directory of the project. 
    You can add materials / remove, the ones that are available in the file are placeholders, and also adjusts the surfaces based on your project

2. **Run the Optimization Algorithm**:
    ```bash
    python material_optimization.py
    ```

3. **Parameters**:
   - The following parameters are hardcoded in the script and should be adjusted based on your project
     - **Number of Solutions**: 500,000
     - **Number of Generations**: 1,000
     - **Fitness Function Weight for Resistance**: 4
     - **Fitness Function Weight for Cost**: 0.25
     - **Target Cost**: 60,000
     - **Mutation Rate**: 0.1

4. **Fitness Function**:
   - The `fitness_function` evaluates solutions based on:
     - **Resistance Value (`total_R`)**: Total resistance value of selected materials, normalized to the maximum possible value.
     - **Cost (`total_C`)**: Total cost of selected materials.
     - **Weights**: Configurable weights (`weight_R` and `weight_C`) that indicate the relative importance of resistance and cost.
     - **Target Cost**: An optional target cost (`target_C`). Penalties are applied if the total cost deviates from the target.

### Example Files

**`material_library.json`**:
```json
[
    {
        "name": "Material A",
        "category": "floor",
        "R_value": 2.5,
        "cost_per_sqm": 50
    },
    {
        "name": "Material B",
        "category": "ceiling",
        "R_value": 3.0,
        "cost_per_sqm": 70
    }
]
```

**`list_surfaces.json`**:
```json
{
    "Floor2": {
        "area": 100.0
    },
    "Ceiling1": {
        "area": 100.0
    }
}
```

### Contributing

Contributions are welcome! If you have improvements, bug fixes, or additional features, please open an issue or submit a pull request.

### License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

