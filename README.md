# ChatGPT SQL Data Analyst

This repository contains an implementation of the ChatGPT assistant that helps with data analysis. The assistant takes a database schema in the JSON format as input and generates SQL queries using business questions as prompts. It can also be asked to compose code for a specific programming language to visualize the results of the generated SQL query.

## Prerequisites

Before running the code, make sure you have the [OpenAI API key](https://platform.openai.com/account/api-keys).<br>
Please note that the use of the API is [not free](https://openai.com/pricing#chat).

## Installation

1. Clone the repository:

   ```shell
   git clone https://github.com/valiotti/chatgpt-sql-data-analyst.git
   ```

2. Install the required dependencies:

   ```shell
   pip install openai panel
   ```

## Repository content

- `Chat.ipynb` - Jupyter Notebook for interaction with the ChatGPT assistant.
- `Convert SQL to JSON.ipynb` - Jupyter Notebook for converting SQL scripts to create tables in a database into the JSON format.


## Usage

### `Chat.ipynb`

1. Provide the OpenAI API key:

   ```python
   openai.api_key = 'MY_OPENAI_API_KEY'
   ```

2. Set up the path and name of the JSON file with the database schema and the database type (for ChatGPT to generate queries for a specific SQL dialect):

   ```python
   JSON_STORE_PATH = './jsons'
   JSON_NAME = 'my_schema.json'
   DB = 'MY_DB'
   ```

3. Run all cells.

4. After running the final cell, you will see the UI for interacting with the ChatGPT assistant. Enter a business question in the input field and click the `Chat!` button to retrieve a corresponding SQL query. Alternatively, if you already have a generated SQL query, you can ask the assistant to compose code for a specific programming language to visualize the results.

5. During the interaction with ChatGPT, the entire chat history is sent as input to the model. This can affect response time and eventually reach the text length limit. However, you can perform a reset. To do so, execute the cell where `context` is defined and the next one where the UI is launched.

<u>To maximize the impact of your interaction with the assistant and ensure accurate results, provide clear and specific instructions in the prompt.</u>

### `Convert SQL to JSON.ipynb`

Since the ChatGPT assistant takes a database schema as the context in the JSON format, it may be useful to have code for converting SQL scripts on hand.

1. Provide the OpenAI API key:

   ```python
   openai.api_key = 'MY_OPENAI_API_KEY'
   ```

2. Set up the input SQL scripts path, path and name for a JSON file to store results:

   ```python
   SQL_SCRIPTS_PATH = './sql_scripts'
   JSON_STORE_PATH = './jsons'
   JSON_NAME = 'my_schema.json'
   ```

   Please note that one SQL script should correspond to one table in the database.

3. Run all cells.

## Demo

### `Convert SQL to JSON.ipynb`

https://github.com/valiotti/chatgpt-sql-data-analyst/assets/127095297/eb32bb41-57c2-4292-b140-1df54d698946

### `Chat.ipynb`

https://github.com/valiotti/chatgpt-sql-data-analyst/assets/127095297/19535f51-8fd1-4bbb-a257-2d89e8d62fef

## AIPRM templates

Corresponding [AIPRM](https://www.aiprm.com/) templates for using the assistant inside the ChatGPT UI:
- [SQL DDL to JSON Converter](https://app.aiprm.com/prompts/1827666952433426432/sql-ddl-to-json-converter). Enter CREATE statements one by one and collect them together later or enter all statements at once.
- [Data Analysis Assistant](https://app.aiprm.com/prompts/1827292112719450112/data-analysis-assistant). You need to specify the type of your database in the corresponding field and enter the database schema in the JSON format as the initial prompt.

## Contributing

Contributions to the code are welcome! If you find any issues or have suggestions for improvement, please create an issue or submit a pull request.

## Acknowledgements

Kudos to the course [ChatGPT Prompt Engineering](https://learn.deeplearning.ai/chatgpt-prompt-eng) for providing inspiration and guidance in developing this assistant.
