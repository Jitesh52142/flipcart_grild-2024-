# Flipkart Grid 2024 - Real-Time Multi-Modal Detection and Analysis

This project is developed for **Flipkart Grid 2024**, showcasing a real-time multi-modal detection and analysis system that integrates object detection, optical character recognition (OCR), and QR/barcode scanning. The system aims to provide an all-in-one solution for analyzing product visuals, textual information, and embedded QR/barcode data in a streamlined and efficient manner.

## Features

### 1. **Object Detection**
- Implements **Faster R-CNN with ResNet-50** as the backbone for object detection.
- Detects objects in real-time with bounding box visualization.
- Filters detected objects based on a configurable confidence threshold (default: 0.3).
- Analyzes detected objects' structure to evaluate box dimensions and categorizes them as "Good Structure" or "Bad Structure."

### 2. **Text Recognition (OCR)**
- Uses **Tesseract OCR** to extract textual information from images or video frames.
- Converts frames to grayscale for enhanced OCR performance.
- Outputs extracted text for further analysis.

### 3. **QR Code and Barcode Detection**
- Utilizes the **Pyzbar library** for scanning and decoding QR codes and barcodes.
- Extracts data, type, and positional information of QR codes/barcodes detected in each frame.
- Displays QR/barcode information visually on the frame.

### 4. **Real-Time Video Processing**
- Captures live video feed from the system's webcam.
- Processes video frames in real-time, with adjustable frame skipping to balance performance and accuracy.
- Annotates frames with detected objects, text, and QR/barcodes for visualization.

## Workflow
1. **Initialization**: Loads the pre-trained Faster R-CNN model for object detection and configures the Tesseract OCR engine.
2. **Video Capture**: Captures frames from the webcam, resized for optimal performance (default: 640x480 resolution).
3. **Object Detection**: Processes each frame to detect objects, calculates their dimensions, and evaluates their structure.
4. **Text Recognition**: Extracts text content from each frame using OCR.
5. **QR/Barcode Detection**: Identifies and decodes any QR codes or barcodes present in the frame.
6. **Results Aggregation**: Combines detection, OCR, and QR/barcode results into a comprehensive report for each frame.
7. **Visualization**: Overlays bounding boxes, text, and QR/barcode details on the video feed.

## Setup Instructions

### Prerequisites
Ensure you have the following installed:
- Python 3.7 or later
- [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) (Install and configure the executable path in the code)
- Required Python libraries:
  ```bash
  pip install opencv-python-headless pytesseract torchvision torch pyzbar numpy
  ```

### Running the Project
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/flipkart-grid-2024.git
   ```
2. Navigate to the project directory:
   ```bash
   cd flipkart-grid-2024
   ```
3. Run the main script:
   ```bash
   python main.py
   ```
4. Press **'q'** to stop the video feed.

## Applications
This project is designed for:
- **Retail and E-commerce**: Enhance product inspection by analyzing object structure, extracting textual labels, and decoding QR/barcodes.
- **Logistics**: Streamline package inspection and automate inventory management.
- **Smart Surveillance**: Monitor and analyze objects, textual signs, and encoded information in real-time environments.

## Key Components
- **Object Detection**: Faster R-CNN with ResNet50 backbone from `torchvision.models.detection`.
- **OCR**: Tesseract for text extraction from frames.
- **QR/Barcode Detection**: Pyzbar library for detecting and decoding.
- **Visualization**: OpenCV for rendering bounding boxes and labels on frames.

## Future Enhancements
- Integrate multilingual OCR for improved global usability.
- Add support for product classification based on detected objects.
- Implement cloud-based storage for detected data and analytics.
- Optimize the system for edge devices to enable real-time on-device processing.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
- **Flipkart Grid 2024**: For inspiring this project and providing a platform to innovate.
- **PyTorch & TorchVision**: For robust deep learning models.
- **Tesseract OCR & Pyzbar**: For simplifying text and barcode detection.

