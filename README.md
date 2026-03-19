
# Development and Deployment of a 'Chat with LLM' Application Using the Gradio Blocks Framework

## AIM:
To design and deploy a "Chat with LLM" application by leveraging the Gradio Blocks UI framework to create an interactive interface for seamless user interaction with a large language model.

## PROBLEM STATEMENT:
Develop a user-friendly chatbot application using a large language model (LLM) to assist users with queries and generate conversational responses. The application should feature a responsive design, real-time text exchange, and customizable settings for response quality.
## DESIGN STEPS:

## STEP 1:Set Up the Environment
Install the necessary libraries (openai, gradio) and verify API access to the LLM.

## STEP 2: Create the Chat Functionality
Write a function to interact with the LLM using OpenAI's API (or another preferred LLM provider).

## STEP 3: Design the Gradio Blocks Interface
Use Gradio Blocks to build a structured, multi-component UI with features like:
A text box for user input.
A chat history display.
A clear button to reset the conversation. 

Step 4: Deploy and Test
Host the Gradio app locally or on a server.
Test with diverse inputs to ensure robust performance.


## PROGRAM:
```python
import gradio as gr
import openai
import os

# Load OpenAI API key securely
openai.api_key = os.getenv("OPENAI_API_KEY")  # Make sure the environment variable is set

def chat_with_llm(user_input):
    try:
        response = openai.ChatCompletion.create(
            model="gpt-4",
            messages=[{"role": "user", "content": user_input}]
        )
        return response["choices"][0]["message"]["content"]
    except Exception as e:
        return f"Error: {str(e)}"

# Create Gradio interface
interface = gr.Interface(
    fn=chat_with_llm,
    inputs="text",
    outputs="text",
    title="Chat with GPT-4",
    description="Ask any question and get a response from GPT-4."
)

# Launch the app
interface.launch(share="True")
```

## OUTPUT:
![i](https://github.com/DHARSHANV7/genai-chat-llm-gradio/blob/ca9323831d6682a13e6c4a03a7d431308dbe639f/img3.png)
![i](https://github.com/DHARSHANV7/genai-chat-llm-gradio/blob/62a7989442e7bdc3003ccef0ed8482c7f044da0e/img4.png)


## RESULT:

The "Chat with LLM" application successfully enables interactive text-based communication with a large language model, offering a streamlined and visually appealing interface for users.
