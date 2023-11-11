
# OCR and Turkish Name Extraction

## Overview

This script is designed to extract text from a screenshot of a webpage, identify names within the text using Natural Language Processing (NLP), and classify these names based on a specific criterion, such as identifying Turkish names. The script uses Optical Character Recognition (OCR) to convert image text into machine-readable text, then applies NLP for name extraction, and finally classifies the names using a pre-trained machine learning model.

## Requirements

- Python 3
- Libraries: pytesseract, spaCy
- Pre-trained spaCy NLP model: `en_core_web_sm`
- Pre-trained machine learning model for name classification ([Turkish Binary Classifier](https://github.com/hakancangunerli/turkish_binary_classifier))
- Tesseract OCR Software

## Usage

1. Place the screenshot you want to process in the `./captured/` directory and ensure it is named `tda_lab_member_page.png`.
2. Ensure the machine learning model files (`tfidf_vectorizer.pkl` and `logistic_regression_model.pkl`) from the [Turkish Binary Classifier](https://github.com/hakancangunerli/turkish_binary_classifier) are in the same directory as the script.
3. Run the script. It performs the following tasks:
   - Extracts text from the screenshot.
   - Saves the extracted text to `extracted_text.txt`.
   - Processes the extracted text to identify names using spaCy's NLP model.
   - Applies the pre-trained machine learning model to classify names as Turkish.
   - Outputs a list of identified Turkish names.

## Script Breakdown

- The script is divided into several cells (marked with `# %%`), each performing a specific task:
  - **OCR Function**: Uses `pytesseract` to perform OCR on the image.
  - **Name Classification Function**: Classifies names using a pre-trained model.
  - **Text Extraction**: Extracts text from the screenshot and saves it to a file.
  - **NLP for Name Extraction**: Uses `spaCy` to extract names from the text.
  - **Name Processing**: Processes names and prepares them for classification.
  - **Turkish Name Classification**: Classifies names as Turkish and filters them based on specific criteria.

## Notes

- The script assumes the existence of certain files and directories. Ensure the directory structure and file names are correct before running the script.
- The effectiveness of name extraction and classification depends on the quality of the OCR, the NLP model, and the training of the machine learning model.
