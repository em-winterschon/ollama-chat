# ollama-chat
A CLI-based Python script that interacts with a local Language Model (LLM) through `Ollama` and `Llama-Cpp` servers. It also supports the use of a local or distant `ChromaDB` vector database for the RAG (Retrieval-Augmented Generation) model, providing a more efficient and flexible way to generate responses.

## Prerequisites

Before you can run the `ollama_chat.py` script, you need to install several Python packages. These packages provide the necessary functionality for the script to interact with the Ollama language model, the ChromaDB vector database, and other features.

Here is the list of required packages:

- `ollama`: This package allows the script to interact with the Ollama server.
- `colorama`: This package is used for colored terminal text.
- `chromadb`: This package enables the script to interact with the ChromaDB vector database.
- `pywin32`: This package provides access to some useful APIs on Windows like clipboard.
- `pygments`: This package is used for syntax highlighting.
- `duckduckgo_search`: This package allows the script to perform DuckDuckGo searches.
- `sentence-transformers`: This package is used for transforming sentences into embeddings.

You can install all these packages using pip, the Python package installer. Run the following command in your terminal:

```bash
pip install ollama colorama chromadb pywin32 pygments duckduckgo_search sentence-transformers
```

## How to Use the Ollama Chatbot Script
This guide will explain how to use the `ollama_chat.py` script. This script is designed to act as a terminal-based user interface for Ollama and it accepts several command-line arguments to customize its behavior.

Here's a step-by-step guide on how to use it:

1. **Run the script**: You can run the script using Python. The command to run the script is `python ollama_chat.py`. This will run the script with all default settings.

2. **Specify ChromaDB client host and port**: If you want to specify the ChromaDB client host and port, you can use the `--chroma-host` and `--chroma-port` arguments. For example, `python ollama_chat.py --chroma-host myhost --chroma-port 1234`.

3. **Specify the ChromaDB collection name**: Use the `--collection` argument to specify the ChromaDB collection name. For example, `python ollama_chat.py --collection mycollection`.

4. **Use Ollama or OpenAI API (Llama-CPP)**: By default, the script uses Ollama. If you want to use the OpenAI API, use the `--use-openai` argument. For example, `python ollama_chat.py --use-openai`.

5. **Set the temperature for the model**: You can set the temperature using the `--temperature` argument. For example, `python ollama_chat.py --temperature 0.8`.

6. **Disable the system role**: If the selected model does not support the system role, like Google Gemma models, use the `--disable-system-role` argument. For example, `python ollama_chat.py --disable-system-role`.

7. **Specify the prompt template for Llama-CPP**: Use the `--prompt-template` argument to specify the prompt template for Llama-CPP. For example, `python ollama_chat.py --prompt-template "ChatML"`.

8. **Specify the path to a JSON file containing additional chatbots**: Use the `--additional-chatbots` argument to specify the path to a JSON file containing additional chatbots. For example, `python ollama_chat.py --additional-chatbots /path/to/chatbots.json`.

9. **Enable verbose mode**: If you want to enable verbose mode, use the `--verbose` argument. For example, `python ollama_chat.py --verbose`.

10. **Specify the sentence embeddings model**: Use the `--embeddings-model` argument to specify the sentence embeddings model to use for vector database queries. For example, `python ollama_chat.py --embeddings-model multi-qa-mpnet-base-dot-v1`.

Remember, all these arguments are optional. If you don't specify them, the script will use the default values.

## How to Specify Custom Chatbot Personalities in JSON Format

1. **description**: This is a brief explanation of the chatbot's purpose. It should be a string that describes what the chatbot is designed to do.

2. **name**: This is the name of the chatbot. It should be a string that uniquely identifies the chatbot.

3. **preferred_model**: This is the model that the chatbot uses to generate responses. It should be a string that specifies the model's name.

4. **system_prompt**: This is the initial prompt that the chatbot uses to start a conversation. It should be a string that describes the chatbot's role and provides some context for the conversation. It can also include a list of possible prompt commands that the chatbot can use.

Here is an example of a JSON object that specifies a custom chatbot personality:

```json
{
    "description": "Chatbot for code-related questions",
    "name": "code",
    "preferred_model": "wizardlm2:latest",
    "system_prompt": "You are a helpful chatbot assistant for software developers. If not specified, assume questions about code and APIs are in TypeScript. Possible chatbot prompt commands: {possible_prompt_commands}"
}
```

This JSON object can be part of a JSON array if you want to specify multiple chatbot personalities.
