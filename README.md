# VeritasAI (Evidence-Aware AI Assistant)

# Overview
VeritasAI is a small project I built to explore how AI responses can be made more reliable instead of just fluent. Many large language models generate confident answers even when they are not fully correct. The goal of this project is to reduce that problem by grounding responses in real information and adding a simple verification step.

The system combines retrieval (to fetch real-world information) with generation (to produce answers) and then checks how well the answer aligns with the retrieved sources.


# How the System Works

1. The user enters a question in the interface.
2. The backend receives the query.
3. Relevant information is fetched using the Tavily API.
4. The retrieved context is passed to a Groq-based LLM.
5. The model generates a response using this context.
6. The response is analyzed and broken into smaller claims.
7. Each claim is compared with the retrieved sources.
8. A simple trust score is calculated based on how well the answer matches the evidence.
9. The final output includes the answer, sources, and trust score.


# Tech Stack

1. Next.js (frontend + backend)
2. TypeScript
3. Groq API (LLM inference)
4. Tavily API (real-time retrieval)
5. Vercel (deployment)
6. GitHub (version control)

# Project Structure

- `app/page.tsx`  
  Handles the frontend UI and user interaction.

- `app/api/chat/route.ts`  
  Main backend logic. It performs:
  1. Retrieval using Tavily
  2. LLM response generation using Groq
  3. Claim verification and trust scoring

- `.env.local`  
  Stores API keys (not pushed to GitHub).


# My Contribution

I designed and implemented the complete flow of this project:
1. Built the frontend interface
2. Created backend API routes
3. Integrated Tavily for retrieval
4. Integrated Groq for response generation
5. Implemented simple claim verification logic
6. Added trust score calculation
7. Deployed the application


# Setup & Run

1.Clone the repository
```bash
git clone https://github.com/charan3949/veritas-ai-final.git
cd veritas-ai-final

2.Install dependencies
 npm
install

3.Create environment file
 Create a file named .env.local in the root folder and add:
GROQ_API_KEY
TAVILY_API_KEY

4.Run the project
npm
run
dev

5.Open in browser
http://localhost:3000

#Note
This project demonstrates how retrieval (Tavily) and generation (Groq) can be combined with simple verification to improve the reliability of AI responses.
