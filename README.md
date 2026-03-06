# Project: Luxury BigQuery ML Pipeline
This project is a Dockerized end-to-end data engineering and machine learning solution designed to predict luxury asset prices. It automates the entire lifecycle—from cloud data ingestion to real-time model serving.
# Key Techniques:
- **Data Orchestration:** Authenticates with Google BigQuery via secure Service Accounts to extract luxury sales and pricing data.
- **Dynamic Engineering:** Automatically creates fresh BigQuery datasets for each run, integrating live currency exchange rates (FX) via API.
- **Machine Learning:** Features a dedicated ML pipeline that cleans, normalises, and trains a model to predict market prices based on brand and collection attributes.
- **API & Deployment:** Uses FastAPI to expose the model and processed data through a containerised environment, making it ready for consumption by BI tools like Power BI.
- **Security & DevOps:** Implements industry-standard practices using Docker Compose for environment parity and `.gitignore` protocols for sensitive cloud credentials.

# Repository Structure
```
.
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── .env                 # Local environment variables
├── secrets/             # bq-sa.json (gitignored)
├── models/              # Saved model files
└── src/
    ├── main.py          # FastAPI & Orchestration
    ├── api_app.py       # API End Point Definitions
    ├── api_state.py     # Storing Variables in a Class
    ├── bq/              # BigQuery logic (Client, Query, Upload)
    ├── fx/              # Exchange rate logic
    └── ml/              # Preprocessing & Training
```
