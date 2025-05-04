# 📄 PDF Content Extractor
A powerful Python script that extracts content from PDF files based on structured section headers. 
It is ideal for parsing reports, research papers, or documents with a clear outline format.

## Features

- Extracts text between two headers in a PDF
- Normalizes and cleans the extracted text
- Supports recursive sub-section extraction
- Saves cleaned sections and logs problematic ones
- Outputs in `.txt` and `.pkl` formats


## 📁 Project Structure

```

pdf-content-extractor/
│
├── extract\_pdf.py               # Core logic for section-wise PDF extraction
├── main.py                      # Sample runner using extract\_pdf
├── output/
│   ├── combined\_content\_save.txt  # Final extracted and cleaned content
│   └── exceeds.txt                # Sections that are too long or invalid
├── requirements.txt             # Python dependencies
└── README.md                    # Project documentation


## Getting Started
##Usage Example


from extract_pdf import extract_main_sections_from_outline, process_subsections_recursive
pdf_path = "your_file.pdf"
main_sections = extract_main_sections_from_outline(pdf_path)
for i in range(len(main_sections) - 1):
    process_subsections_recursive(pdf_path, main_sections[i], main_sections[i + 1])

Outputs are saved in the `output/` directory.

---

## 🧾 Sample Output

**combined\_content\_save.txt**

Section Title
-----------------------------
Cleaned content of this section...

**exceeds.txt**

SectionTitle | Length | No subsections

---

##Configuration

You can adjust the length limit for section content:

section_split_threshold = 15000  # default value
