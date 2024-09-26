# Groq LLM CLI Script

This Python script provides a command-line interface for interacting with Groq's Language Learning Models (LLMs). It allows users to send structured or unstructured input to an LLM and receive streamed responses.

## Features

- Supports direct user prompts or text files containing multiple messages
- Handles structured input with roles like [SYSTEM], [USER], and [ASSISTANT]
- Implements retries with exponential backoff
- Streams responses with a slight delay for improved readability
- Supports output redirection to files

## Installation

1. Ensure you have Python 3.6 or later installed on your system.
2. Clone this repository:
   ```
   git clone https://github.com/gmfunk9/groq_cli.git
   cd groq-llm-cli
   ```
3. Install the required `groq` package:
   ```
   pip install groq
   ```
4. Move into: /usr/local/bin/groq_cli
   ```
   mv groq_cli /usr/local/bin/groq_cli
   ```

## Usage

The script can be used in three main ways:

1. Direct Prompt:
   ```
   groq_cli "your prompt here"
   ```

2. File Input:
   ```
   groq_cli input.txt
   ```

3. File Output:
   ```
   groq_cli input.txt > output.txt
   ```

### Input File Structure

When using a file as input, structure it as follows:

```
[SYSTEM]
System message here

[USER]
User message here

[ASSISTANT]
Assistant response here
```

## Configuration

You can modify the following variables in the script to adjust the behavior:

- `MODEL`: The Groq model to use (default: "llama3-8b-8192")
- `MAX_TOKENS`: Maximum number of tokens in the response (default: 1024)
- `TEMPERATURE`: Controls randomness in output (default: 0.1)
- `TOP_P`: Controls diversity of output (default: 1)
- `MAX_RETRIES`: Number of retry attempts for API calls (default: 3)

## Notes

- The script automatically detects whether the input is a file or a direct prompt.
- Responses are streamed with a slight delay for readability when outputting to a terminal.
- When redirecting output to a file, streaming is disabled for efficient writing.

## Contributing

Contributions to improve the script are welcome! Please feel free to submit a Pull Request.

## Disclaimer

This script is provided as-is, without any warranties. Users are responsible for their usage of the Groq API and should ensure they comply with Groq's terms of service.
