# pneumonia-detection-localisation
Pneumonia is a life-threatening lung infection particularly in children under 5, especially in areas lacking specialized radiologists. The challenge is to detect and localize pneumonia in chest X-rays where only weak labels (image-level pneumonia positive/negative) are available, lacking precise location annotations.

This project implements a weakly supervised learning approach for detecting and localizing pneumonia in chest X-ray images. The dataset used is the RSNA Pneumonia Detection Challenge dataset from Kaggle.
The model does not rely on bounding-box annotations. Instead, it uses only image-level labels to both classify and localize pneumonia regions using Class Activation Maps (CAMs).
The notebook final_Weakly_Supervised_Pneumonia_Localization.ipynb contains all stages of the workflow: data loading, preprocessing, model training, evaluation, and visualization of results.

Dataset
The dataset used in this project is too large to be stored directly in this repository.
A file named link-to-dataset.rtf is provided, which contains the official Kaggle URL for downloading the RSNA Pneumonia Detection Challenge dataset.

To set up the dataset:
Open link-to-dataset.rtf and visit the Kaggle link provided.
Download the dataset zip file from the Kaggle page.
Extract the dataset contents into a folder.
Place that folder in the same directory as the Jupyter Notebook (final_Weakly_Supervised_Pneumonia_Localization.ipynb).
The notebook expects the dataset path to be relative to its own directory.

Requirements
Install the dependencies before running the notebook:
pip install numpy pandas matplotlib opencv-python pydicom torch torchvision scikit-learn tqdm
You can also create a virtual environment and install the dependencies there.

How to Run
Ensure that the dataset is extracted and placed in the same directory as the notebook.
Open the notebook in Jupyter or VS Code.
Run all cells in order.
The training process will begin, and model checkpoints will be saved automatically.
Once training is complete, the notebook will generate Class Activation Maps (CAMs) showing pneumonia localization.

Project Structure
Weakly-Supervised-Pneumonia-Localization/
final_Weakly_Supervised_Pneumonia_Localization.ipynb
link-to-dataset.rtf
sample_submission.csv
README.md

Model Summary
Architecture: Custom CNN (SmallCAMNet)
Learning Type: Weakly Supervised
Input: DICOM chest X-ray images
Output: Classification (pneumonia/no pneumonia) + localization heatmaps
Loss Function: Binary Cross Entropy
Visualization: Class Activation Maps for interpretability

Results
The model produces both:
Classification metrics (accuracy, loss, etc.), and
Visual localization heatmaps identifying pneumonia-affected regions.
Quantitative metrics and visual examples are shown within the notebook output.

Notes
The dataset must be kept locally and is not included in this repository.
The notebook is designed to run locally (on CPU or GPU) without requiring cloud mounts.
For reproducibility, all random seeds are set within the notebook.
