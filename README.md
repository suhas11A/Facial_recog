# Facial\_recog

A Python-based face recognition system that detects and identifies faces in images and live video streams. This repository contains the source code, pre-trained models, and sample media for demonstration.

## Repository Structure

```
Facial_recog/
├── data/                     # Sample images and face datasets
│   ├── known_faces/          # Labeled images of known individuals
│   └── unknown/              # Test images for recognition
├── models/                   # Pre-trained face encoding models
├── src/                      # Source code
│   ├── capture.py            # Capture and process video stream
│   ├── detect.py             # Face detection scripts
│   ├── encode_faces.py       # Generate face encodings from images
│   └── recognize.py          # Perform face recognition on inputs
├── utils/                    # Utility modules (e.g., image preprocessing)
├── requirements.txt          # Python package dependencies
├── .gitignore                # Files and directories to ignore in version control
└── README.md                 # This file
```

## Features

* Detect faces in images and video streams using OpenCV.
* Encode faces into numerical feature vectors.
* Compare face encodings to identify known individuals.
* Real-time recognition via webcam or video file.

## Prerequisites

* Python 3.7 or higher
* Virtual environment (recommended)
* Libraries:

  * `face_recognition`
  * `opencv-python`
  * `numpy`

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/suhas11A/Facial_recog.git
   cd Facial_recog
   ```
2. **Create and activate a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```
3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Prepare Known Faces:**

   * Place labeled face images in `data/known_faces/`, one subfolder per person.
2. **Encode Faces:**

   ```bash
   python src/encode_faces.py --input data/known_faces --output models/encodings.pickle
   ```
3. **Run Recognition:**

   * **Image Recognition:**

     ```bash
     python src/recognize.py --encodings models/encodings.pickle --image data/unknown/test1.jpg
     ```
   * **Real-time Video:**

     ```bash
     python src/capture.py --encodings models/encodings.pickle
     ```

## Scripts Overview

* **`encode_faces.py`**: Scans known\_faces directory, extracts face encodings, and serializes to a pickle file.
* **`detect.py`**: Demonstrates basic face detection on images.
* **`recognize.py`**: Loads encodings and performs recognition on images.
* **`capture.py`**: Captures webcam feed, detects and recognizes faces in real time.

## Configuration Options

* `--detection-method`: Choose between `hog` and `cnn` for face detection (default: `hog`).
* `--output-video`: Save processed video stream to file.
* Other flags available; run `python src/recognize.py --help` for details.

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add feature'`)
4. Push to your branch (`git push origin feature/my-feature`)
5. Open a pull request

## Contact

For questions or support, open an issue or contact the maintainer.
