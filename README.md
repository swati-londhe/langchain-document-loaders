LangChain Document Loader Examples
This repository contains Python scripts demonstrating various document loaders from the LangChain community library. These examples show how to load different types of files and web content, including PDFs, CSVs, text files, directories of PDFs, and web pages. Some scripts also integrate with OpenAI's Chat model for processing the loaded content, such as summarization or question answering.
Prerequisites

Python 3.8+
Install required dependencies:pip install langchain langchain-community langchain-openai python-dotenv


For scripts using ChatOpenAI, set up an OpenAI API key in a .env file:OPENAI_API_KEY=your_api_key_here


Ensure the following files are available in the working directory (as referenced in the scripts):
Social_Network_Ads.csv (CSV dataset for csv_loader.py)
cricket.txt (Text file for text_loader.py)
dl-curriculum.pdf (PDF file for pdf_loader.py)
A books directory containing PDF files (for directory_loader.py)



Files and Descriptions

directory_loader.py

Uses DirectoryLoader with PyPDFLoader to lazily load all PDF files from a specified directory ('books').
Prints metadata for each loaded document.
Useful for batch loading multiple documents of the same type.


csv_loader.py

Loads a CSV file ('Social_Network_Ads.csv') using CSVLoader.
Prints the number of loaded documents and an example document.
Each row in the CSV is treated as a separate document.


text_loader.py

Loads a text file ('cricket.txt') using TextLoader.
Prints document type, length, content, and metadata.
Chains with ChatOpenAI to generate a summary of the loaded poem.


pdf_loader.py

Loads a PDF file ('dl-curriculum.pdf') using PyPDFLoader.
Prints the number of pages (documents) and content/metadata of example pages.
Each page of the PDF is loaded as a separate document.


webbase_loader.py

Loads content from a web URL (e.g., a Flipkart product page) using WebBaseLoader.
Chains with ChatOpenAI to answer a question based on the loaded web content.
Demonstrates web scraping and question-answering integration.



How to Run

Ensure the .env file is configured with your OpenAI API key (for scripts using ChatOpenAI).
Place required data files (CSV, TXT, PDF) and the 'books' directory in the same folder as the scripts.
Run any script using Python:python <script_name>.py

Replace <script_name> with the desired file (e.g., pdf_loader.py).
Outputs will be printed to the console, such as document counts, content, metadata, or AI-generated responses.

Notes

Scripts using ChatOpenAI (e.g., text_loader.py, webbase_loader.py) require an active OpenAI API key and may incur usage costs.
Ensure a stable internet connection for webbase_loader.py as it fetches web content.
The Social_Network_Ads.csv and dl-curriculum.pdf files are referenced in the scripts; their contents are provided in the query for reference but should be actual files for execution.
Modify file paths or URLs in the scripts to test with different data sources.
