## MEDICAL INSIGHT AI

This Streamlit application utilizes Google's Gemini Pro Vision API to analyze medical conditions based on uploaded images and input prompts.

### Setup

Before running the app, ensure you have set up your environment variables using dotenv.

```python
from dotenv import load_dotenv

load_dotenv()  # Load all the environment variables
```

### Libraries Used

- `streamlit`: For creating the web application interface.
- `google.generativeai`: API integration for using Google's Gemini Pro Vision model.
- `PIL`: Python Imaging Library for handling image data.

### Functions

#### `get_gemini_response(input_text, image, prompt)`

Function to query Google's Gemini Pro Vision API and retrieve a response based on input text, uploaded image, and a default input prompt.

#### `input_image_setup(uploaded_file)`

Prepares the uploaded image for processing by converting it into bytes and extracting MIME type information.

#### `manage_chat(user_input, response)`

Stores user-bot chat interactions in the session state to maintain a chat history.

### Streamlit App Initialization

The app is configured with a specific page title and header:

```python
st.set_page_config(page_title="Medical Health AI")
st.header("Gemini Health App")
```

### Interface Components

- **Input Prompt**: Allows users to provide text prompts for the AI analysis.
- **Image Uploader**: Enables users to upload images (JPEG, JPG, PNG) for health condition analysis.
- **Analyze Health Condition Button**: Triggers the analysis based on the uploaded image and input prompt.

### Default Input Prompt

If no specific prompt is provided, a default prompt is used:

```python
default_input_prompt = """
You are a medical professional. Using the uploaded image and the input description, analyze the overall health condition of the patient. 
Provide a detailed report that includes the following:

1. Identify visible symptoms or conditions.
2. Discuss potential diagnoses based on visual cues.
3. Recommend further medical tests or actions.
4. Suggest general health advice and preventive measures.
5. Mention any urgent signs that require immediate medical attention.

Ensure the analysis is thorough and accurate.
"""
```

### Analyzing Health Condition

Upon clicking the "Analyze Health Condition" button, the app processes the uploaded image and displays the AI's response.

### Chat Feature

Users can engage in a chat with the AI to discuss the analysis or ask additional questions. The chat history is preserved during the session.

### Example Interaction

The app maintains a session state to track the chat history and previous responses for a seamless user experience.

---
