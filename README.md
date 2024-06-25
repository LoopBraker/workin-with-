# workin-with-pdfs: Extracting Insights from Scientific Papers

This repository aims to streamline the extraction and structuring of information from scientific academic papers (PDFs) for use in a Retrieval-Augmented Generation (RAG) pipeline. We leverage the power of Python libraries like `unstructured`, `grobid`, and potentially Large Language Models (LLMs) to achieve this. 

**Key Features:**
1. **Automated PDF Processing:**  Effortlessly extract text and metadata from PDFs of research papers.
2. **Structure Inference:** Identify and segment documents into meaningful sections (e.g., Abstract, Introduction, Methods, Results, Conclusion).
3. **Markdown Conversion:** Transform extracted content into a clean and readable Markdown format for easy editing and integration with other tools.
4. **RAG Pipeline Foundation:**  Prepare the processed documents for efficient indexing and retrieval, crucial for building a robust RAG system.

## Technology Stack

- **Python:** The core programming language for this project.
- **unstructured:** A powerful library for extracting text and structure from various document formats, including PDFs.
- **grobid:**  (Optional) A specialized tool designed for extracting and structuring bibliographic information and citations from scientific articles.
- **Large Language Model (LLM):**  (Optional) Explore the potential of LLMs for tasks like section classification, content summarization, and keyword extraction.
- **Markdown:** The chosen format for representing structured information, ensuring human readability and compatibility.

## Setup and Usage

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/LoopBraker/working-with-pdfs.git
   cd working-with-pdfs
   ```

2. **Create a Virtual Environment (Recommended):**
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **(Optional) Download grobid:**
   - Download the latest grobid release from [https://grobid.readthedocs.io/](https://grobid.readthedocs.io/)
   - Extract the archive and note the path to the `grobid.sh` script.

5. **Prepare your PDFs:**
   - Place the PDFs you want to process in a dedicated directory (e.g., `./data/pdfs`).

6. **Run the Extraction Script:**
   ```bash
   python extract_and_structure.py --pdf_dir ./data/pdfs --output_dir ./data/processed
   ```
   - Replace `./data/pdfs` and `./data/processed` with your desired input and output directories.
   - Use the `--grobid_path` argument to specify the path to your `grobid.sh` script if you choose to use grobid.

## Examples

**Basic Text Extraction:**
```python
from unstructured.partition.auto import partition

document = partition(filename="example.pdf")

for element in document:
    print(element.text)
```

**Structure Inference with unstructured:**
```python
# ... (Code example demonstrating how to use unstructured to infer document structure) 
```

**Incorporating grobid (Optional):**
```python
# ... (Code example showcasing grobid integration for bibliographic data)
```

## Contributing

We welcome contributions! If you have ideas for improvements, new features, or bug fixes, feel free to open an issue or submit a pull request. 

## License

This project is licensed under the MIT License. 
