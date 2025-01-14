# AI_TEXT_CLASSIFICATION

## Overview

This project leverages advanced Natural Language Processing (NLP) techniques to classify text as "AI-generated" or "Human-written." It also includes a feature to process PDF documents, identifying and highlighting AI-generated sentences in yellow.

---

## Features

1. **Text Classification**:

   - Classifies text into two categories: "AI-generated" or "Human-written" using a fine-tuned BERT model.

2. **PDF Sentence Highlighting**:

   - Automatically highlights AI-generated sentences in yellow within PDF documents.

3. **Batch Prediction**:
   - Processes multiple unlabelled articles and saves predictions in a CSV file.

---

## Requirements

### Python Packages

Install the following packages before running the project:

```bash
pip install pandas tensorflow transformers scikit-learn ftfy fitz nltk
```

### Additional Requirements

- Pre-trained BERT model (`bert-base-uncased`) from Hugging Face.
- NLTK data for sentence tokenization (`punkt`).

---

## How to Run the Project

### 1. Code Execution

#### Text Classification

1. **Train the Model**:

   - Fine-tune the BERT model using the labelled training dataset by running the provided script.

2. **Predict Labels for New Text**:

   - Use the `predict_text` function to classify individual text samples:
     ```python
     user_text = "Sample text to classify."
     predicted_label = predict_text(user_text, model, tokenizer)
     print(f"Predicted label: {predicted_label}")
     ```

3. **Batch Prediction**:
   - Classify multiple articles from the unlabelled dataset and save the results in a CSV file (`predictions.csv`).

#### Highlight AI-Generated Sentences in PDFs

1. **Input and Output Paths**:

   - Set the input PDF path (`pdf_path`) and specify the output PDF path (`output_path`):
     ```python
     pdf_path = '/content/input_document.pdf'
     output_path = '/content/output_document.pdf'
     ```

2. **Run the Highlighting Function**:
   - Execute the `highlight_ai_text_in_pdf` function to process the PDF and highlight AI-generated sentences.

---

## Output

### 1. CSV File

- Batch predictions for the unlabelled dataset will be saved in a file named `predictions.csv`.

### 2. PDF File

- A new PDF file with AI-generated sentences highlighted in yellow will be saved at the specified `output_path`.

---

## Applications

1. **Content Moderation**:

   - Identify and manage AI-generated content in online platforms.

2. **Academic Integrity**:

   - Detect AI-generated content in research papers and assignments.

3. **Content Analysis**:
   - Analyze the origin of text in large datasets.
