# Small Cows finding relationship between entities

This project focuses on extracting entities and their relationships from text found in web articles (URLs) and PDF files. The relationships betwween entities are then scored based on their relevance, and visual graph is generated to represent these connections. This script utilise Natural Language Processing (NLP) techniques, especially using **spaCy**, for entities and relationships extraction.

## Features 
- Extract entities such as `PERSON`, `ORG`, `GPE` from text.
- Identifies relationships between these entities using dependency parsing and predefined patterns.
- Computes a score for each relationships based on entity types and relation length.
- Visualises the extracted entities and relationships in an interactive graph using **NetworkX** and **Matplotlib**
- Accepts input from both web URLs and PDF files

## Requirements
To run the project, you will need to install the following dependencies:

- Python 3.x
- Install dependencies using the `requirements.txt` file:

```
pip install -r requirements.txt
```

Dependencies include:
- spacy: for Natural Language Processing (NLP).
- beautifulsoup4: for web scraping HTML content.
- networkx: for creating and visualizing the graph.
- matplotlib: for plotting the graph.
- PyPDF2: for extracting text from PDF files.
- pandas: for data manipulation.
- numpy: for numerical operations.
- tqdm: for progress bars.

## Setup
1. Download spaCy model: Before running the script, ensure you have the spaCy model installed:
```
python -m spacy download en_core_web_sm
```
2. Dependencies: Create a virtual environment and install the dependencies:
```
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

## How to Use
### Running the Script
1. Run the main script:
```
python Small_cows_final_script.py
```
2. Choose the input type:
  - URL: To process a web article.
  - PDF: To process a PDF file.

  Example:
  - For a URL: Enter 'url' to process a web article or 'pdf' to process a PDF file: url
  - For a PDF: Enter 'url' to process a web article or 'pdf' to process a PDF file: pdf

3. If you choose URL, you will be asked to input the URL of the article you want to process.
4. If you choose PDF, you will be prompted to enter the file path of the PDF you want to process.

### Output
The script will:
- Extract text from the provided source (URL or PDF).
- Break down the text into sentences.
- Extract entities and relationships from each sentence.
- Score the entity-relation pairs based on predefined criteria.
- Filter the top entity-relation pairs based on their score.
- Visualize the relationships as a graph with nodes (entities) and edges (relations).

## Code Breakdown
- **parse_text_from_url(url)**: Extracts text from a given URL using web scraping.
- **parse_text_from_pdf(pdf_path)**: Extracts text from a given PDF file.
- **save_sentences_to_csv(text)**: Saves parsed text as sentences in a CSV file for further processing.
- **get_entities(sent)**: Extracts entities (subjects and objects) from a sentence using spaCy.
- **get_relation(sent)**: Extracts relationships between entities using dependency parsing.
- **score_entity_relation(entities, relation)**: Scores the extracted entity-relation pairs based on certain criteria.
- **process_sentences_to_graph(csv_sentences)**: Processes the sentences to extract entities, relationships, scores, and visualize them as a graph.
