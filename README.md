# Recruiter AI Agent using Letta Framework

This project demonstrates how to build a multi-agent AI recruiter using the Letta framework. The primary example is provided in the `Recruiter_AI_Agent.ipynb` Jupyter Notebook.

## Project Structure

- **`Recruiter_AI_Agent.ipynb`**: The main Jupyter Notebook showcasing the implementation of the recruiter AI agent. It covers:
    - Setting up the Letta client.
    - Creating and utilizing shared memory blocks for context persistence.
    - Orchestrating multiple AI agents, including an "outreach_agent" and a "recruiter_agent".
    - Defining and using tools for agents, such as drafting candidate emails and finding suitable candidates.
- **`helper.py`**: A utility script for managing environment variables and, critically, for retrieving the OpenAI API key required by the agents.
- **`requirements.txt`**: Lists the Python dependencies required to run the project.

## Preparation

### 1. Install Dependencies

Open your terminal, navigate to the project's root directory (where `requirements.txt` is located), and run:

```bash
pip install -r requirements.txt
```

This will install the necessary libraries, including `letta` and `python-dotenv`.

### 2. Configure OpenAI API Key

This project requires an OpenAI API key to function. The API key is managed through the `helper.py` file. You have two options to set it up:

*   **Environment Variable (Recommended):**
    Set the `OPENAI_API_KEY` environment variable in your system. The `helper.py` script is configured to automatically pick it up. Create a `.env` file in the project root directory (or one level above) with the following content:
    ```
    OPENAI_API_KEY="YOUR_ACTUAL_OPENAI_API_KEY"
    ```
*   **Directly in `helper.py` (Not Recommended for Production):**
    You can hardcode your API key by modifying the `get_openai_api_key()` function within `helper.py`.
    Locate the line `api_key = "YOUR_API_KEY"` and replace `"YOUR_API_KEY"` with your actual OpenAI API key.
    **Caution:** If you choose this method, be extremely careful not to share your notebook or commit this file to a public repository with your API key exposed.

Ensure that `helper.py` is in the same directory as the `Recruiter_AI_Agent.ipynb` notebook or is accessible in your Python path.

## Running the Recruiter AI Agent

1.  After completing the preparation steps, open the `Recruiter_AI_Agent.ipynb` notebook using Jupyter Lab or Jupyter Notebook.
2.  Follow the instructions and execute the cells in the notebook sequentially to see the recruiter AI agent in action.

The notebook will guide you through:
- Initializing the Letta client.
- Creating a shared memory block with company information.
- Defining and setting up an outreach agent to draft emails.
- Defining and setting up a recruiter agent to find candidates.
- Running a conversation with the recruiter agent to find a candidate for a "Product Manager" role.

## Letta Framework

This project leverages the [Letta framework](https://docs.letta.dev/) for building and orchestrating AI agents. The Letta framework simplifies the development of multi-agent systems by providing tools for agent creation, memory management, and tool integration.

## Contributing

Feel free to fork this repository, make improvements, and submit pull requests.
