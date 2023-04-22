import os
import pdfplumber
import sys

# Get the current directory where the script file is located
script_dir = os.path.dirname(os.path.abspath(__file__))

# Loop through each file in the script directory
for filename in os.listdir(script_dir):
    # Check if the file is a PDF file
    if filename.endswith('.pdf'):
        # Create the input and output file paths
        input_file_path = os.path.join(script_dir, filename)
        output_file_path = os.path.join(script_dir, os.path.splitext(filename)[0] + '.txt')
        
        # Print the file name before starting the conversion
        print(f"Converting {filename}...")

        # Open the PDF file
        with pdfplumber.open(input_file_path) as pdf:
            # Create an empty string to hold the text from the PDF file
            text = ""

            # Loop through each page in the PDF file
            for i, page in enumerate(pdf.pages):
                # Extract the text from the current page
                page_text = page.extract_text()
                # Add the text from the current page to the overall text string
                text += page_text
                # Add a demarcation after the current page
                text += "\n" * 5

                # Update progress bar
                progress = (i+1) / len(pdf.pages)
                sys.stdout.write('\r')
                sys.stdout.write("[%-20s] %d%%" % ('='*int(20*progress), 100*progress))
                sys.stdout.flush()

        # Open the output TXT file in write mode
        with open(output_file_path, 'w') as txt_file:
            # Write the text to the output TXT file
            txt_file.write(text)

        # Clear progress bar
        sys.stdout.write('\r')
        sys.stdout.write("[%-20s] %d%%" % ('='*20, 100))
        sys.stdout.write('\n')
