# **An Intelligent Predictive Analytics Framework for Fraudulent Digital Transaction Detection**

---

# **a. URL / SOURCE FOR DATASET**

---

## **DATASET 1 : CREDIT CARD FRAUD DATASET**

* **Source**       : Kaggle
* **URL**          : [https://www.kaggle.com/datasets/kartik2112/fraud-detection](https://www.kaggle.com/datasets/kartik2112/fraud-detection)
* **File Name**    : fraudTrain.csv
* **Dataset Size** : 1,296,675 transactions | 23 columns
* **Target Column**: is_fraud (0 = Legitimate, 1 = Fraudulent)

### **Class Distribution**

* **Legitimate (0)** : 1,289,169 transactions (99.42%)
* **Fraudulent (1)** : 7,506 transactions (0.58%)

### **Key Features**

* trans_date_trans_time : Transaction timestamp
* cc_num : Credit card number
* merchant : Merchant name
* category : Transaction category
* amt : Transaction amount
* first, last : Cardholder name
* gender : Cardholder gender
* street, city, state : Billing address
* lat, long : Cardholder location coordinates
* city_pop : City population
* job : Cardholder occupation
* dob : Date of birth
* unix_time : Unix timestamp
* merch_lat, merch_long : Merchant location coordinates
* is_fraud : Target label

### **Download Steps**

* Step 1 : Go to [https://www.kaggle.com/datasets/kartik2112/fraud-detection](https://www.kaggle.com/datasets/kartik2112/fraud-detection)
* Step 2 : Click Download
* Step 3 : Upload fraudTrain.csv to Google Colab as /content/fraudTrain.csv

---

## **DATASET 2 : UPI FRAUD DATASET (SYNTHETIC)**

* **Source**       : Synthetically Generated / Kaggle
* **URL**          : [https://www.kaggle.com](https://www.kaggle.com) (Search: synthetic UPI fraud transaction dataset)
* **File Name**    : synthetic_fraud_dataset.csv
* **Dataset Size** : 50,000 transactions | 22 columns
* **Target Column**: Fraud_Label (0 = Safe, 1 = Fraud)

### **Class Distribution**

* **Safe (0)** : 33,933 transactions (67.87%)
* **Fraud (1)** : 16,067 transactions (32.13%)

### **Key Features**

* Transaction_ID : Unique transaction ID
* User_ID : User identifier
* Transaction_Amount : Amount transferred (INR)
* Transaction_Type : Type of UPI transaction
* Timestamp : Date and time
* Account_Balance : User account balance
* Device_Type : Mobile device type
* Location : Geographic location
* Merchant_Category : Category of merchant
* Merchant_UPI_ID : UPI ID of merchant
* IP_Address_Flag : Suspicious IP flag
* Previous_Fraudulent_Activity : Past fraud history flag
* Daily_Transaction_Count : Transactions per day
* Avg_Transaction_Amount_7d : 7-day average amount
* Failed_Transaction_Count_7d : Failed attempts in 7 days
* Card_Age : Age of payment card (days)
* Transaction_Distance : Distance from usual location
* Risk_Score : Computed risk score
* Fraud_Label : Target label

### **Download Steps**

* Step 1 : Search on Kaggle for "synthetic UPI fraud dataset"
* Step 2 : Download synthetic_fraud_dataset.csv
* Step 3 : Upload to Google Colab as /content/synthetic_fraud_dataset.csv

---

## **DATASET 3 : ATM SURVEILLANCE DATASET (ATMA-V)**

* **Source**       : Custom Video Dataset (ATMA-V)
* **Type**         : Video dataset with frame-level annotations
* **Storage**      : Google Drive
* **Total Videos** : 65 MP4 video files

### **Video Files Used in This Project**

* 71.mp4, 75.mp4, 76.mp4, 78.mp4, 80.mp4, 82a.mp4
* 82b.mp4, 83.mp4, 84.mp4, 87.mp4, 88.mp4, 89.mp4
* 90.mp4, 92.mp4, 93.mp4 (and more in the full dataset)

### **Labels File**

* **File Name** : labels.txt
* **Label Format** : filename total_frames fps start_frame end_frame
* **(-1 -1 means no suspicious activity in that video)**

### **Sample Label Entries**

* 71.mp4 1128 25 1 1128 (full video is suspicious)
* 75.mp4 712 25 80 687 (frames 80 to 687 are suspicious)
* 92.mp4 588 6 225 340 (frames 225 to 340 are suspicious)
* 12.mp4 910 24 -1 -1 (no suspicious activity)

### **Google Drive Folder Structure**

* MyDrive/

  * ATMA-V Dataset/

    * videos/ (All MP4 files)
    * labels/

      * labels.txt (Annotation file)
    * ATM_Output/

      * face_detected_output.mp4 (Generated output)

### **Setup Steps**

* Step 1 : Upload the ATMA-V Dataset folder to your Google Drive
* Step 2 : Mount Drive in Colab using:

```
from google.colab import drive
drive.mount('/content/drive')
```

* Step 3 : Verify path:

```
BASE_DIR = "/content/drive/MyDrive/ATMA-V Dataset"
```

---

# **b. SOFTWARE AND HARDWARE REQUIREMENTS**

---

## **SOFTWARE REQUIREMENTS**

* **Operating System** : Windows 10/11 | macOS 12+ | Ubuntu 20.04+
* **Python Version** : Python 3.10 or above
* **Primary IDE** : Google Colab (Recommended)
* **Secondary IDE** : VS Code with Jupyter Extension
* **Browser** : Google Chrome / Microsoft Edge (latest)

### **Python Libraries Required**

#### **Data Processing and Visualization**

* pandas >= 2.0.0
* numpy >= 1.24.0
* matplotlib >= 3.7.0
* seaborn >= 0.12.0

#### **Machine Learning (CC and UPI Notebooks)**

* scikit-learn >= 1.3.0
* xgboost >= 1.7.0
* lightgbm >= 4.0.0

#### **Deep Learning (CC and UPI Notebooks)**

* tensorflow >= 2.13.0
* keras >= 2.13.0

#### **Deep Learning (ATM Notebooks)**

* torch >= 2.0.0
* torchvision >= 0.15.0
* diffusers >= 0.20.0

#### **Computer Vision (ATM Notebooks)**

* opencv-python >= 4.8.0
* Pillow >= 10.0.0
* tqdm >= 4.65.0
* mediapipe == 0.10.31

#### **Pre-trained Models Used in ATM Notebooks**

* ResNet18 (PyTorch via torchvision)
* ResNet50 (TensorFlow / Keras)
* SSD Face Detector (OpenCV DNN - res10_300x300_ssd)
* Stable Diffusion Inpainting (runwayml/stable-diffusion-inpainting)

### **Install Command (Run in terminal or Colab)**

```
pip install pandas numpy matplotlib seaborn scikit-learn
pip install xgboost lightgbm tensorflow keras
pip install torch torchvision
pip install opencv-python Pillow tqdm mediapipe==0.10.31
pip install diffusers transformers accelerate
```

### **Notebook Viewer (Web Interface)**

* VS Code with Live Server Extension (by Ritwick Dey)
* Files needed: FYP.html and nb_data.js (both in same folder)
* Any modern browser to view

---

## **HARDWARE REQUIREMENTS**

### **Minimum Configuration**

* Processor : Intel Core i5 / AMD Ryzen 5 (8th Gen+)
* RAM : 8 GB
* Storage : 15 GB free disk space
* GPU : Not required for CC and UPI notebooks
* Internet : Required for Google Colab

### **Recommended Configuration**

* Processor : Intel Core i7 / AMD Ryzen 7 (10th Gen+)
* RAM : 16 GB or above
* Storage : 25 GB free disk space
* GPU : NVIDIA GPU with CUDA support (Required for ATM notebooks)
* Internet : High-speed (for Colab and Google Drive access)

### **Google Colab Configuration Used for This Project**

* GPU Runtime : Tesla T4 / A100 (Free / Pro tier)
* RAM : 12 GB (Free) / 25 GB (Pro)
* Storage : Google Drive (15 GB free / expandable)

---

# **c. DETAILED INSTRUCTIONS TO EXECUTE THE SOURCE CODE**

---

## **OPTION 1 : RUN ON GOOGLE COLAB (RECOMMENDED)**

### **Prerequisite Setup**

* **Step 1** : Create a Google account at [https://accounts.google.com](https://accounts.google.com)
* **Step 2** : Go to [https://drive.google.com](https://drive.google.com)
* **Step 3** : Upload the ATMA-V Dataset folder to your Google Drive
  (Required only for ATM notebooks)
* **Step 4** : Upload the dataset CSV files to Google Drive or
  directly to Colab session storage

### **Steps to Run Each Notebook**

* **Step 1** : Go to [https://colab.research.google.com](https://colab.research.google.com)

* **Step 2** : Click File > Upload Notebook

* **Step 3** : Select the .ipynb file you want to run

* **Step 4** : Click Runtime > Change Runtime Type

  Select Python 3
  Hardware Accelerator: GPU (for ATM notebooks)
  Click Save

* **Step 5** : Upload dataset file

  For CC notebooks : Upload fraudTrain.csv
  (Click folder icon on left > Upload)

  For UPI notebooks : Upload synthetic_fraud_dataset.csv

  For ATM notebooks : Mount Google Drive
  (Cell 1 will do this automatically)

* **Step 6** : Click Runtime > Run All

* **Step 7** : Wait for all cells to execute

* **Step 8** : To save outputs: File > Download > Download .ipynb

---

## **OPTION 2 : RUN LOCALLY IN VS CODE**

* **Step 1 : Install Python**

  Download from [https://www.python.org/downloads/](https://www.python.org/downloads/)
  Check "Add Python to PATH" during install

* **Step 2 : Install VS Code**

  Download from [https://code.visualstudio.com/](https://code.visualstudio.com/)

  Install extensions:

  * Jupyter (by Microsoft)
  * Python (by Microsoft)

* **Step 3 : Install Required Libraries**

  Open terminal in VS Code (Ctrl + `) and run:

```
pip install pandas numpy matplotlib seaborn
pip install scikit-learn xgboost lightgbm
pip install tensorflow keras
pip install torch torchvision
pip install opencv-python Pillow tqdm
pip install mediapipe==0.10.31 diffusers
```

* **Step 4 : Update Dataset Paths in Notebooks**

  FROM : /content/fraudTrain.csv
  TO : C:/path/to/your/fraudTrain.csv

  FROM : /content/synthetic_fraud_dataset.csv
  TO : C:/path/to/your/synthetic_fraud_dataset.csv

  FROM : /content/drive/MyDrive/ATMA-V Dataset
  TO : C:/path/to/your/ATMA-V Dataset

* **Step 5 : Run the Notebook**

  Open the .ipynb file in VS Code

  Click "Select Kernel" > Choose your Python environment

  Click Run All or run cells one by one using the play button

---

# **NOTEBOOK EXECUTION ORDER**

---

# **DOMAIN 1: CREDIT CARD FRAUD DETECTION**

### **Step 1 : PP3CC_DL_8_2.ipynb**

* **Deep Learning models** : LSTM, Attention-LSTM, GRU
* **Dataset** : fraudTrain.csv (1,296,675 transactions)
* **Preprocessing** : TruncatedSVD (48,937 features reduced to 50)

**Results:**

* LSTM : Accuracy = 94.89%, ROC-AUC = 0.9846
* Attention-LSTM : Accuracy = 94.82%, ROC-AUC = 0.9820
* GRU : Accuracy = 95.07%, ROC-AUC = 0.9849

---

### **Step 2 : PP3CC_ML_8_2.ipynb**

* **ML Models** : Logistic Regression, Linear Regression,
  KNN, XGBoost, LightGBM

* **Dataset** : fraudTrain.csv (balanced to 27,506 records)

* **Preprocessing** : TruncatedSVD (48,937 features reduced to 50)

* **Output** : Confusion matrix and ROC curves for all models

---

# **DOMAIN 2: UPI FRAUD DETECTION**

### **Step 3 : PP3UPI_DL_8_2.ipynb**

* **Deep Learning models** : LSTM, Attention-LSTM, GRU

* **Dataset** : synthetic_fraud_dataset.csv (50,000 records)

* **Preprocessing** : TruncatedSVD (110,119 features reduced to 50)

**Results:**

* LSTM : Accuracy = 99.66%, ROC-AUC = 0.9999
* Attention-LSTM : Accuracy = 99.40%, ROC-AUC = 0.9999
* GRU : Accuracy = 99.66%, ROC-AUC = 0.9999

---

### **Step 4 : PP3UPI_ML_8_2.ipynb**

* **ML Models** : Logistic Regression, Linear Regression,
  KNN, XGBoost, LightGBM, SVM

* **Dataset** : synthetic_fraud_dataset.csv (50,000 records)

* **Preprocessing** : TruncatedSVD (110,084 features reduced to 50)

**Results:**

* Logistic Regression : Accuracy = 79.97%, Log Loss = 0.3795
* Linear Regression : Accuracy = 80.25%, Log Loss = 0.3917
* KNN : Accuracy = 83.08%, Log Loss = 0.6172
* XGBoost : Accuracy = 97.33%, Log Loss = 0.0844
* LightGBM : Accuracy = 97.77%, Log Loss = 0.0716
* SVM : Accuracy = 98.06%, Log Loss = 0.0404

---

### **Step 5 : PP3UPI_TA.ipynb**

* **Purpose** : UPI Transaction Analysis (Exploratory Data Analysis)
* **Dataset** : synthetic_fraud_dataset.csv
* **Output** : Hourly, daily, weekly and monthly fraud trend visualizations

---

### **Step 6 : UPI_AD__1_.ipynb**

* **Purpose** : Unsupervised Anomaly Detection

* **Models** : Isolation Forest, One-Class SVM, Local Outlier Factor (LOF)

* **Dataset** : synthetic_fraud_dataset.csv (50,000 records)

* **Preprocessing** : TruncatedSVD (110,019 features reduced to 50)

**Results (on 10,000 test samples):**

* Isolation Forest : Fraud detected = 835 out of 10,000
* One-Class SVM : Fraud detected = 320 out of 10,000
* LOF : Fraud detected = 116 out of 10,000

---

# **DOMAIN 3: ATM SURVEILLANCE**

### **Step 7 : ATM1.ipynb**

* **Purpose** : ATM Video Data Pipeline and Model Training

* **Dataset** : ATMA-V (65 videos with frame-level labels)

* **Models** : CNN, CNN+LSTM, CNN+BiLSTM, CNN+BiLSTM+Attention

* **Backbone** : ResNet18 (PyTorch, pretrained on ImageNet)

**Results:**

* CNN : Accuracy = 91.53%

* CNN+LSTM : Accuracy = 96.61%

* CNN+BiLSTM : Accuracy = 100.00%

* CNN+BiLSTM+Attention : Accuracy = 98.31%

* **Output** : Flags ABNORMAL / FRAUD ACTIVITY in real time

---

### **Step 8 : ATM2.ipynb**

* **Purpose** : ATM Face Detection and Inpainting

* **Face Detector** : OpenCV DNN SSD (res10_300x300_ssd_iter_140000)

* **Inpainting Model** : Stable Diffusion Inpainting
  (runwayml/stable-diffusion-inpainting)

* **Output** : face_detected_output.mp4 saved to Google Drive

* **Frames Processed** : 1,012 frames from surveillance video

---

### **Step 9 : ATM3.ipynb**

* **Purpose** : ATM Frame Classification using ResNet50

* **Framework** : TensorFlow / Keras

* **Backbone** : ResNet50 (pretrained on ImageNet)

* **Input Shape** : 96 x 96 x 3 (RGB frames)

* **Training** : 5 Epochs on 2,350 batches per epoch

**Results:**

* Training Accuracy : 99.88%
* Validation Accuracy : 99.66%
* Test Accuracy : 99.88%
* Test Loss : 0.0018

---

# **HOW TO RUN THE NOTEBOOK VIEWER WEBSITE**

---

### **Files Required**

* FYP.html (main viewer page)
* nb_data.js (embedded notebook data - 13 MB)
* Both files MUST be placed in the same folder

---

### **Steps**

* **Step 1** : Download both FYP.html and nb_data.js

* **Step 2** : Place both files in the same folder on your computer

* **Step 3** : Open VS Code > File > Open Folder > Select that folder

* **Step 4** : Install Live Server extension by Ritwick Dey

  Extensions panel > search "Live Server" > Install

* **Step 5** : Right-click FYP.html in the Explorer panel

* **Step 6** : Select "Open with Live Server"

* **Step 7** : Browser opens at [http://127.0.0.1:5500/FYP.html](http://127.0.0.1:5500/FYP.html)

---

### **Features of the Viewer**

* Browse all 9 notebooks from the sidebar
* Filter by domain: Credit Card / UPI / ATM
* View code cells with syntax highlighting
* View all plot outputs and dataframe tables
* Click any plot to enlarge (lightbox view)
* Copy individual cells or all code at once
* Download any notebook as .ipynb for VS Code

---
.

