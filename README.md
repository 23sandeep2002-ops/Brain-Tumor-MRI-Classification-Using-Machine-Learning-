# Brain-Tumor-MRI-Classification-Using-Machine-Learning

A comparative study of five classical machine learning models for classifying brain MRI images into four categories: **glioma**, **meningioma**, **pituitary**, and **no tumor**. Course project for DA 514.

## Dataset
- 7,023 grayscale axial MRI slices (5,712 training / 1,311 testing)
- Sources: [figshare brain tumor dataset](https://figshare.com/articles/dataset/brain_tumor_dataset/1512427) and [Kaggle brain tumor classification (MRI)](https://www.kaggle.com/sartajbhuvaji/brain-tumor-classification-mri)
- Also available on [Hugging Face](https://huggingface.co/datasets/Cayanaaa/BrainTumorDatasets)
- The dataset is not included in this repository.

## Preprocessing
- Resized to 128×128 pixels
- Converted to grayscale
- Normalized pixel values to [0, 1]
- Flattened into 16,384-length vectors

## Models
Logistic Regression, Decision Tree, KNN (k = 5), MLP (one hidden layer, 100 neurons, ReLU, Adam), SVM (RBF kernel)

## Results
| Model | Accuracy | F1 (macro) | ROC-AUC | Log Loss |
|---|---|---|---|---|
| SVM | 96.8% | 0.966 | 0.998 | 0.081 |
| MLP | 95.3% | 0.949 | 0.993 | 0.195 |
| Logistic Regression | 94.3% | 0.939 | 0.992 | 0.335 |
| KNN (k = 5) | 89.9% | 0.892 | 0.990 | 0.343 |
| Decision Tree | 87.2% | 0.865 | 0.911 | 4.619 |

## Key Findings
- SVM performed best on nearly every metric.
- All models handled the no-tumor class very well.
- Most errors came from confusing glioma and meningioma.

## Limitations and Future Work
- Flattening images discards spatial information.
- Default hyperparameters were used, with no tuning.
- Future work: HOG/LBP/GLCM features, ensembles, hybrid deep learning, 3D modeling.

## Authors
Sandeep Kaur and Rutwik Devmurari
