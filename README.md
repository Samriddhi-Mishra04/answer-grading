Answer Grading Using BERT and PDF Extraction : 
This project provides a tool to grade student answers by comparing them with a reference text (e.g., questions and solutions) from PDF files. 
It uses BERT embeddings to evaluate the relevance of the student's answers and generates a score based on cosine similarity between the answers and reference material.

Features : (1) PDF Text Extraction: Extract text from PDF files using PyMuPDF (fitz).
           (2)BERT-Based Embeddings: Utilize BERT to generate embeddings for both reference material (e.g., questions) and student answers.
           (3)Cosine Similarity Scoring: Compare BERT embeddings of student answers to the reference text using cosine similarity and generate a relevance score.
           (4)Easy File Upload: Users can input file paths for both the reference and student answer PDFs.

Setup Instructions : 
Prerequisites
Ensure you have Python installed (Python 3.7 or higher).

Install the required dependencies by running: pip install torch transformers scikit-learn pymupdf


Usage :
Prepare the PDFs: (1) Reference PDF: Contains the questions (or reference material) that the student needs to answer.
                  (2)Student Answers PDF: Contains the student’s answers to the reference questions.

Run the Script: After preparing the PDFs, run the script, which will prompt you for the file paths of both the reference and student answer PDFs.
python grade_answers.py

View Results: The script will output the relevance score for each answer as well as the average score for the entire batch of answers. The scores are generated based on cosine similarity between the reference material and student answers, converted into percentages.



How It Works
PDF Text Extraction:

The text is extracted from the PDF files using PyMuPDF (fitz).
Text is retrieved page-by-page and concatenated.
BERT Embeddings:

BERT is used to generate dense vector representations (embeddings) for the reference material and student answers.
The script uses the bert-base-uncased pre-trained model from Hugging Face's transformers library.
Cosine Similarity:

Cosine similarity measures the closeness between two embeddings. The higher the cosine similarity, the more relevant the student’s answer is to the reference material.
The similarity score is then multiplied by 100 to convert it into a percentage.
Scoring:

The script compares the first two questions from the reference text with the first two student answers and provides individual scores.
An average score is calculated based on the similarity of all answers.
