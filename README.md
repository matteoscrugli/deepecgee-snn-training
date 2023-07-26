
# ECG Spike Signal Analysis with PyTorch

This project involves the analysis and visualization of ECG (Electrocardiogram) spike signals using a PyTorch based neural network. It aims to classify these signals and provide insight into their patterns over time.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Installation

The project requires the following dependencies (recommend using a virtual environment):

```
python -m venv myenv
source myenv/bin/activate  # Windows users should use `myenv\Scripts\activate`
```

Now install the dependencies:

```
pip install torch torchvision numpy matplotlib scikit-learn
```

This project also requires the Lava library, which is not available directly through pip. Lava is a productive and flexible library for asynchronous event-driven programming, particularly designed for neuromorphic computing tasks.

The Lava library can be downloaded from its official GitHub repository at [https://github.com/lava-nc/lava-dl](https://github.com/lava-nc/lava-dl). After downloading the repository as a zip file, use pip to install it. Run the following command in your command line:

```sh
pip install /path_to_downloaded_zip_file/lava-dl-main.zip
```

Please replace `/path_to_downloaded_zip_file/` in the command above with the actual path to your downloaded Lava library zip file. After running the command, the Lava library should be successfully installed and ready for use in the project. 

Ensure that you have the necessary permissions to read files from the location.

## Dataset

Our project employs the well-established MIT-BIH Arrhythmia Dataset, a rich resource for the detection and classification of cardiac arrhythmias. The dataset, contributed by the Massachusetts Institute of Technology and Boston's Beth Israel Hospital, comprises ECG recordings, each lasting approximately 30 minutes, from 47 subjects.

The ECG signals in the dataset are subjected to windowing, a procedure that frames a span of 300 samples around the label, or point of interest. This windowing operation helps us efficiently focus on specific portions of the signal related to each heart rhythm anomaly, allowing us to extract salient features for subsequent analysis and prediction.

After windowing, we partition the dataset using a 70-10-20 % scheme for training, validation, and testing, respectively. This approach ensures a balanced and unbiased evaluation of the model's performance during the learning process and when facing unseen data.

## Usage

To use this project, follow the steps below:

1. Ensure you have PyTorch and all necessary dependencies installed.
2. Load your ECG data and split them into training, validation, and test sets.
3. Adjust parameters as necessary, such as batch size or dataset paths.
4. Run the code to visualize and analyze the signals.

## Project Structure

The code is structured as follows:

1. **Data Loading**: The ECG data is loaded and preprocessed for analysis. The data is split into training, validation, and test sets. The dataset is then loaded into a DataLoader to allow efficient iteration during training.

2. **Model Definition**: The PyTorch model is defined here. It consists of a specific architecture suited to the task of classifying ECG signals. It's a custom architecture that can be modified based on specific needs.

3. **Training**: The model is trained using the training data. The training loop involves forwarding data through the model, computing the loss, performing backpropagation to compute gradients, and updating the model parameters. Training progress is logged for monitoring.

4. **Visualization**: This section creates plots to visualize spike signals over time for both normal and anomalous ECG data. The plots provide insights into the patterns of ECG signals, which can help in understanding the nature of the data and the performance of the model.

5. **Accuracy Computation**: After training, the code infers the labels for the test, validation, and training sets and computes the accuracy for each set. This gives a measure of the model's performance.

6. **Detailed Signal Plotting**: This section plots detailed signal patterns for a specific label, aiding in debugging and model evaluation. It visualizes how the model responds to a specific type of ECG signal.

## License

This project is open-source, made available under the [MIT License](LICENSE).
