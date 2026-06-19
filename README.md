# hybrid-ai-quantum-galaxy-retrieval

# Hybrid AI–Quantum Galaxy Retrieval

This repository contains the code and validation outputs for a hybrid AI–quantum prototype for galaxy morphology catalog retrieval.

The system:
1. Loads labeled Galaxy10 SDSS galaxy images.
2. Uses a DenseNet121-based CNN classifier to predict galaxy morphology.
3. Maps Galaxy10 labels into simplified project classes: Elliptical, Lenticular, and Spiral.
4. Assigns binary morphology tags.
5. Stores galaxies in a row-numbered catalog.
6. Uses simulated Grover search to retrieve catalog rows matching a requested galaxy type.
7. Evaluates AI classification, Grover retrieval, and end-to-end system performance.

## Main files

- `qasc_galaxy_hybrid_publication_clean.ipynb`: Notebook version of the full implementation.
- `qasc_galaxy_hybrid_publication_clean.py`: Python script version of the implementation.
- `classified_galaxy_catalog.csv`: AI-tagged validation catalog.
- `ai_classification_report.csv`: AI precision, recall, and F1 metrics.
- `ai_confusion_matrix.csv`: AI confusion matrix.
- `grover_validation_trials.csv`: Trial-by-trial Grover retrieval results.
- `grover_validation_summary.csv`: Summary of Grover retrieval performance.
- `end_to_end_validation_trials.csv`: Trial-by-trial full-system results.
- `end_to_end_validation_summary.csv`: Summary of end-to-end validation.

## Dataset

This project uses the Galaxy10 SDSS dataset through the public `astroNN` dataset interface. The full image dataset is not redistributed in this repository.

## Main results

- AI classification accuracy: 82.22%
- Macro F1-score: 0.82
- Grover success probability: 0.933–0.957
- Amplification factor: 2.84×–5.20×
- End-to-end predicted-tag success: 1.00 for all tested classes

## Important limitation

A single Grover measurement returns one sampled catalog row, not every matching galaxy. To retrieve many examples from a class, the search must be repeated and duplicate results filtered.

## Requirements

Install the required packages with:

```bash
pip install -r requirements.txt
