# Epblproject```
import nltk
from nltk.tokenize import word_tokenize
from nltk.stem import WordNetLemmatizer
nltk.download('punkt')
nltk.download('wordnet')

Define intents and responses
intents = {
    'greeting': ['hello', 'hi', 'hey'],
    'goodbye': ['bye', 'see you later'],
    'help': ['support', 'assistance']
}

responses = {
    'greeting': 'Hello! How can I assist you?',
    'goodbye': 'Goodbye! Have a great day.',
    'help': 'What do you need help with?'
}

def process_query(query):
    tokens = word_tokenize(query.lower())
    lemmatizer = WordNetLemmatizer()
    tokens = [lemmatizer.lemmatize(token) for token in tokens]

    for intent, keywords in intents.items():
        if any(keyword in tokens for keyword in keywords):
            return responses[intent]

    return "I didn't understand that. Can you please rephrase?"

Test the chatbot
queries = [
    "Hello",
    "I need some assistance",
    "Bye"
]

for query in queries:
    print(f"User: {query}")
    print(f"Chatbot: {process_query(query)}")
    print()
```
