# Brain Cancer Classification using Deep Learning

Deep Learning project for the classification of brain MRI images into three categories: **Glioma, Meningioma, and Brain Tumor**.

The project explores **Transfer Learning** using pre-trained Convolutional Neural Networks, with **DenseNet121** selected as the final model.

## Dataset

The dataset consists of brain MRI images belonging to three classes:

- Glioma
- Meningioma
- Brain Tumor

The dataset is divided into:

| Set | Percentage |
|---|---:|
| Training | 70% |
| Validation | 15% |
| Test | 15% |

All images are resized to **200 × 200 pixels**.

### Data Augmentation

The training images are augmented using:

- Random horizontal flip
- Random rotation
- Random zoom
- Random contrast

## Model

The final model uses **DenseNet121**, pre-trained on **ImageNet**, as the backbone.

The classification architecture is:

**Input → DenseNet121 → Global Average Pooling → Dense (256, ReLU) → Dropout (0.5) → Softmax**

The model performs multi-class classification across the three target categories.

## Training

| Parameter | Value |
|---|---|
| Backbone | DenseNet121 |
| Pre-trained on | ImageNet |
| Image size | 200 × 200 |
| Optimizer | AdamW |
| Learning rate | 0.0001 |
| Batch size | 32 |
| Maximum epochs | 20 |
| Loss function | Sparse Categorical Crossentropy |
| Dropout | 0.5 |

**Early Stopping** and **Learning Rate Reduction** are used during training to improve model performance and reduce overfitting.

## Results

The final model was evaluated on the independent test set.

| Metric | Result |
|---|---:|
| **Test Accuracy** | **90.68%** |
| **Test Loss** | **0.2235** |

An additional experiment with **Xception** was performed during the development of the project. DenseNet121 was selected as the final model.

## Technologies

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- KaggleHub
- Split-Folders
- Google Colab / Jupyter Notebook

## Project Structure

- `brainCancerDL.ipynb` — Main Jupyter Notebook containing the complete analysis, model development, training, and evaluation.
- `README.md` — Project documentation.

## How to Run

The notebook can be run using **Google Colab** or **Jupyter Notebook**.

Install the required libraries with:

`pip install tensorflow kagglehub split-folders pandas numpy matplotlib`

Then open `brainCancerDL.ipynb` and execute the cells sequentially.

The notebook handles dataset preparation, preprocessing, model creation, training, evaluation, and visualization of the results.

## Future Work

Possible improvements include:

- Fine-tuning the DenseNet121 backbone
- Comparing additional pre-trained architectures
- Evaluating precision, recall, and F1-score
- Generating a confusion matrix
- Applying Grad-CAM for model explainability
- Performing hyperparameter optimization

## Disclaimer

This project is intended for **educational and research purposes only**. The model is not a certified medical device and its predictions should not be used for medical diagnosis or clinical decisions.

## Author

**Francesco Tiengo**
