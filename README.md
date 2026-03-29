# Flight Fare Prediction

An end-to-end machine learning project that predicts flight ticket prices based on travel parameters. Built with a modular MLOps architecture covering data ingestion, transformation, model training, and evaluation — with MLflow experiment tracking and a Flask web interface for live predictions.

## Features

- Modular pipeline: data ingestion → transformation → training → evaluation
- Multiple regression models evaluated and compared
- MLflow integration for experiment tracking and model registry
- DVC for pipeline versioning and reproducibility
- Flask web UI for real-time fare predictions
- Dockerized for easy deployment

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| Scikit-learn | Regression models & preprocessing |
| Pandas / NumPy | Data manipulation |
| MLflow | Experiment tracking & model registry |
| DVC | Pipeline & data versioning |
| Flask | Web application & prediction API |
| Docker | Containerization |

## Project Structure

```
flight-fare-prediction/
├── src/FlightPricePrediction/
│   ├── components/         # Data ingestion, transformation, training, evaluation
│   ├── pipelines/          # Training & prediction pipelines
│   ├── utils/              # Shared utility functions
│   ├── exception.py        # Custom exception handling
│   └── logger.py           # Logging setup
├── Artifacts/              # Generated model & data artifacts
├── mlruns/                 # MLflow experiment logs
├── Notebook_Experiments/   # EDA & training notebooks
├── app.py                  # Flask web application
├── setup.py                # Package setup
├── dvc.yaml                # DVC pipeline stages
├── Dockerfile              # Docker image definition
└── requirements.txt        # Python dependencies
```

## Getting Started

### Prerequisites

- Python 3.8+
- Docker (optional)

### Installation

```bash
git clone https://github.com/smunir25/general-ai-flight-fare-prediction.git
cd general-ai-flight-fare-prediction
pip install -r requirements.txt
```

### Run Training Pipeline

```bash
python src/FlightPricePrediction/pipelines/Training_pipeline.py
```

Or using DVC:

```bash
dvc repro
```

### Run the Web App

```bash
python app.py
```

Visit `http://localhost:5000` and enter flight details to get a predicted fare.

### Docker

```bash
docker build -t flight-fare-prediction .
docker run -p 5000:5000 flight-fare-prediction
```

## Input Features

| Feature | Description |
|---------|-------------|
| Airline | Name of the airline carrier |
| Date of Journey | Travel date |
| Source | Departure city |
| Destination | Arrival city |
| Route | Flight route |
| Dep Time | Departure time |
| Arrival Time | Arrival time |
| Duration | Total flight duration |
| Total Stops | Number of stops (non-stop, 1 stop, etc.) |
| Additional Info | Extra details (meal, baggage, etc.) |

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
