# Drift Detection in Student Written Answers using BERT Embeddings

This project presents a drift-aware automated grading framework designed to detect semantic changes in student-written answers and maintain grading performance over time.

The system combines transformer-based semantic embeddings, statistical drift detection, and adaptive retraining to address the problem of concept drift in educational AI systems.

Traditional automated grading systems assume that student answer distributions remain stable after deployment. In real-world educational environments, however, writing styles, curriculum structure, vocabulary usage, conceptual explanations, and AI-assisted writing patterns continuously evolve. These changes can degrade the performance of static machine learning models over time.

This project investigates how semantic drift in student-written answers can be detected using BERT embeddings and statistical divergence measures such as Jensen-Shannon divergence. When significant drift is detected, the grading model is automatically retrained using updated data to restore performance and maintain reliability.

---

## Project Overview

The proposed framework integrates:

- Semantic embedding generation using BERT
- Automated grading using Random Forest Regression
- Statistical drift detection
- Adaptive retraining
- Performance monitoring and evaluation

The system is designed as a proof-of-concept framework for building robust and adaptive AI-based educational assessment systems.

---

## Problem Statement

Automated grading systems deployed in educational environments often experience performance degradation over time due to evolving student response patterns.

Changes in:
- curriculum,
- teaching methodologies,
- writing styles,
- vocabulary usage,
- AI-assisted writing tools,
- and student demographics

can alter the semantic distribution of student answers.

This phenomenon is known as concept drift.

Without drift detection and adaptation mechanisms, grading systems may become unreliable, inconsistent, and unfair over long-term deployment.

This project addresses that challenge by building a drift-aware grading pipeline capable of continuously monitoring embedding distributions and retraining the model when significant semantic drift is detected.

---

## Methodology

The pipeline follows these stages:

1. Student answers are converted into semantic embeddings using BERT.
2. The embeddings are used to train a Random Forest Regressor for score prediction.
3. New incoming answers are monitored for distributional changes.
4. Jensen-Shannon divergence is computed between historical and incoming embedding distributions.
5. If the drift threshold is exceeded, retraining is triggered automatically.
6. Model performance is re-evaluated after adaptation.

---

## Tech Stack

### Languages and Frameworks
- Python
- Google Colab

### Machine Learning and NLP
- BERT
- Transformers
- PyTorch
- Random Forest Regressor

### Libraries
- NumPy
- Pandas
- Scikit-learn
- SciPy
- Matplotlib

---

## Repository Structure

```bash
drift-detection-student-answers/
│
├── notebooks/
│   └── drift_detection_pipeline.py
│
├── reports/
│   ├── final_report.pdf
│   └── synopsis.pdf
│
├── figures/
│
├── results/
│
├── README.md
├── LICENSE
├── requirements.txt
└── .gitignore
```

---

## Dataset

The project uses a custom synthetic dataset containing undergraduate-level student answers from domains such as:

- Operating Systems
- DBMS
- Computer Networks
- Machine Learning
- Artificial Intelligence
- Software Engineering

Each answer is associated with manually assigned scores to simulate human grading.

The dataset was intentionally designed with semantic variations and writing diversity to study drift behavior.

---

## Drift Detection

The project uses Jensen-Shannon divergence to measure distributional differences between historical embeddings and incoming student responses.

If the computed drift score exceeds the predefined threshold:

```python
if drift_score > 0.1:
```

the model is retrained using both historical and incoming drifted data.

---

## Evaluation Metrics

The framework evaluates performance using:

- Accuracy
- F1 Score
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)

---

## Results

The experiments demonstrate that concept drift significantly affects grading consistency and prediction quality.

### Before Retraining
- Accuracy: 0.60
- F1 Score: 0.52
- MAE: 0.4560
- MSE: 0.3036

### After Retraining

The adaptive retraining mechanism significantly improved model performance on the incoming drifted samples.

Observed evaluation metrics on the controlled experimental dataset:

- Accuracy: 1.00
- F1 Score: 1.00
- MAE: 0.16
- MSE: 0.0374

Since the dataset used in this project is relatively small and synthetic, these results should be interpreted as proof-of-concept behavior rather than evidence of perfect real-world generalization.

---

## Key Contributions

This project contributes:

- A drift-aware educational NLP framework
- Integration of semantic embeddings with statistical drift detection
- Adaptive retraining for grading stability
- Automated monitoring of embedding distribution changes
- A proof-of-concept framework for robust AI-based educational assessment systems

---

## Limitations

Current limitations include:

- Small synthetic dataset
- Limited real-world answer diversity
- Simplified retraining strategy
- No deployment pipeline
- No streaming data infrastructure

The project is positioned as a proof-of-concept research framework.

---

## Future Improvements

Potential future enhancements include:

- Fine-tuning BERT instead of feature extraction
- Real-world educational datasets
- Streaming drift detection
- Incremental learning
- Transformer-based grading architectures
- Adaptive window-based monitoring
- Real-time educational deployment

---

## Academic Context

This project was completed as part of a B.Tech Computer Science Engineering (Artificial Intelligence and Machine Learning) mini-project at Manipal University Jaipur.

---

## References

The implementation and methodology are based on research in:
- automated essay scoring,
- concept drift detection,
- transformer-based NLP,
- educational AI systems,
- adaptive machine learning.

Detailed references are included in the project report.

---

## License

This project is licensed under the MIT License.

---

## Author

Sheenjani Das  
Department of Artificial Intelligence and Machine Learning  
Manipal University Jaipur
