APPROACH: 

1. Data Preparation:

-> loaded Positive and negative word lists and English stop words list (for text cleaning).
-> Input/Output Setup:
*Read URLs and desired output structure from separate Excel files.

2. Web Page Processing:

-> Function: extract_article_text
* Fetches the web page
* checks for successful retrieval with response.raise_for_status 
* Parses HTML using BeautifulSoup.
-> Extracted: 
* Title (soup.find('h1'))
* Main content (soup.find('div', class_='td-post-content'))

3. Preprocessed the text by removing stop words, keeping all the alpha numeric characters, and keeping everything in lower case for equality.

4. Sentiment Analysis:

Calculated various metrics on the basis of formulas given in Text Analysis Document file.

5. Data Output and Execution:

-> iterated over each URL
-> Process each URL in the input dataframe.
-> extracted the main content and the heading from each of the URL
-> Calculated the sentiment and other metrics.
-> then for Formatting and Saving to the Output:
* Convert data to a pandas DataFrame.
* Reorder based on desired output structure (from separate Excel file).
* Save DataFrame as a new Excel file.
* Download the output file using files.download().


//****************************************************************************//

GETTING STARTED: 

-> open the .py file in Google colab or Jupyter Notebook etc.
-> import all the necessary Dependencies 
-> Upload your input.xlsx, positive_words.txt, negative_words.txt, and Output Data Structure.xlsx files using the file upload dialog in Colab.
-> finally run the code

Note: 
-> Ensure the file paths for input_file, positive_words_file, negative_words_file, and structure_file match the uploaded file names.
-> The script will automatically download the output Excel file (output.xlsx) after processing.

//*****************************************************************************//

DEPENDENCIES:

requests -> for making HTTP requests to fetch web pages
BeautifulSoup -> for parsing HTML and XML document
TextBlob -> for simple text processing and sentiment analysis
nltk -> Natural Language Toolkit for text processing
pandas -> for data manipulation and analysis
re -> regular expression
files -> for uploading file
