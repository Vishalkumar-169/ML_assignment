This code builds a simple AI sales chatbot using a structured workflow with LangGraph. The system starts by loading a knowledge base from a JSON file and converting it into vector embeddings using a HuggingFace model. These embeddings are stored in FAISS, which allows the chatbot to retrieve relevant information when the user asks questions, especially about pricing (this is the RAG pipeline).

When a user enters a message, the intent_node analyzes the text using keyword-based rules to classify it into one of four categories: greeting, pricing, lead, or general. Based on this intent, the LangGraph routes the conversation to the appropriate node. For example, pricing questions go to the pricing_node, which returns predefined plan details, while greeting messages get a simple welcome response.

The chatbot also maintains a shared state (using a dictionary) to store user information like name, email, and platform. The lead_node ensures that missing details are collected step by step. Once all required information is gathered, the tool_node simulates capturing the lead by printing the details.

The entire system runs in a loop, continuously taking user input, updating the state, and generating responses, creating a smooth conversational experience.
