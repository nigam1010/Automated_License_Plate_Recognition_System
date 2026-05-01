# License Plate Recognition Project

A computer vision project for automatic license plate detection and OCR using YOLO and Tesseract.

## Overview

This project uses:
- **YOLOv8** for license plate detection
- **Tesseract OCR** for text extraction from detected plates
- **OpenCV** for image processing
- **cvzone** for visualization

## Project Structure

```
├── main1.py                 # Main script for plate detection and OCR
├── img.py                   # Extract frames from video
├── imgdeleteyolo.py        # Utility to clean up unmatched images
├── best.pt                 # Pre-trained YOLOv8 model
├── image/                  # Extracted frames and annotations
├── fdt/                    # Training data directory
├── car_plate_data.txt      # Output: detected plates with timestamps
└── requirements.txt        # Python dependencies
```

## Prerequisites

### System Requirements
- **Tesseract-OCR**: Install from https://github.com/UB-Mannheim/tesseract/wiki
  - Update the path in `main1.py` if installed in a different location
  - Default: `C:\Program Files\Tesseract-OCR\tesseract.exe`

### Python Requirements
- Python 3.8+
- Dependencies listed in requirements.txt

## Installation

1. Install system dependencies:
   ```bash
   # Install Tesseract-OCR
   # Download from: https://github.com/UB-Mannheim/tesseract/wiki
   ```

2. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Main Detection Script
```bash
python main1.py
```
- Processes `mycarplate.mp4` video file
- Detects license plates and extracts text
- Saves results to `car_plate_data.txt`

### Extract Frames from Video
```bash
python img.py
```
- Extracts frames from `mycarplate.mp4`
- Saves to the `image/` directory

### Clean Up Images
```bash
python imgdeleteyolo.py
```
- Removes images without corresponding `.txt` annotation files

## Output

- **car_plate_data.txt**: Detected license plates with timestamps
  - Format: NumberPlate | Date | Time

## Notes

- The project expects a video file named `mycarplate.mp4` in the project root
- Ensure Tesseract-OCR is properly installed and the path is correct
- The pre-trained model (`best.pt`) should be in the project root directory

## License

This project is for educational purposes.
