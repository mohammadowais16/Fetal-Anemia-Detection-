# GeoProteoNet — Fetal Anemia Detection

GeoProteoNet is a student project exploring how Doppler ultrasound images and machine learning can support research into fetal anemia assessment. It combines image segmentation, hemodynamic feature extraction, and a web dashboard for reviewing analysis results.

> Final-year B.E. major project at MJCET (2026), supervised by Ms. Nabeela Fatima.

**Important:** This is an academic prototype, not a medical device. It must not be used to diagnose, treat, or make clinical decisions. The reported model metrics describe the project's evaluation setup and are not evidence of clinical validation.

## How it works

1. **Image segmentation** — a CNN encoder-decoder identifies relevant structures in Doppler ultrasound images.
2. **Feature extraction** — the pipeline derives hemodynamic features such as PSV, EDV, RI, PI, and S/D ratio.
3. **Risk classification** — a Random Forest model uses extracted features to produce a model prediction.
4. **Results dashboard** — a React interface displays analysis results, visualizations, history, and PDF exports.

## Architecture

![System Architecture](./architecture.png)

| Component | Role |
| --- | --- |
| Frontend | React, Vite, Tailwind CSS, Recharts, and PDF report export |
| Backend | FastAPI endpoints and image preprocessing |
| ML pipeline | CNN-based segmentation, feature extraction, and Random Forest classification |
| Data layer | Patient records, scan history, and generated reports |

## Reported model metrics

The project README reports the following metrics on a held-out split of its labeled ultrasound dataset:

- **Segmentation:** 93.99% Dice coefficient
- **Classification:** 92.90% F1-score

These are project-reported experimental results. They should be interpreted in the context of the dataset, split, and evaluation procedure; they do not establish real-world clinical performance.

## Technology

- **Frontend:** React, Vite, Tailwind CSS, Recharts, Lucide React
- **Backend:** Python, FastAPI, Uvicorn
- **Machine learning / computer vision:** TensorFlow/Keras, OpenCV, scikit-learn
- **Infrastructure:** Docker, GitHub Actions, AWS
- **Reporting:** jsPDF, html2canvas

## Project structure

```text
├── backend/            # FastAPI app, inference, and database access
├── frontend/           # React + Vite dashboard
├── notebooks/          # Model development and training notebooks
├── .github/workflows/  # CI workflows
└── docker/             # Containerization configuration
```

## Run locally

Run the backend and frontend in separate terminals.

### Backend

```bash
cd backend
pip install -r requirements.txt
python main.py
```

The backend runs on `http://localhost:8000`.

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.

The exact setup may depend on the available model files, dataset, and local configuration. If the full dataset is unavailable, the repository's lightweight development path may help test the application flow; it should not be confused with a validated trained model.

## Team

- Shaikh Mazein Ahmed
- Mohammad Owais
- Shaik Syed

Supervised by Ms. Nabeela Fatima, Department of Computer Science and Engineering, MJCET.

## License

MIT — see [LICENSE](./LICENSE).
