# PDF to Text Converter

This Python script converts PDF files to plain text files, preserving the original content and formatting as much as possible. It is designed to be simple to use and efficient in processing multiple PDFs within a directory. By utilizing the `pdfplumber` library, the script extracts text from each page of a PDF file and stores it in a corresponding text file.

## Features

- Batch processing of multiple PDF files within a directory
- Progress bar for each file conversion
- Output text files named after their respective input PDFs

## Installation

1. Clone this repository to your local machine:

git clone https://github.com/your-username/pdf-to-text-converter.git

2. Navigate to the project folder and install the required dependencies:

cd pdf-to-text-converter
pip install -r requirements.txt


## Usage

1. Place the PDF files you want to convert in the same directory as the script.
2. Run the script:

python pdf_to_text_converter.py

3. The script will convert each PDF file to a text file and save it in the same directory.

## Dependencies

- [pdfplumber](https://github.com/jsvine/pdfplumber)

