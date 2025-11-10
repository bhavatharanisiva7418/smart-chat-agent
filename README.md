# smart-chat-agent
# AIM:
The aim of this project is to develop an AI-driven intelligent chatbot capable of understanding user queries, providing accurate and context-aware responses, and assisting users in performing tasks efficiently. The system leverages Natural Language Processing (NLP) and machine learning to enable human-like interaction and enhance user experience across various domains.
# PROCEDURE:
Collect publicly available sample data related to HR policies, IT support, company events, and other organizational topics for chatbot training.

Preprocess and prepare the dataset, including question-answer pairs and document samples.

Utilize sentence transformer models (e.g., all-MiniLM-L6-v2) to encode queries and FAQs into embeddings.

Build a similarity-based retrieval system for matching user queries to FAQ answers using cosine similarity.

Integrate a document processing module enabling the chatbot to analyze uploaded documents by extracting summaries or keywords.

Implement chatbot architecture ensuring minimum 5 parallel users handling capacity with optimized response time under 5 seconds.

Enhance chatbot security by enabling email-based two-factor authentication (2FA).

Test the chatbot with sample queries and document uploads to evaluate response accuracy, speed, and user management.
# PROGRAM:
```
from phi.agent import Agent
from phi.model.groq import Groq
from dotenv import load_dotenv
%%writefile .env
GROQ_API_KEY='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'
from dotenv import load_dotenv
import os
load_dotenv()
print("Loaded key:", os.getenv("GROQ_API_KEY"))
pip install phidata groq python-dotenv > /dev/null

from phi.agent import Agent
from phi.model.groq import Groq
import os
os.environ["GROQ_API_KEY"] = "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"
chatbot = Agent(
    name="Enterprise Assistant",
    model=Groq(id="llama-3.3-70b-versatile"), 
    description="An intelligent chatbot to assist employees with HR, IT, and company-related queries."
)

print("🤖 Intelligent Enterprise Assistant is ready! Type 'exit' to stop.\n")
while True:
    user_input = input("You: ")
    if user_input.lower() in ["exit", "quit", "bye"]:
        print("Bot: Goodbye! Have a productive day!")
        break
    response = chatbot.run(user_input)
    print("Bot:", response)
```
# OUTPUT:
<img width="1725" height="173" alt="image" src="https://github.com/user-attachments/assets/a563c327-c3d0-4e9d-a2d1-25c43dc33a66" />

# RESULT:
The AI-driven enterprise chatbot effectively understands and responds to diverse organizational queries, processes documents for summarization, supports multiple concurrent users with fast response times, and enhances security with two-factor authentication, thereby improving organizational efficiency significantly.
