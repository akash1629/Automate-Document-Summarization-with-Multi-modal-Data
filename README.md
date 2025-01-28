# Automate-Document-Summarization-with-Multi-modal-Data


## Overview
This project implements a **multi-modal document summarization pipeline** that extracts and processes both **text** and **images** from PDF documents. Using advanced AI models, it combines these data modalities to generate meaningful summaries and insights.

## Features
- Extracts **text** and **images** from PDF documents.
- Cleans and preprocesses extracted text.
- Generates **text embeddings** using `SentenceTransformer`.
- Processes **image embeddings** using `CLIP`.
- Combines text and image embeddings for enhanced context understanding.
- Produces summaries using a **T5-based summarization model**.
- Supports evaluation using **ROUGE** and **BLEU** metrics.
- Interactive Gradio interface for user-friendly input/output.

## Project Structure
- **Main Script**: Contains the pipeline for processing PDFs, extracting data, and generating summaries.
- **Utility Functions**:
  - Text and image extraction.
  - Embedding generation.
  - Summarization and evaluation.
- **Gradio Interface**: Interactive tool to upload PDFs and receive summaries instantly.

## Models Used
1. **CLIP** (for image embeddings): `openai/clip-vit-base-patch32`
2. **SentenceTransformer** (for text embeddings): `sentence-transformers/all-MiniLM-L6-v2`
3. **T5 Model** (for summarization): `t5-small`

## Installation

### Environment Setup
1. Clone this repository:
   ```bash
   git clone https://github.com/akash1629/Automate-Document-Summarization-with-Multi-modal-Data.git
   cd Automate-Document-Summarization-with-Multi-modal-Data
   ```
2. Install required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

### Required Libraries
- `torch`, `transformers`, `sentencepiece`, `sentence-transformers`
- `PyMuPDF` (PDF processing)
- `opencv-python` (Image handling)
- `evaluate` (ROUGE/BLEU metrics)
- `gradio` (Interactive interface)

## Usage

### Run Locally
1. Launch the main pipeline:
   ```bash
   python main.py
   ```
2. Upload your PDF file through the Gradio interface and select the summary style (concise/detailed).
3. View the generated summary and error messages (if any).

### Example Output
- Input: A sample PDF containing multiple pages with text and images.
- Output: A concise or detailed summary based on the input.

### Sample Pipeline Execution
```python
from main import multi_modal_summarization_pipeline
summary, embeddings = multi_modal_summarization_pipeline("sample_document.pdf", style_prompt="concise")
print("Generated Summary:", summary)
```

## Evaluation
- Evaluate the summarization output using reference summaries:
```python
from main import evaluate_summary
scores = evaluate_summary("reference_summary", "generated_summary")
print(scores)
```

## Gradio Interface
Launch the Gradio interface with the following command:
```bash
python app.py
```
Features:
- Upload PDFs.
- Select summary style (concise/detailed).
- Real-time summary generation.

## Examples
- **Sample PDF**: `sample_document.pdf` (included in the repository).
- **Sample Summary**:
  ```
  This document contains multiple pages with text and images to demonstrate multi-modal summarization capabilities.
  ```

## Contribution
We welcome contributions! To contribute:
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Added new feature"
   ```
4. Push to your branch:
   ```bash
   git push origin feature-name
   ```
5. Open a pull request.

## License
This project is licensed under the [MIT License](LICENSE).

## Acknowledgments
- **Hugging Face Transformers**: For providing pre-trained models.
- **PyMuPDF**: For efficient PDF text and image extraction.
- **Gradio**: For simplifying UI development.

## Contact
- **Author**: Akash Raut
- **Email**: [akashraut16299@gmail.com](mailto:akashraut16299@gmail.com)
- **GitHub**: [https://github.com/akash1629](https://github.com/akash1629)

Feel free to open issues or pull requests for any bugs or enhancements!

