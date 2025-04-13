# Research Title: Automated Melanoma Detection using CNN, VLM & LLM

### A custom VLM where a fine-tuned CNN model as image encoder & text encoder have used to leverage the image-text relationship. This way end-user will get a textual description of their skin lesion images & a brief knowledge  of their skin lesion to take proper initiative.

Dataset list (From Kaggle): 
1. [HAM 10000](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000)<sup>[<a href="#ref1">1</a>]</sup>
2. [PAD-UFES-20](https://www.kaggle.com/datasets/mahdavi1202/skin-cancer)<sup>[<a href="#ref2">2</a>]</sup>
3. [Derm7pt](https://www.kaggle.com/datasets/menakamohanakumar/derm7pt)<sup>[<a href="#ref3">3</a>]</sup>
4. [PH2](https://www.kaggle.com/datasets/kliuiev/ph2databaseaddi)<sup>[<a href="#ref4">4</a>]</sup>

# Procedure for Code Execution

## In Kaggle:
 ### 1. Import the Notebook(s) in Kaggle.
 ### 2. Add the dataset to the notebook through "Add Input".
 ### 3. Run all the cells in the notebook.

## In Google Colab/ Local:
### 1. Import the Notebook(s) in Google Colab or clone the repository.
### 2. As these datasets are from Kaggle, you need to create a Kaggle API key.
    Go to your Kaggle account settings and click "Create New Token". This will download a file called kaggle.json.
### 3. Upload the kaggle.json file to your Google Colab or local environment by adding the following code:
```python
from google.colab import files
files.upload()

!mkdir -p ~/.kaggle
!mv kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json
```

### 4. Download the datasets:
```python
%cd /content/dataset
!mkdir <Dataset Name>
%cd /content/dataset/<Dataset Name>
!kaggle datasets download <Dataset Owner User Name/Dataset Name>
!unzip <Dataset Name>.zip
!rm <Dataset Name>.zip
```
### 5. Run all other cells in the notebook.

#### Note: In case of VLM, you need to get you HuggingFace API key. Click on your profile picture in the top right corner of the Hugging Face website, then click on "Access Tokens". Then click on "Create new token" to create a new token. You can give it a name and set the scope to "read" or "write" depending on your needs. Once you have created the token, copy it and use it in your code.
```python
from huggingface_hub import login
login(token="<HF TOKEN>")
```

References Papers/Sources:

1. <a id="ref1"></a> [HAM10000](https://arxiv.org/abs/1803.10417)
2. <a id="ref2"></a> [PAD-UFES-20](https://www.sciencedirect.com/science/article/pii/S235234092031115X)
3. <a id="ref3"></a> [Derm7pt](https://arxiv.org/abs/2409.12390)
4. <a id="ref4"></a> [PH2](https://www.fc.up.pt/addi/ph2%20database.html)