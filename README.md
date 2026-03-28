
---

# 📊 Reddit Post Classification Dashboard – Simple 6 Steps Guide

---

## ✅ Step 1: Understand File Structure (Diagram + Purpose)

### 📁 Project Structure

```id="9e8c7p"
reddit-dashboard/
│
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── dashboard.js
│
├── models/
│       model.pkl
│
├── training/
│       train_model.py
│       notebook.ipynb
│
└── app.py
```

### 📌 Purpose of Each File

| File/Folder        | Purpose                              |
| ------------------ | ------------------------------------ |
| **index.html**     | Main dashboard UI                    |
| **styles.css**     | Styling and layout                   |
| **dashboard.js**   | Handles API calls and UI updates     |
| **models/**        | Stores trained ML model              |
| **train_model.py** | Converts notebook into trained model |
| **notebook.ipynb** | Used for NLP model training          |
| **app.py**         | Backend API server                   |

---

## ✅ Step 2: Design Dashboard (index.html Structure)

Use:

* Bootstrap 5
* DC.js
* Crossfilter2
* D3.js

### 📊 Dashboard Layout Diagram

```id="qv5m2n"
---------------------------------------------------------
📊 Reddit Post Classification Dashboard
---------------------------------------------------------
Header:
- Title + Subtitle + Model Info
---------------------------------------------------------
KPI Cards Row:
[ Accuracy ] [ Total Samples ] [ Classes ] [ Model Name ]
---------------------------------------------------------
Prediction Section:
[ Text Input Area ]
[ Predict Button ]
[ Result Display ]
---------------------------------------------------------
Charts Row:
[ Confusion Matrix ] [ Class Distribution ]
---------------------------------------------------------
Table Section:
[ Classification Report Table ]
---------------------------------------------------------
Visualization Section:
[ Top Keywords Chart ]
---------------------------------------------------------
Footer:
[ Model Details ]
---------------------------------------------------------
```

### 🎯 Goal

* Create responsive dashboard using Bootstrap
* Allocate sections for charts (DC.js)
* Maintain clean UI layout

---

## ✅ Step 3: Create Model Training Script

### 📌 Task

Create **train_model.py** using the `.ipynb` file.

### 🎯 Purpose

* Perform text preprocessing (NLP steps)
* Apply TF-IDF feature extraction
* Train classification model (Naive Bayes)
* Evaluate performance

---

## ✅ Step 4: Generate and Save Model

### 📌 Task

Run the training script.

### 🎯 Output

* Save trained model into:

```id="k3x8pw"
/models/model.pkl
```

* This model will be used by backend APIs

---

## ✅ Step 5: Create Backend API (app.py)

### 📌 API Design (Names, Routes, Purpose)

| API Name              | Route                              | Purpose                    |
| --------------------- | ---------------------------------- | -------------------------- |
| Model Overview        | `/api/model/overview`              | Accuracy, samples, classes |
| Confusion Matrix      | `/api/model/confusion-matrix`      | Matrix data                |
| Classification Report | `/api/model/classification-report` | Performance metrics        |
| Class Distribution    | `/api/data/class-distribution`     | Class counts               |
| Top Keywords          | `/api/model/top-keywords`          | Important words per class  |
| Prediction            | `/api/predict`                     | Predict category of text   |

### 🎯 Goal

* Connect frontend dashboard with NLP model
* Return structured JSON responses

---

## ✅ Step 6: Create dashboard.js (Frontend Logic)

### 📌 Responsibilities

dashboard.js connects **index.html ↔ app.py**

### 🔧 Tasks

1. On Page Load

   * Fetch model overview
   * Load charts
   * Load classification report

2. Prediction Handling

   * Take user input text
   * Send request to prediction API
   * Display predicted category and confidence

3. Display Data

   * Update KPI cards
   * Render table data
   * Show results

4. Chart Rendering

   * Confusion Matrix
   * Class Distribution
   * Top Keywords

5. Handle

   * Loading indicators
   * Error messages
   * Dynamic updates

---

## 🎯 Final Flow

```id="v2zq1r"
User → index.html (Dashboard UI)
        ↓
dashboard.js (Frontend Logic)
        ↓
app.py (Backend API)
        ↓
ML Model (Prediction)
        ↓
Response → Dashboard Visualization
```

---

