# Audio Emotion Classifier

By Xiangzhi Chen (Theon)

---

## Abstract

Speech emotion recognition (SER) remains a challenging problem due to variations in speakers, languages, recording conditions, and dataset-specific biases. So this work presents the design and evaluation of a robust emotion classification system capable of handling diverse, multi-source audio data. A combined dataset of over 10000 audio samples was constructed by integrating 9 publicly available and self-collected datasets, covering 6 emotion categories: anger, disgust, fear, happiness, neutrality, and sadness. All audio samples were preprocessed into fixed-length (8-second) Mel-spectrograms to ensure consistency across sources. The proposed model adopts a hybrid CNN–Transformer architecture. A convolutional backbone, enhanced with ConvNeXt-style blocks, is used to extract spectral features, while a Transformer encoder captures long-range temporal dependencies. An attention-based pooling mechanism is further applied to aggregate temporal information for final classification. The model was trained using stratified splits with label smoothing and evaluated on the test set. The system achieved an overall accuracy of 71.0%, with strong performance on structured datasets such as TESS (100.0%) and RAVDESS Song (92.0%), and relatively balanced results across the two genders. However, performance dropped significantly on more natural, real-world datasets (e.g., Friends and iPartment), highlighting the persistent challenge of cross-domain generalization. These results demonstrate the effectiveness of CNN–Transformer architectures for SER while emphasizing the ongoing challenge of generalization across heterogeneous data sources.

**Final report (PDF):** [./paper.pdf](./paper.pdf)

**Final report (HTML):** [./paper.html](./paper.html)

`Keywords`

- Speech Emotion Recognition
- Multilingual Emotion Classification
- Mel-Spectrogram
- Deep Learning
- Hybrid CNN-Transformer Architecture
- ConvNeXt Blocks
- Convolutional Neural Network
- Transformer Encoder
- Attention Mechanism

## Repository Structure

```
AUDIO-EMOTION-CLASSIFIER/
│
├── data/           # Raw datasets from multiple sources
│ ├── AudioWAV/     # CREMA-D
│ ├── EmoDB/        # Berlin Emotional Speech Dataset
│ ├── EMOVO/        # Italian emotional speech dataset
│ ├── RAV_song/     # RAVDESS song dataset
│ ├── RAVDESS/      # RAVDESS speech dataset
│ ├── reallife/     # Real-world data (e.g., Friends, iPartment)
│ ├── ShEMO/        # Persian emotional speech dataset
│ └── TESS/         # Toronto Emotional Speech Set
│
├── images/         # Figures, diagrams, and visualizations...
├── mel_cache/      # Preprocessed Mel-spectrograms (.npy files)
│
├── best_model.pth  # Trained model weights
│
├── data_loading.ipynb          # Data loading and preprocessing pipeline
├── self_data_processing.ipynb  # Processing for real-world data
├── emotion_classifier.ipynb    # Main model training and evaluation
├── emotion_classifier.html     # Exported notebook (model)
│
├── paper.ipynb     # Notebook version of report
├── paper.pdf       # Final project report
├── paper.html      # HTML version of report
│
├── DSAN6600 Final Pre.pptx     # Presentation slides
├── DSAN6600 Final Pre.pdf      # Presentation PDF
│
├── README.md       # Project documentation
├── references.bib  # Bibliography (for report)
└── .gitignore      # Ignored files

```

## Notes
- The `data/` folder contains multiple datasets used for cross-domain training.
- `mel_cache/` stores precomputed Mel-spectrograms for faster training.
- Notebooks are organized by function: data processing, model training, and reporting.
- Final outputs include the trained model, report, and presentation materials.