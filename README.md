# 📚 CTSE Lecture Notes Chatbot 🤖

An AI-powered chatbot that answers questions about **Current Trends in Software Engineering (CTSE)** lecture notes using Retrieval-Augmented Generation (RAG) with free LLMs.

[![Python Version](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-0.1.0-orange)](https://python.langchain.com/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

![Chatbot Demo](demo.gif) <!-- Replace with your demo GIF -->

## 🚀 Features

- **RAG Pipeline**: Combines retrieval with generation for accurate answers
- **Hardware-Aware**: Automatically selects models based on available GPU/CPU
- **Multi-Format Support**: Processes both PDF and text lecture notes
- **Source Citation**: Shows which lecture notes provided the answer
- **Interactive UI**: Jupyter notebook widget for easy Q&A

## 📦 Installation

### Prerequisites
- Python 3.9+
- pip package manager
- (Optional) NVIDIA GPU with CUDA for faster processing

### Step-by-Step Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Sathiradissanayaka45/CTSE_Lecture_Notes_Chatbot.git
   cd CTSE_Lecture_Notes_Chatbot
   ```

2. **Create and activate virtual environment (recommended)**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Add your lecture notes**:
   - Place PDF/text files in the `./data` directory
   - Or use the sample notes provided

## 🖥️ Usage

1. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

2. **Open CTSE_Chatbot.ipynb**
   - Run all cells sequentially

3. **Interact with the chatbot**:
   - Type questions in the input box
   - Click "Ask" to get answers
   - Use "Clear History" to restart conversation

4. **Add new documents dynamically**:
   ```python
   load_new_document("path/to/your/lecture_notes.pdf")
   ```

## 🛠️ Technical Architecture

### Key Components

- **Document Processing**:
  - Uses PyPDFLoader and TextLoader
  - Splits documents with RecursiveCharacterTextSplitter

- **Vector Database**:
  - FAISS for efficient similarity search
  - sentence-transformers/all-MiniLM-L6-v2 embeddings

- **Language Models**:
  - Default: Mistral-7B (with GPU)
  - Fallback: TinyLlama (CPU)
  - Customizable prompt template

## 📂 Project Structure
```
CTSE_Lecture_Notes_Chatbot/
├── data/                   # Lecture notes storage
├── vectorstore/            # Saved FAISS index
├── CTSE_Chatbot.ipynb      # Main notebook
├── requirements.txt        # Dependencies
├── LICENSE
└── README.md
```

## 🧪 Testing

Try these sample questions:
- "What are the key aspects of agile development?"
- "Explain RAG in the context of LLMs"
- "How does CI/CD work in DevOps?"

## 🚨 Troubleshooting

### Common Issues
- **CUDA Out of Memory**: Try smaller model (edit `model_name` in notebook)
- **PDF Loading Errors**: Ensure files aren't password-protected
- **Slow Performance**: Use `use_4bit=True` for GPU users

## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments
- LangChain for RAG framework
- HuggingFace for models and embeddings
- SE4010 course for the project inspiration

## 🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
