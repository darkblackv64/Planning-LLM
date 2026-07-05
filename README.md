# Laboratory 4 - Planning with Qwen3-8B

## Overview

This project implements a planning system using **Qwen3-8B** to solve multi-step logical problems in a virtual simulation environment. The model receives a scenario description and generates the optimal sequence of actions required to complete the task.

The solution follows the requirements of the assignment:

- Uses **Qwen3-8B** exclusively.
- Deterministic inference with `temperature = 0.0`.
- Processes the provided evaluation dataset (`Task.json`).
- Generates a JSON output containing:
  - `complexity_level`
  - `target_action_sequence`
- Execution time is designed to remain below **2 minutes** in Google Colab.

## Project Structure

```
.
├── Examples.json        # Training examples with optimal action sequences
├── Task.json            # Evaluation scenarios
├── output.json          # Generated predictions
├── notebook.ipynb       # Main implementation
└── README.md
```

## Methodology

Our approach uses prompt engineering techniques to guide Qwen3-8B in performing structured reasoning for planning tasks. The prompting strategy is designed to infer:

1. The complexity level of the scenario.
2. The optimal sequence of actions needed to solve it.

Inference is fully deterministic (`temperature = 0.0`) to satisfy the assignment requirements.

## Requirements

- Python 3.10+
- transformers
- torch
- accelerate

## Running the Project

1. Open the notebook in Google Colab.
2. Install the required dependencies.
3. Execute all notebook cells.
4. The script will:
   - Load `Task.json`
   - Generate predictions using Qwen3-8B
   - Save the results as `output.json`

## Output Format

Each scenario produces an output similar to:

```json
{
  "complexity_level": "medium",
  "target_action_sequence": [
    "action_1",
    "action_2",
    "action_3"
  ]
}
```

## Group Members

- Juan Pedro Vazques
- Angello Soldi
