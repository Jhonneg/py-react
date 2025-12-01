# ReAct Agent with OpenAI

This project implements a simple ReAct (Reasoning and Acting) agent using OpenAI's GPT models. The agent is designed to break down complex queries into thoughts and actions, executing external tools as needed to gather information before providing a final answer.

## Features

-   **`Agent` Class**: A core [`Agent`](main.ipynb#cc7aa2e1) class that manages conversational state and interacts with the OpenAI API.
-   **ReAct Prompting**: Utilizes a specific prompt structure (defined in [`main.ipynb`](main.ipynb#4d5c1ebf)) to guide the model's reasoning and action generation.
-   **Tool Integration**: Includes several external tools that the agent can invoke:
    -   [`calculate`](main.ipynb#ddf45638): Performs arithmetic calculations.
    -   [`get_cost`](main.ipynb#ddf45638): Returns the cost of specific items.
    -   [`wikipedia`](main.ipynb#ddf45638): Searches Wikipedia for summaries.
-   **Automated Query Execution**: A [`query`](main.ipynb#e786e610) function that runs the agent in a loop, parsing actions from the agent's responses and executing the corresponding tools automatically.

## Setup

To get this project running, follow these steps:

1.  **Install dependencies**:
    You can install the necessary Python packages using pip:

    ```sh
    pip install python-dotenv openai httpx
    ```

2.  **Set up environment variables**:
    Create a file named [`.env`](.env) in the root directory of the project. Add your OpenAI API key to this file:

    ```
    OPENAI_API_KEY='YOUR_OPENAI_API_KEY'
    ```

    The [`main.ipynb`](main.ipynb) notebook includes code to load these environment variables.

## Usage

The primary implementation and demonstration of the ReAct agent are within the [`main.ipynb`](main.ipynb) Jupyter Notebook.

Here's a quick overview of how to interact with the agent using the automated `query` function:

```python
# filepath: /home/jonee/Work/py-react/main.ipynb
...
# Import the query function
# from main.ipynb (assuming you have run previous cells)

# Example 1: Calculate total cost
question_cost = """I want to buy 2 books and 3 pens. How much do i have to pay?"""
query(question_cost)

# Example 2: Get information from Wikipedia
question_wiki = """EUFA Euro 2021"""
query(question_wiki)