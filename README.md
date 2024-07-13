## OCR with Tesseract and OpenCV

### Overview

This project demonstrates how to perform Optical Character Recognition (OCR) on images using Tesseract and OpenCV in Python. It includes image preprocessing, text detection in multiple languages, bounding box visualization for detected characters and texts (only for English), and post-processing of the detected text.

### Features

1. **Multilingual OCR**: Supports text detection in English, Bengali, Kannada, and Hindi.
2. **Image Preprocessing**: Includes resizing, grayscale conversion, Gaussian blur, and binary thresholding.
3. **Text Detection**: Detects text in images using Tesseract OCR.
4. **Character and Text Bounding Boxes**: Draws bounding boxes around detected characters and text (only for English).
5. **Text Post-Processing**: Corrects detected text for spelling and punctuation.
6. **Output Visualization**: Displays processed images and text using matplotlib (for notebook environments).

### Installation

1. **Prerequisites**:
    - Python 3.x
    - OpenCV
    - Pytesseract
    - Tesseract OCR
    - TextBlob
    - matplotlib

2. **Install Tesseract OCR**:
    - Download and install Tesseract OCR from [here](https://github.com/tesseract-ocr/tesseract).
    - Note the installation path, e.g., `C:\Program Files\Tesseract-OCR`.

3. **Install Python packages**:
    ```sh
    pip install opencv-python pytesseract textblob matplotlib
    ```

### Usage

1. **Set the Path to Tesseract Executable**:
    - Modify the `pytesseract.pytesseract.tesseract_cmd` line in the script to the path where Tesseract OCR is installed, e.g.:
    ```python
    pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"
    ```

2. **Run the Script**:
    - Execute the script in a Python environment.
    - Follow the prompts to select the language and provide the image file path.
    - The script will process the image and display the results.

### Script Explanation

1. **Import Libraries**:
    ```python
    import cv2
    import pytesseract
    import numpy as np
    import matplotlib.pyplot as plt
    import string
    import re
    from textblob import TextBlob
    ```

2. **Set Tesseract Executable Path**:
    ```python
    pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"
    ```

3. **Image Preprocessing**:
    - Converts the image to grayscale.
    - Applies Gaussian blur.
    - Uses Otsu's thresholding to binarize the image.

4. **Text Detection**:
    - Detects text in the image using Tesseract OCR.
    - Supports multiple languages.

5. **Bounding Boxes (Only for English)**:
    - Draws bounding boxes around detected characters and texts.
    - Saves the processed images with bounding boxes.

6. **Text Post-Processing**:
    - Corrects spelling and punctuation using TextBlob.

7. **Visualization**:
    - Displays images using matplotlib for better compatibility in notebook environments.

### Future Updates

- **Additional Language Support**: Add support for more languages by updating the `languages` dictionary and ensuring Tesseract has the necessary language data files.
- **Enhanced Image Preprocessing**: Experiment with other preprocessing techniques to improve OCR accuracy.
- **GUI Integration**: Create a graphical user interface to make the tool more user-friendly.
- **Batch Processing**: Add functionality to process multiple images in a batch.

### How to Add Other Languages

1. **Ensure Tesseract Supports the Language**:
    - Check if Tesseract has the trained data for the desired language.
    - Language files are typically named `<lang>.traineddata` and located in the `tessdata` directory.

2. **Update the `languages` Dictionary**:
    ```python
    languages = {
        "1": "eng",
        "2": "ben",
        "3": "kan",
        "4": "hin",
        "5": "new_language_code"
    }
    ```

3. **Modify the Prompts**:
    - Add a new option in the language selection prompt to accommodate the new language.

### Conclusion

This project provides a comprehensive OCR solution using Tesseract and OpenCV, capable of handling multiple languages and providing visual feedback on text detection. By following the installation and usage instructions, users can easily process images and extract text in their desired languages. Future updates and enhancements will further extend the capabilities of this tool.
