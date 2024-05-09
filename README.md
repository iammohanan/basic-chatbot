import random

# Define responses for different types of user inputs
responses = {
    "hi": ["Hello!", "Hey there!", "Hi! How can I help you today?"],
    "how are you": ["I'm doing well, thank you.", "I'm great, thanks for asking!"],
    "what is your name": ["You can call me Chatbot.", "I go by the name Chatbot."],
    "quit": ["Goodbye!", "It was nice talking to you. Take care!"],
    "default": ["I'm sorry, I don't understand that.", "Could you please rephrase that?"]
}

def chatbot_response(user_input):
    # Convert user input to lowercase for easier comparison
    user_input = user_input.lower()
    
    # Check if user input matches any predefined responses
    for key in responses:
        if key in user_input:
            return random.choice(responses[key])
    
    # If no match found, return a default response
    return random.choice(responses["default"])

def main():
    print("Welcome! Type 'quit' to exit.")
    while True:
        user_input = input("You: ")
        response = chatbot_response(user_input)
        print("Chatbot:", response)
        if user_input.lower() == "quit":
            break

if __name__ == "__main__":
    main()
