
# AI Predictive Model for Credit Underwriting

## Introduction
The **AI Predictive Model for Credit Underwriting** is a comprehensive application designed to predict loan eligibility and assist users in understanding the loan application process. It provides two interfaces:

1. A Flask-based backend for API-based predictions and an AI-powered chatbot.
2. A Streamlit-based web app for interactive user input and prediction display.
  

---

## Features

### Flask Application
1. **Loan Eligibility Prediction API**:
   - Provides a `/predict` endpoint for predictions based on user data.
2. **AI-Powered Chatbot**:
   - Answers loan-related queries and explains prediction results.

### Streamlit Application
1. **User-Friendly Form**:
   - Sidebar input fields for loan applicant data.
2. **Real-Time Predictions**:
   - Displays loan eligibility instantly.
3. **Data Storage**:
   - Saves submitted data in a JSON file for future reference.

### Jupyter Notebook
1. **Model Training**:
   - `SB_Trained_Model.ipynb` contains the complete workflow for data preprocessing, model training, and evaluation.
2. **Visualization**:
   - Includes exploratory data analysis (EDA) and model performance metrics.
3. **Pipeline Export**:
   - Exports the trained model as `final_best_model.pkl` for integration with Flask and Streamlit applications.

---

## Technologies Used

### Backend
- **Flask**: For creating the REST API and chatbot functionality.
- **Streamlit**: For building an interactive web interface.
- **Python**: For application logic and machine learning integration.
- **Joblib**: To load the trained ML model pipeline.

### Machine Learning
- **Pre-trained Pipeline**: A machine learning model trained on credit underwriting data.

### API Integration
- **Grok LLM API**: For AI-driven conversation and guidance.

### Frontend
- **HTML**: Used for the Flask-based interface.
- **Streamlit Components**: For the interactive web app.

---

## Installation

### Prerequisites
1. Python 3.8+
2. Virtual environment tools (optional but recommended)

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/ShriyamTiwari/Credit-Underwriting.git
   cd credit_underwriting
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up the ML model:
   - Place the trained ML model (`final_best_model.pkl`) in the project directory.
   - Update the `model_path` variable in both `app.py` and `loan_app.py` if necessary.

4. Set up Grok API:
   - Replace the `GROK_API_KEY` in `app.py` with your valid API key.

5. Run the Flask application:
   ```bash
   python app.py
   ```
   Access the flask interface at `http://127.0.0.1:5000/chat-interface`.

6. Run the Streamlit application:
   ```bash
   streamlit run loan_app.py
   ```
   Access the Streamlit app at the URL displayed in the terminal (e.g., `http://127.0.0.1:8501`).

7. Explore the Jupyter notebook:
   Open `SB_Trained_Model.ipynb` using Jupyter Notebook or Jupyter Lab to review the model training and evaluation process.

---

## Usage

- **Flask API**:  Navigate to `http://localhost:5000/predict` in your browser to input loan details and receive predictions or use Postman.
- **Streamlit App**: Navigate to `http://localhost:8501` in your browser to input loan details and receive predictions.


### Flask Interface
1. Visit the flask interface at `/predict`.
2. Enter your data and app will show you the predictions.
3. For loan predictions, provide details like age, income, and credit history.

### API Endpoint
- **Endpoint**: `/predict`
- **Method**: `POST` `GET`
- **Payload** (example):

```json
{
  "person_age": 35,
  "person_income": 60000,
  "person_home_ownership": "OWN",
  "person_emp_length": 5,
  "loan_intent": "PERSONAL",
  "loan_grade": "B",
  "loan_amnt": 15000,
  "loan_int_rate": 12.5,
  "loan_percent_income": 0.25,
  "cb_person_default_on_file": "N",
  "cb_person_cred_hist_length": 8
}
```

- **Response** (example):

```json
{
  "predition": "Loan Approved!",
  "Input Data": {
    "person_age": 35,
    "person_income": 60000,
    "person_home_ownership": "OWN",
    "person_emp_length": 5,
    "loan_intent": "PERSONAL",
    "loan_grade": "B",
    "loan_amnt": 15000,
    "loan_int_rate": 12.5,
    "loan_percent_income": 0.25,
    "cb_person_default_on_file": "N",
    "cb_person_cred_hist_length": 8
  }
}
```

### Streamlit App
1. Enter applicant details in the sidebar form (age, income, loan details, etc.).
2. Click **Submit** to view the prediction results.
3. The application displays:
   - Submitted details in JSON format.
   - Prediction result (Approved or Denied).
   - Explanation for the decision.

### Jupyter Notebook
1. Open the `SB_Trained_Model.ipynb` notebook in Jupyter.
2. Explore the following sections:
   - Data Preprocessing: Handling missing values, encoding, and scaling.
   - Model Training: Training multiple models and selecting the best one.
   - Model Evaluation: Metrics like accuracy, precision, recall, and F1 score.
3. Modify the notebook to retrain the model with updated data if required.

---

## Project Structure

```
├── app.py                     # Flask application for API
├── loan_app.py                # Streamlit application for user input and predictions
├── SB_Trained_Model.ipynb     # Jupyter notebook for model training and evaluation
├── final_best_model.pkl       # Pre-trained ML pipeline
├── requirements.txt           # Python dependencies
├── templates/
│   ├── chat.html              # Frontend for chat interface
│   └── index.html             # Frontend for flask app
├── static/                    # Static assets (if any)
├── README.md                  # Project documentation
```
**Here is the link to download the model:-** (https://drive.google.com/file/d/1J-j46fx2a8AB0NXEbDknYcPYurIXETmB/view?usp=sharing)

---

## Future Improvements
1. Integrate multi-language support for a broader audience.
2. Automate the retraining process using the Jupyter notebook.

---

## Contributing
Contributions are welcome! Feel free to fork this repository, submit pull requests, or open issues for suggestions and improvements.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Acknowledgments
- The dataset used to train the model was sourced from Kaggle.
