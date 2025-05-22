# Student Habits & Academic Performance Explorer

This repository contains an end-to-end pipeline that analyzes how student lifestyle habits relate to academic outcomes using real-world data. It includes:

* **Data Ingestion & Cleaning:** Google Colab notebooks to download, clean, and preprocess the dataset.
* **Exploratory Data Analysis & Hypothesis Testing:** Visualizations and statistical tests to uncover relationships.
* **Predictive Modeling:** Train and evaluate regression models (Linear Regression, Random Forest, Gradient Boosting) to predict exam scores.
* **Results Storage:** Persist model metrics and predictions in a PostgreSQL (or Supabase) database.
* **Interactive Dashboard:** A Streamlit application (`app.py`) that:

  * Displays model performance metrics and data distributions.
  * Allows educators or learners to experiment with habit inputs and see predicted exam scores in real time.
  * Shows full predictions vs. actuals and feature correlation insights.

---

## 📁 Repository Structure

```
├── notebooks/                # Colab notebooks for each phase
│   ├── 01_data_ingestion.ipynb
│   ├── 02_EDA_and_hypothesis.ipynb
│   ├── 03_model_training.ipynb
│   └── 04_db_upload.ipynb
├── app.py                    # Streamlit dashboard script
├── requirements.txt          # Python dependencies
├── .streamlit/               # Streamlit secrets and config
│   └── secrets.toml
└── README.md                 # Project overview and instructions
```

---

## 🚀 Getting Started

### 1. Prerequisites

* Python 3.8+
* PostgreSQL database (local or hosted via Supabase)
* Git & GitHub account
* [Streamlit Cloud](https://streamlit.io/cloud) account (optional for hosted demo)

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Prepare the Database

1. Create a PostgreSQL database, e.g., `education_db`.
2. In your `.streamlit/secrets.toml`, add:

   ```toml
   DB_USER = "<your_db_user>"
   DB_PASSWORD = "<your_db_pass>"
   DB_HOST = "<your_db_host>"
   DB_PORT = "5432"
   DB_NAME = "education_db"
   ```
3. Run the Colab notebook `04_db_upload.ipynb` (or local script) to upload cleaned data, model metrics, and predictions to your database.

### 4. Run the Dashboard Locally

```bash
streamlit run app.py
```

### 5. Deploy to Streamlit Cloud (Optional)

1. Push this repo to GitHub.
2. On [Streamlit Cloud](https://share.streamlit.io), link your GitHub repo.
3. In Streamlit deployment settings, add the same secrets from your local `secrets.toml`.
4. Deploy and share your interactive dashboard!

---

## 📊 Project Highlights

* **Strong Model Performance:** Linear Regression achieved R² ≈ 0.90, RMSE ≈ 5.15.
* **Key Findings:** Study hours per day and mental health rating positively correlate with exam scores.
* **Dynamic Predictions:** Real-time sliders in the dashboard let users simulate how changing habits impacts predicted outcomes.

---

## 🤝 Contributing

Feel free to open issues or submit pull requests for:

* Adding more features (e.g., social media usage impact).
* Improving model accuracy with advanced architectures.
* Enhancing dashboard UI/UX.

---

## 📝 License

MIT License © \Nsikak Menim
