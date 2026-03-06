# 📘 Assignment: Reddit Post Classification Dashboard

## 🎯 Objective

Design and develop a **Frontend Dashboard** for a Machine Learning project titled:

> **“Reddit Post Classification Dashboard”**
> Model: **TF-IDF + Multinomial Naive Bayes**

The dashboard must connect to a Flask REST API backend and dynamically display model results and predictions.

---

# 🧠 Background

The backend model performs:

* Text preprocessing using NLTK
* TF-IDF feature extraction
* Multinomial Naive Bayes classification
* Train-Test split (80/20)
* Evaluation using:

  * Accuracy
  * Confusion Matrix
  * Classification Report
* Live prediction of new Reddit posts

---

# 🏗️ Technology Stack (Frontend)

You must use:

* HTML5
* Bootstrap 5
* DC.js
* D3.js
* Crossfilter2
* External JavaScript file (`app.js`)
* Fetch API for backend communication

❌ Do NOT use Chart.js
❌ Do NOT write backend code

---

# 📊 Dashboard Layout Structure

Your dashboard must follow the structure below:

```
---------------------------------------------------------
| Reddit Post Classification Dashboard                  |
---------------------------------------------------------
| KPI Cards (4 Cards in One Row)                        |
---------------------------------------------------------
| Live Prediction Section                               |
---------------------------------------------------------
| Confusion Matrix | Class Distribution Chart           |
---------------------------------------------------------
| Classification Report Table                           |
---------------------------------------------------------
| Top Keywords Visualization                            |
---------------------------------------------------------
| Footer (Model Details)                                |
---------------------------------------------------------
```

---

# 🧩 Section-wise Requirements

---

## 🔹 1. Header Section

Include:

* Dashboard Title
* Subtitle:

  > Text Classification using TF-IDF + Multinomial Naive Bayes
* Model badge (top right corner)

---

## 🔹 2. KPI Cards Section

Create 4 Bootstrap cards in a single row:

| Card               | Data Source           |
| ------------------ | --------------------- |
| Accuracy           | `/api/model/overview` |
| Total Test Samples | `/api/model/overview` |
| Number of Classes  | `/api/model/overview` |
| Model Name         | `/api/model/overview` |

All values must be loaded dynamically from the API.

---

## 🔹 3. Live Prediction Section

Create:

* Large Textarea (Title + Content combined)
* Predict Button
* Result Display Area

When user clicks **Predict**:

Call:

```
POST /api/predict
```

Display:

* Predicted Category
* Confidence Score
* Probability per class

Include:

* Loading spinner
* Error handling

---

## 🔹 4. Confusion Matrix (DC.js Chart)

Call:

```
GET /api/model/confusion-matrix
```

Requirements:

* Heatmap-style visualization using DC.js
* X-axis → Predicted
* Y-axis → Actual
* Display counts inside cells
* Responsive design

---

## 🔹 5. Class Distribution Chart

Call:

```
GET /api/data/class-distribution
```

Requirements:

* Bar chart using DC.js
* Show:

  * Class name
  * Number of samples
* Must be interactive

---

## 🔹 6. Classification Report Table

Call:

```
GET /api/model/classification-report
```

Display:

| Class | Precision | Recall | F1-Score | Support |

Also include:

* Accuracy row
* Macro average
* Weighted average

Table must be dynamically rendered using JavaScript.

---

## 🔹 7. Top Keywords Visualization

Call:

```
GET /api/model/top-keywords
```

Display:

* Horizontal bar chart per class
* Show top TF-IDF words
* Use DC.js row chart

---

## 🔹 8. Footer Section

Display:

* Model Name
* Feature Extraction Method (TF-IDF)
* NLP Preprocessing (Lowercase, Stopwords, Stemming)
* Train/Test Split (80/20)
* Year

---

# 🔌 API Endpoints Available

The backend provides the following endpoints:

```
GET  /api/model/overview
GET  /api/model/confusion-matrix
GET  /api/model/classification-report
GET  /api/data/class-distribution
GET  /api/model/top-keywords
POST /api/predict
```

You must use `fetch()` to connect to these endpoints.

---

# 📁 Required Folder Structure

```
reddit-dashboard/
│
├── index.html
├── app.js
├── css/
│   └── styles.css (optional)
└── assets/
```

JavaScript must be written in `app.js`.

Do NOT write JS inside HTML except for script imports.

---

# ⚙️ Functional Requirements

Your dashboard must:

* Be fully responsive
* Use Bootstrap grid system
* Load all data dynamically
* Show loading indicators during API calls
* Handle API errors properly
* Keep code clean and modular
* Use DOMContentLoaded event listener

---

# 📌 Additional Requirements

* Clean modern UI
* Proper spacing
* Card-based layout
* Clearly labeled charts
* Maintain consistent theme

---

# 🧪 Evaluation Criteria

| Criteria                    | Marks |
| --------------------------- | ----- |
| Layout & Design             | 20    |
| API Integration             | 20    |
| DC.js Chart Implementation  | 20    |
| Live Prediction Feature     | 15    |
| Code Structure & Separation | 15    |
| Responsiveness & UI Quality | 10    |

Total: **100 Marks**

---

# 📦 Submission Requirements

Students must submit:

1. Complete project folder
2. Screenshots of:

   * Dashboard
   * Prediction working
   * Charts working
3. Short explanation document (2–3 pages) explaining:

   * How DC.js works with Crossfilter
   * How data flows from Flask API to frontend
   * Challenges faced

---

# 🚀 Bonus (Optional – Extra Credit)

* Add filtering support in DC.js charts
* Add reset filter button
* Add misclassified samples table
* Add confidence progress bar
* Add dark mode toggle

---

# 🏁 Expected Learning Outcomes

After completing this assignment, students will understand:

* How to connect ML models with frontend dashboards
* REST API integration
* DC.js and Crossfilter usage
* Dynamic UI rendering
* NLP model visualization

---

**Instructor Note:**
Backend API will be provided separately. Students must only focus on frontend dashboard implementation.

---

# ✅ End of Assignment
