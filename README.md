# Behavioral Analysis Transformer

## About DeepHL
DeepHL (Deep Highlighting) is a deep learning-based system that automatically identifies and analyzes meaningful segments in animal trajectory data. Using attention mechanisms, this system automatically highlights parts of trajectories that characterize differences between two groups, helping researchers discover new behavioral patterns.

## Project Overview
This repository provides a Transformer-based neural network for analyzing mouse trajectory data obtained through DeepLabCut. Similar to DeepHL, it offers the following capabilities:
* Automatic identification of important behavioral segments
* Highlighting behaviorally significant patterns
* Presenting noteworthy behaviors to researchers
* Visualizing behavioral differences in an interpretable format

## Key Features

### Data Processing
- Loading coordinate data from DeepLabCut output
- Calculation of basic movement features including:
  - Velocity
  - Angular velocity
  - Distance from starting position
  - Movement patterns
- Sequence preparation for Transformer models

### Transformer Model
```python
class TransformerModel:
    - Multi-head attention mechanism
    - Positional encoding for temporal information
    - Layer-wise attention mechanism
    - Classification head for behavioral analysis
```

### Visualization Features
* Trajectory highlighting based on attention weights
* Interactive visualization of important behavioral segments
* Correlation analysis with manually designed features

![image](https://github.com/user-attachments/assets/825c9ee4-926d-49e2-b0ff-4955de5dcc1c)
![image](https://github.com/user-attachments/assets/a0ac3148-615c-45ea-889f-87a17af29981)


# Behavioral Analysis Transformer

## About DeepHL
DeepHL (Deep Highlighting) is a deep learning-based system that automatically identifies and analyzes meaningful segments in animal trajectory data. Using attention mechanisms, this system automatically highlights parts of trajectories that characterize differences between two groups, helping researchers discover new behavioral patterns.

## Project Overview
This repository provides a Transformer-based neural network for analyzing mouse trajectory data obtained through DeepLabCut. Similar to DeepHL, it offers the following capabilities:
* Automatic identification of important behavioral segments
* Highlighting behaviorally significant patterns
* Presenting noteworthy behaviors to researchers
* Visualizing behavioral differences in an interpretable format

## Key Features

### Data Processing
- Loading coordinate data from DeepLabCut output
- Calculation of basic movement features including:
  - Velocity
  - Angular velocity
  - Distance from starting position
  - Movement patterns
- Sequence preparation for Transformer models

### Transformer Model
```python
class TransformerModel:
    - Multi-head attention mechanism
    - Positional encoding for temporal information
    - Layer-wise attention mechanism
    - Classification head for behavioral analysis
```

### Visualization Features
* Trajectory highlighting based on attention weights
* Interactive visualization of important behavioral segments
* Correlation analysis with manually designed features

## Usage
```python
from mouse_analyzer import MouseTrajectoryDataset, TransformerModel
# Load data
dataset = MouseTrajectoryDataset("dlc_output.csv")
# Initialize model
model = TransformerModel(
    input_dim=dataset.features.shape[1],
    d_model=128,
    nhead=8,
    num_layers=4
)
# Train model
history = train_model(model, dataset)
# Visualize results
visualize_results(dataset, model)
```

## Requirements
* Python 3.7+
* PyTorch 1.7+
* pandas
* numpy
* matplotlib
* seaborn

## Analysis Workflow
1. Load coordinate data obtained from DeepLabCut
2. Calculate basic behavioral features
3. Identify important segments using the Transformer model
4. Highlight areas of interest using attention mechanisms
5. Visualize and interpret results

## References
- DeepHL: Deep learning-assisted comparative analysis of animal trajectories with DeepHL (Nature Communications, 2020)
- DeepLabCut: Markerless pose estimation of user-defined body parts with deep learning




