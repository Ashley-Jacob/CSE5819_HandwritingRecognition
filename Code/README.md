# Handwriting Recognition with Machine Learning

Welcome to our project! Here's how to teach a computer to read handwritten text using machine learning. We'll train a model to recognize individual handwritten letters and use clustering techniques to process and "read" entire sentences. 

Note: our code is built in Colab for easy integration with Google Drive; feel free to change destination paths or dataset uploading methods as needed!

## Overview

This project focuses on recognizing and interpreting images of handwritten capital letters. Here's the two-step process:

1. **Identifying Individual Letters**  
   We classify an image of a single handwritten capital letter into one of 26 classes using a Convolutional Neural Network (CNN).  
2. **Reading Entire Sentences**  
   Using DBSCAN clustering, we segment handwritten sentences into words, break words into individual letters, classify each letter, and reconstruct the text.

With these steps, we aim to transform an image of handwritten text (restricted to capital letters) into a readable string of text.

---

## Getting Started

### Step 1: Download the Dataset  
We use the **A-Z Handwritten Alphabets** dataset from Kaggle. Download it from [this link](https://www.kaggle.com/datasets/sachinpatel21/az-handwritten-alphabets-in-csv-format).  
Save the dataset to your Google Drive for convenient access.

### Step 2: Prepare the Dataset  
In the `Final_Handwriting_Recognition_CNN.ipynb` notebook, load the dataset by mounting your Google Drive. Update the file path as needed:

```python
from google.colab import drive
drive.mount('/content/drive')
!unzip /content/drive/My\ Drive/letterDataset.zip
df = pd.read_csv("/content/A_Z Handwritten Data.csv")
```

### Step 3: Train the Model
Click "Run All" in `Final_Handwriting_Recognition_CNN.ipynb`.
* Training takes approximately 50 minutes.
* The trained model (hw_final.keras) will be saved to your Google Drive.
For convenience, we’ve included a pretrained model so you can skip training if preferred.

### Step 4: Start Reading!
Use the IsolateLetters.ipynb notebook to process handwritten sentences.
* Upload an image of handwritten text (we've provided some test images).
* The notebook will extract individual letters and classify them using the trained CNN.
* Within seconds, you'll see the predicted text.
