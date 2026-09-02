````markdown
# Brain Cancer Classification using Deep Learning

Deep Learning project for the classification of brain MRI images into three categories: **Glioma, Meningioma, and Brain Tumor**.

The project uses **Transfer Learning** with a pre-trained **DenseNet121** model, combined with data augmentation and a custom classification head.

## Dataset

The dataset contains brain MRI images divided into:

- **70%** Training
- **15%** Validation
- **15%** Test

Images are resized to **200 × 200 pixels**.

Data augmentation techniques include random horizontal flipping, rotation, zoom, and contrast adjustment.

## Model

The final model is based on **DenseNet121**, pre-trained on ImageNet.

```text
Input (200x200)
      ↓
DenseNet121
      ↓
Global Average Pooling
      ↓
Dense (256, ReLU)
      ↓
Dropout (0.5)
      ↓
Softmax
      ↓
3 Classes
````

### Training

| Parameter     | Value                           |
| ------------- | ------------------------------- |
| Backbone      | DenseNet121                     |
| Optimizer     | AdamW                           |
| Learning Rate | 0.0001                          |
| Batch Size    | 32                              |
| Epochs        | 20                              |
| Loss          | Sparse Categorical Crossentropy |
| Dropout       | 0.5                             |

Early stopping and learning-rate reduction are used during training.

## Results

The final model achieved:

| Metric            |     Result |
| ----------------- | ---------: |
| **Test Accuracy** | **90.68%** |
| **Test Loss**     | **0.2235** |

An additional experiment with **Xception** was also performed, while DenseNet121 was selected as the final model.

## Technologies

* Python
* TensorFlow / Keras
* NumPy
* Pandas
* Matplotlib
* KaggleHub
* Split-Folders
* Google Colab / Jupyter Notebook

## Project Structure

```text
brain-cancer-classification/
├── brainCancerDL.ipynb
└── README.md
```

## How to Run

The notebook can be executed using **Google Colab** or **Jupyter Notebook**.

Install the required libraries if necessary:

```bash
pip install tensorflow kagglehub split-folders pandas numpy matplotlib
```

Then open `brainCancerDL.ipynb` and execute the cells sequentially.

## Future Work

Possible improvements include:

* Fine-tuning DenseNet121
* Comparing additional architectures
* Computing precision, recall, and F1-score
* Generating a confusion matrix
* Applying Grad-CAM for model explainability
* Hyperparameter optimization

## Disclaimer

This project is intended for **educational and research purposes only**. The model is not a certified medical device and should not be used for medical diagnosis or clinical decisions.

## Author

Francesco Tiengo

```
```
