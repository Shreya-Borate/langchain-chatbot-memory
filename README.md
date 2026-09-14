# LangChain Chatbot with Memory

A simple conversational chatbot built using **LangChain** and **Google Gemini**.

The chatbot maintains conversation history so it can understand follow-up questions based on previous messages.

## 🚀 Features

- 🤖 Conversational chatbot using Google Gemini
- 🧠 Maintains conversation history
- 💬 Understands context from previous messages
- 🔄 Interactive command-line interface
- 🔐 Uses environment variables to securely store the API key
- 🐍 Built with Python and LangChain

## 🛠️ Technologies Used

- Python
- LangChain
- Google Gemini
- `langchain-google-genai`
- `python-dotenv`

## 📁 Project Structure

```text
Basic_Chatbot/
│
├── Chatbot.py
├── .gitignore
└── README.md
```

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Shreya-Borate/langchain-chatbot-memory.git
```

### 2. Navigate to the Project

```bash
cd langchain-chatbot-memory
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```powershell
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install langchain-google-genai python-dotenv
```

## 🔑 API Key Setup

Create a `.env` file in the project directory:

```env
GOOGLE_API_KEY=your_google_api_key
```

Replace `your_google_api_key` with your actual Google Gemini API key.

**Important:** Never upload your `.env` file or API key to GitHub.

Add the following to your `.gitignore` file:

```text
.env
venv/
__pycache__/
```

## ▶️ Run the Chatbot

Run the following command:

```bash
python Chatbot.py
```

### Example

```text
You: hi
AI: Hello! How can I help you?

You: which is greater 5 or 7
AI: 7 is greater than 5.

You: multiply bigger number with 2
AI: 14

You: exit
```

Type `exit` to stop the chatbot.

## 🧠 How Conversation Memory Works

The chatbot stores the conversation in a `chat_history` list.

User messages are stored using `HumanMessage`, while AI responses are stored using `AIMessage`.

The complete conversation history is then passed to the model:

```python
result = model.invoke(chat_history)
```

This allows the chatbot to understand the context of previous messages.

### Without Memory

```text
User: Which is greater, 5 or 7?
AI: 7

User: Multiply the bigger number by 2.
AI: Please provide the numbers.
```

The model only receives the latest message and does not know what "bigger number" refers to.

### With Memory

```text
User: Which is greater, 5 or 7?
AI: 7

User: Multiply the bigger number by 2.
AI: 14
```

The model receives the previous conversation along with the new question, allowing it to understand the context.

## 📌 Learning Objective

This project demonstrates the basic concept of **conversation memory in LangChain**.

It shows how an LLM can maintain conversational context by storing previous user and AI messages and passing them back to the model with each new request.

## 🔮 Future Improvements

- Add a Streamlit web interface
- Add persistent chat history
- Store conversations in a database
- Add conversation/session management
- Add streaming responses
- Add support for multiple users
- Improve error handling

## 👩‍💻 Author

**Shreya Borate**

GitHub: [Shreya-Borate](https://github.com/Shreya-Borate)