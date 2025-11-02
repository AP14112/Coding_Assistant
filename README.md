#  CodeMaster AI – Local Code Assistant

CodeMaster AI is a lightweight Gradio web app that connects to a locally hosted AI model to help you generate and understand code in a simple chat interface.

## ✅ Features

- 💬 Chat-style interface for coding questions  
- 🧠 Remembers previous conversation context  
- ⚡ Uses a local AI model (`codemaster`) via `http://localhost:11434/api/generate`  
- 🖥️ Simple and clean Gradio UI  

## 📁 Project Structure

```
.
├── app.py          # Main application
├── requirements.txt # Dependencies
└── modelfile       # Model configuration for CodeMaster
```

## 🛠️ How It Works

- Each user prompt is stored in a `history` list to maintain chat context.  
- The conversation is sent to the local API in JSON format.  
- The model’s reply is processed and shown in the Gradio interface.

## ▶️ Run the App

### 1. Install dependencies:
```bash
pip install -r requirements.txt
```

### 2. Make sure your model backend is running:
Example using Ollama:
```bash
ollama serve
```

### 3. Run the app:
```bash
python app.py
```

### 4. Open the link shown in the terminal to start chatting!

## ⚙️ Model Configuration (`modelfile`)

```
FROM codellama
FROM codemaster

PARAMETER num_ctx 2048
PARAMETER temperature 0.7

SYSTEM """
You are a code teaching assistant that answers and briefly explains all coding-related queries in a crisp and clear manner.
"""
```

## 💡 Example Prompts

```
Explain bubble sort in Python.  
Write a C++ function to reverse a string.  
What's the difference between an array and a linked list?
```

## 🛑 Troubleshooting

| Issue                         | Solution                                         |
|------------------------------|--------------------------------------------------|
| No response / API error      | Ensure backend model server is running at port 11434 |
| Model not found              | Check if `codemaster` is installed in Ollama    |
| Gradio not starting          | Run `pip install -r requirements.txt`           |

## 🤝 Contribute

Feel free to improve this project — UI, backend logic, or model setup. Pull requests are welcome!

## 📜 License

Open for personal, educational, or experimental use. Modify as needed.
