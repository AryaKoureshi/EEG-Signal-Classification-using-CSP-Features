# EEG Signal Classification using CSP Features

This repository contains a Python implementation for solving a two-class classification problem using Common Spatial Pattern (CSP) features extracted from EEG data. The classification task involves discriminating between mental tasks, specifically imagining foot movement and performing mental discrimination. The project utilizes provided EEG datasets and implements various machine learning algorithms for classification.

## Instructions

### Dataset
The EEG data is stored in the `CSPdata.mat` file, which contains training and test data along with their corresponding labels. The dimensions of the provided arrays are as follows:
- **Training Data**: A three-dimensional array (`TrainData`) with dimensions `(30 x 256 x 165)`. Each entry represents EEG recordings, with 30 channels, 256 time samples, and 165 trials.
- **Training Labels**: Labels for the training data are stored in the vector `TrainLabel`.
- **Test Data**: A three-dimensional array (`TestData`) with dimensions `(30 x 256 x 45)` representing EEG recordings for test trials.

### Tasks

1. **CSP Spatial Filters**
    - Obtain CSP spatial filters using all training data.
    - Apply the filters to the training data and visualize the filtered signals for the first and last filters.

2. **Visualization**
    - Visualize the first and last spatial filters obtained in the previous step using the `plottopomap` function.

3. **Cross Validation**
    - Divide the training data into 4 categories using 4-fold cross-validation.
    - Apply the CSP algorithm on the training data for feature extraction.
    - Train a classifier (e.g., kNN, SVM, LDA) using the extracted features and evaluate performance using validation data.
    - Determine the optimal number of CSP filters through cross-validation.

4. **Testing**
    - Apply the best classifier obtained from cross-validation to both training and test data.
    - Evaluate the classifier's performance on the test data and store the predicted labels.

### EEG Signal Details
- Recorded using the g.tec GAMMAsys system with 30 EEG measurement channels.
- Data sampled at 256 Hz with a crossover filter between 0.5 and 100 Hz and 50 Hz notch filter to remove city electricity noise.
- Each test represented as a matrix of size `(30 x 256)`.

## Usage

1. Clone the repository:

```bash
git clone https://github.com/your_username/EEG-Signal-Classification-using-CSP-Features.git
```

2. Navigate to the project directory:

```bash
cd EEG-Signal-Classification-using-CSP-Features
```

3. Open the notebook (using Jupyter Lab or Jupyter Notebook). Ensure you have all dependencies installed.

```bash
EEG_Classification_CSP.ipynb
```

## Dependencies

- `scipy`
- `numpy`
- `matplotlib`
- `scikit-learn`
- `mne`

Ensure you have these libraries installed using `pip` or any other package manager.

## Contributing

Contributions are welcome! For major changes, please open an issue first to discuss what you would like to change. Please make sure to update tests as appropriate.
