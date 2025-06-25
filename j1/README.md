# Comfortable Weather Predictor & Explorer

This project transforms a raw weather dataset into a full-stack, interactive web application. Users can define their own "comfortable" weather conditions using sliders and instantly see a machine learning model's prediction, along with dynamic charts showing historical trends for their chosen criteria.

![Application Screenshot](https://i.imgur.com/vHqL3hP.png)
*(A screenshot of the final, running application)*

---

## Features

-   **Interactive Controls:** Sliders for temperature, humidity, and wind speed allow users to define custom weather conditions.
-   **Real-Time ML Predictions:** A Scikit-learn (Random Forest) model predicts whether the input conditions are "comfortable" in real-time.
-   **Dynamic Data Visualization:** Charts for seasonal and monthly trends are powered by Chart.js and update instantly based on user input.
-   **Responsive UI:** The interface is built with Tailwind CSS for a seamless experience on both desktop and mobile devices.
-   **Professional Animations:** Subtle animations provide a smooth, modern user experience.
-   **Full-Stack Architecture:** The application is powered by a Flask backend and a vanilla JavaScript frontend.

---

## Tech Stack

-   **Backend:** Python, Flask, Flask-Cors
-   **Machine Learning:** Scikit-learn, Pandas, NumPy
-   **Frontend:** HTML5, CSS3, JavaScript (ES6+)
-   **Styling:** Tailwind CSS
-   **Data Visualization:** Chart.js
-   **Model Persistence:** Joblib

---

## Project Journey & Key Steps

This project evolved through several distinct stages, moving from basic data analysis to a fully interactive web application.

#### 1. Initial Data Analysis
The project began in a Jupyter Notebook (`Untitled.ipynb`) with exploratory data analysis (EDA) on the `weather_dataset.csv`. The primary goal was to understand the data's structure, clean it, and perform an initial analysis to identify "comfortable" days based on a fixed set of rules.

#### 2. Interactive Frontend Prototype
The initial findings were then translated into a single-page interactive HTML dashboard. This version used vanilla JavaScript to allow users to adjust comfort criteria with sliders and see charts update dynamically, all within the browser.

#### 3. Transition to a Full-Stack Application
To make the application more robust and scalable, we moved to a full-stack architecture using Flask. This involved separating the frontend (HTML/CSS/JS) from the backend logic (Python).

#### 4. Machine Learning Model Development
A machine learning model was introduced to replace the simple rule-based filtering.
-   **Model Selection:** A **Random Forest Classifier** was chosen for its robustness and performance.
-   **Training:** The model was trained (`model.py`) on the weather dataset to classify conditions as "comfortable" or "not comfortable."
-   **Evaluation:** The model achieved **100% accuracy** on the test set. (See *A Note on Model Performance* below).
-   **Persistence:** The trained model was saved to a file (`comfortable_weather_model.pkl`) using `joblib`.

#### 5. Backend and Frontend Integration
The Flask application (`app.py`) was developed to:
-   Load the pre-trained model at startup.
-   Serve the `index.html` file.
-   Create API endpoints (`/predict` and `/chart_data`) to handle requests from the frontend, run predictions, perform data analysis, and return results as JSON.

#### 6. Debugging and Refinement
The final stage involved significant debugging, including:
-   **Fixing Server Errors:** Resolving a "white screen" issue caused by a mismatch in the data being sent from the backend and expected by the frontend.
-   **Solving CORS Errors:** Implementing the `Flask-Cors` library to allow the browser to communicate with the local Flask server.
-   **Adding Professional Touches:** Incorporating smooth animations and debounced event handling for a polished user experience.

---

## Final File Structure


/weather-prediction-app
|
|-- app.py                     # Main Flask application
|-- model.py                   # Script to train and save the ML model
|-- comfortable_weather_model.pkl  # The saved, trained model
|-- weather_dataset.csv        # The source dataset
|-- README.md                  # This file
|
|-- templates/
|   |-- index.html           # The HTML frontend


---

## How to Run Locally

Follow these steps to get the application running on your local machine.

#### 1. Clone the Repository
```bash
git clone <your-repository-url>
cd weather-prediction-app

2. Install Dependencies
It's recommended to use a virtual environment.

# Create and activate a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

# Install the required Python libraries
pip install Flask Flask-Cors scikit-learn pandas numpy joblib

3. Train the Model
Run the model training script to generate the .pkl file.

python model.py

4. Run the Flask Application
Start the web server.

flask run

5. View in Browser
Open your web browser and navigate to:
http://127.0.0.1:5000

The application should now be fully functional.

A Note on Model Performance
The model reports a 100% accuracy, which in most machine learning projects is a major red flag for overfitting or data leakage.

In this specific case, it occurs because the features used to train the model (Temp_C, Rel Hum_%, Wind Speed_km/h) are the same ones used to define the target label ("Comfortable"). The model perfectly learns the simple rules embedded in the data. For this project's goal of creating a responsive interface based on these rules, this is acceptable. However, in a real-world predictive scenario,