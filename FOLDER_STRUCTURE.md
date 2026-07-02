# Code Folder Structure

This document summarizes the repository’s directory layout.

```text
.
├── requirements.txt
├── data/
│   ├── README.md
│   ├── raw/
│   │   ├── train/
│   │   │   ├── jumping/
│   │   │   │   ├── jumping1-<timestamp>/
│   │   │   │   │   ├── Accelerometer.csv
│   │   │   │   │   ├── AccelerometerUncalibrated.csv
│   │   │   │   │   ├── Gyroscope.csv
│   │   │   │   │   ├── GyroscopeUncalibrated.csv
│   │   │   │   │   ├── Annotation.csv
│   │   │   │   │   └── Metadata.csv
│   │   │   │   ├── jumping2-<timestamp>/
│   │   │   │   └── ...
│   │   │   ├── standing/
│   │   │   │   ├── <session>-<timestamp>/
│   │   │   │   └── ...
│   │   │   ├── still/
│   │   │   │   ├── <session>-<timestamp>/
│   │   │   │   └── ...
│   │   │   └── walking/
│   │   │       ├── walking1-<timestamp>/
│   │   │       └── ...
│   │   └── test/
│   │       ├── jumping/
│   │       │   └── test-jumping-<timestamp>/
│   │       ├── standing/
│   │       │   └── test-standing-<timestamp>/
│   │       ├── still/
│   │       │   └── test-still01-<timestamp>/
│   │       └── walking/
│   │           └── test-walking-<timestamp>/
│   └── processed/
├── notebooks/
│   └── HAR_HMM_pipeline.ipynb
└── reports/
```

## Notes

- **`data/raw/`**: Original exported CSV data.
  - Organized by split: `train/` and `test/`.
  - Under `train/`, activities are grouped (e.g., `jumping/`, `standing/`, `still/`, `walking/`).
  - Each session folder is timestamped and typically contains:
    - `Accelerometer.csv`, `AccelerometerUncalibrated.csv`
    - `Gyroscope.csv`, `GyroscopeUncalibrated.csv`
    - `Annotation.csv`
    - `Metadata.csv`
- **`data/processed/`**: Derived features/artifacts produced by the pipeline (currently present as a folder).
- **`notebooks/`**: Jupyter notebooks used for experiments/pipeline development.
- **`reports/`**: Output artifacts (e.g., plots, summaries, exported results).
