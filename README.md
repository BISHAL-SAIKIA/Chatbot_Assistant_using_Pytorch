# Chatbot_Assistant_using_Pytorch
An AI chatbot built using PyTorch, NLTK, and a custom intents-based NLP model. This assistant classifies user input into predefined intents, supports response generation, and can trigger Python functions (like fetching stocks) based on intent.
⚠️ Currently Under Development: Model improvements, better accuracy, and additional features will be added in future updates.

# 📂 Project Structure
graphql
Copy
Edit
.
├── chatbot.py            # Main chatbot code
├── intents.json          # Dataset containing patterns, intents, and responses
├── chatbot_model.pth     # Trained PyTorch model (saved after training)
├── dimensions.json       # Stores input/output size metadata
└── README.md             # Project documentation


---


---

## 🧠 Features

- **Tokenization & Lemmatization** using NLTK
- **Bag-of-Words** vectorization
- **Feedforward Neural Network** with ReLU, Dropout
- **Custom Intent-to-Function Mapping**
- **Train, Save, Load** model functionality
- **CLI-based interaction loop**

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/chatbot-project.git
cd chatbot-project
```
### 2. Install dependencies
Make sure you have Python 3.7+ and install the required packages:

```bash
pip install numpy torch nltk
```
Also, download NLTK tokenizer resources:
```bash
import nltk
nltk.download('punkt')
nltk.download('wordnet')
```
### 3. Define Your Intents
Edit the intents.json file to define your chatbot's behavior:
```bash
{
  "intents": [
    {
      "tag": "greeting",
      "patterns": ["Hi", "Hello", "Hey"],
      "responses": ["Hello!", "Hi there!", "Greetings!"]
    },
    {
      "tag": "stocks",
      "patterns": ["Show me stocks", "Stock prices?"],
      "responses": ["Here's some stock info!"]
    }
  ]
}
```
### 4. Training the Model
Uncomment the training section in chatbot.py and run:
```bash
assistant = ChatbotAssistant('intents.json', function_mapping={'stocks': get_stocks})
assistant.parse_intents()
assistant.prepare_data()
assistant.train_model(batch_size=8, lr=0.001, epochs=100)
assistant.save_model('chatbot_model.pth', 'dimensions.json')

```

### 🔧 Future Improvements
Add GUI or web interface

Improve intent classification using transformers

Implement contextual memory in conversation

Add multi-language support

