# Hotel Cancellation Detection System

## 1. Description
This project is a complete Machine Learning application designed to predict whether a hotel booking will be cancelled. It implements a robust MLOps pipeline that handles data ingestion, preprocessing, model training, and evaluation using **LightGBM**. The trained model is served via a **Flask** web application, allowing users to input booking details and receive real-time cancellation predictions.

The system integrates **MLflow** for experiment tracking and is containerized using **Docker** for consistent deployment.

## 2. Features
* **Automated Training Pipeline:** End-to-end pipeline script handling data ingestion, transformation, and model training.
* **Advanced Modeling:** Utilizes the **LightGBM** classifier optimized via `RandomizedSearchCV` for high performance.
* **MLOps Integration:** Uses **MLflow** to log experiments, metrics (Accuracy, Precision, Recall, F1), and model artifacts.
* **Web Interface:** A user-friendly **Flask** web app to interact with the model and generate predictions based on user input.
* **Containerization:** Fully Dockerized application for easy reproducibility and deployment.
* **Scalable Architecture:** Modular code structure separating configuration, ingestion, processing, and training logic.

## 3. Installation

### Prerequisites
* Python 3.8+
* Docker (optional, for containerized run)

### Local Setup
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/hotel_cancel_detection-application.git](https://github.com/your-username/hotel_cancel_detection-application.git)
    cd hotel_cancel_detection-application
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    # Or install in editable mode
    pip install -e .
    ```

## 4. Usage

### Running the Training Pipeline
To process the raw data and train a new model:
```bash
python pipeline/training_pipeline.py
````

This will generate processed datasets and save the trained model artifact (e.g., `lgbm_pickle.pkl`).

### Running the Web Application

Start the Flask server to serve predictions:

```bash
python app.py
```

The application will launch on `http://localhost:8080`.

### Running with Docker

1.  **Build the Docker image:**

    ```bash
    docker build -t hotel-cancel-app .
    ```

    *Note: The Docker build process automatically triggers the training pipeline.*

2.  **Run the container:**

    ```bash
    docker run -p 8080:8080 hotel-cancel-app
    ```

## 5\. Project Structure

```
├── artifacts/          # Stores models and data (generated)
├── config/             # Configuration files (params, paths)
├── pipeline/           # Pipeline scripts (training_pipeline.py)
├── src/                # Source code (ingestion, processing, training)
├── static/             # CSS and assets for Flask
├── templates/          # HTML templates for Flask
├── app.py              # Flask application entry point
├── Dockerfile          # Docker configuration
└── requirements.txt    # Python dependencies
```

## 6\. Contributing

Contributions are welcome\! Please follow these steps:

1.  Fork the repository.
2.  Create a new feature branch (`git checkout -b feature/YourFeature`).
3.  Commit your changes (`git commit -m 'Add some feature'`).
4.  Push to the branch (`git push origin feature/YourFeature`).
5.  Open a Pull Request.

## 7\. License

This project is open-source and available under the [MIT License](https://opensource.org/licenses/MIT).

## 8\. Contact

For any questions or support, please open an issue in this repository or contact the maintainer.
