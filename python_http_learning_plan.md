# 🐍 Learning HTTP Engineering in Python — A Passion-Project Roadmap

## Your End Goal: Building a RAG System

RAG (Retrieval-Augmented Generation) sits at the intersection of several technologies:
- **HTTP requests** (talking to APIs, models, databases)
- **Data retrieval** (searching, fetching, parsing)
- **Prompt engineering** (structuring context for a model)

This plan builds those skills gradually through mini projects that are fun and tangible.

---

## Phase 1: The Very Basics — Making a Request

### 🎯 Goal
Understand what happens when "the internet happens." Learn the vocabulary: URL, method, headers, status codes, response body.

### 🛠 Tools
- The `requests` library (the friendly, human-readable Python HTTP library)
- A free public API (like JSONPlaceholder or JSONBin)

### 💡 Mini Project Ideas

1. **Quote of the Day App**
   - Fetch a random quote from a free API and print it
   - Learn: GET requests, reading JSON responses, handling basic errors

2. **Weather Checker**
   - Sign up for a free OpenWeatherMap key
   - Fetch current weather for a city the user types in
   - Learn: URL parameters, API keys, parsing JSON

3. **Random Joke Fetcher**
   - Hit an API like https://official-joke-api.appspot.com
   - Print the punchline
   - Learn: chaining responses, reading documentation

### 📚 Concepts to Focus On
- What is a REST API?
- GET vs POST vs PUT vs DELETE (just recognize them for now)
- HTTP status codes (200 = success, 404 = not found, 500 = server broke)
- JSON as the "universal language" of APIs
- Reading API documentation (a critical skill)

### 🧠 Learner Tips
- Print everything. Print the URL, print the status code, print the raw response text. Seeing the actual data demystifies it.
- Use `print(response.json())` liberally in the beginning to understand what an API is actually giving you.
- Don't memorize — look up. Even senior engineers google "how to get query params with requests."

---

## Phase 2: Working with Data — Parsing, Filtering, Storing

### 🎯 Goal
Take API responses and do something interesting with the data. Start thinking like a data processor.

### 🛠 Tools
- `requests`, `json`, basic file I/O, maybe `csv` or `sqlite3`

### 💡 Mini Project Ideas

4. **Movie / Book / Game Finder**
   - Use TheMovieDB or OpenLibrary API
   - Let a user search, filter results (by year, genre, rating), and display them nicely
   - Learn: filtering JSON data, working with nested structures

5. **Crypto / Stock Price Tracker**
   - Fetch prices from CoinGecko or similar free API
   - Save historical data to a CSV or SQLite file
   - Plot a simple chart with `matplotlib` or just display trends
   - Learn: storing data, working with timestamps, simple data visualization

6. **Recipe Collector**
   - Search for recipes by ingredient
   - Save your "favorites" to a local file
   - Learn: basic file persistence, organizing data

### 📚 Concepts to Focus On
- Working with Python dictionaries and lists (your main data shapes)
- JSON structure and nested access
- Basic file I/O (reading/writing text files, CSV)
- Error handling with try/except

### 🧠 Learner Tips
- Print the structure of your JSON response as a tree. Use `pprint` if needed. Understanding the shape of data is 80% of the work.
- Start small. A program that prints one thing perfectly is better than a broken program that does ten things.

---

## Phase 3: Sending Data — POST, Auth, and APIs That Write Back

### 🎯 Goal
Learn to not just read data, but send it. Understand authentication and request bodies.

### 🛠 Tools
- `requests`, understanding of API authentication patterns

### 💡 Mini Project Ideas

7. **Note-Taking CLI App**
   - Build a simple command-line note app
   - Store notes on a free API like JSONBin.io or your own backend
   - Learn: POST requests, sending JSON payloads, API keys

8. **Twitter / Reddit Sentiment Sniffer**
   - Fetch posts from Reddit via their API
   - Send them to a free sentiment analysis API
   - Display results
   - Learn: chaining API calls, working with authentication, rate limits

9. **Simple Form Submitter**
   - Practice sending form data and file uploads to test APIs
   - Learn: multipart/form-data, headers like `Content-Type`

### 📚 Concepts to Focus On
- POST, PUT, PATCH — when and why you send data
- Authentication: API keys, Bearer tokens, OAuth (just the concepts)
- Headers and what they control
- Rate limits and why they exist
- Idempotency (bonus concept — what happens if you send the same request twice?)

### 🧠 Learner Tips
- Learn to use Postman or curl. Seeing requests in those tools builds intuition.
- Read error messages carefully. APIs often tell you exactly what's wrong (missing field, bad token, rate limit hit).

---

## Phase 4: Building Your Own Service — Understanding the Other Side

### 🎯 Goal
Instead of just calling APIs, learn to build a tiny one. This cements your understanding of HTTP from both sides.

### 🛠 Tools
- `Flask` (lightweight) or `FastAPI` (modern, auto-docs)

### 💡 Mini Project Ideas

10. **Your Own Quote / Joke / Fact API**
    - Host a list of quotes/facts in your app
    - Serve them via endpoints like `/quotes/random`
    - Learn: building routes, returning JSON, running a local server

11. **URL Shortener**
    - Accept a long URL, generate a short one, store the mapping
    - Redirect when someone visits the short URL
    - Learn: redirects (301/302), stateful services, basic databases

12. **Simple Poll / Voting App**
    - Create polls, allow people to vote
    - Display results
    - Learn: state management, CRUD operations (Create, Read, Update, Delete)

### 📚 Concepts to Focus On
- What is an endpoint / route?
- Building responses: status codes, headers, JSON bodies
- Running a local server
- Understanding what "API documentation" looks like from the builder's side

### 🧠 Learner Tips
- Run your app and call it with the `requests` library. This is a powerful way to connect the two sides of the web.
- FastAPI gives you a free auto-generated docs page (`/docs`). Use it! It's like a playground for your own API.

---

## Phase 5: The Bridge to RAG — LLM APIs and Async

### 🎯 Goal
Start working with AI/LLM APIs. Learn the patterns that power RAG.

### 🛠 Tools
- `requests` (or `httpx` for async), OpenAI/Claude/Anthropic API keys, or open-source models via Ollama

### 💡 Mini Project Ideas

13. **Chat App (Single Turn)**
    - Take user input, send it to an LLM API, display the response
    - Learn: the structure of LLM API requests (messages, system prompt, temperature)

14. **Summarizer Tool**
    - Fetch an article (from a URL or RSS feed)
    - Send it to an LLM for summarization
    - Learn: sending large payloads, working with context, token limits

15. **Research Assistant Draft**
    - Given a topic, search the web (DuckDuckGo API or SerpAPI)
    - Fetch a few results
    - Send them to an LLM to synthesize a response
    - This is your first step toward RAG!
    - Learn: multi-step workflows, combining search + LLM

### 📚 Concepts to Focus On
- The LLM API contract: system messages, user messages, assistant messages
- Temperature and other generation parameters
- Token limits and context windows
- Streaming responses (getting tokens as they arrive)
- Async/await with `httpx` (for concurrent requests)

### 🧠 Learner Tips
- The LLM API is just another HTTP API. Treat it the same way you treat the weather API — it's just a request and a response.
- Start with the synchronous `requests` library even for LLMs. Async is a separate learning curve.
- Save all your conversations/responses to files. You'll want to analyze them later.

---

## Phase 6: The RAG System

### 🎯 Goal
Build a basic RAG pipeline that retrieves relevant information and augments a model's response.

### 🛠 Tools
- Everything from previous phases + a vector store (like ChromaDB or FAISS), an embedding model

### 💡 Mini Project Ideas

16. **Personal Knowledge Base**
    - Let a user "upload" documents (PDFs, text files, markdown)
    - Embed them using a free embedding API
    - Store vectors in ChromaDB
    - When asked a question, retrieve relevant chunks, send to LLM
    - This is RAG!

17. **Coursework / Study Assistant**
    - Feed it your lecture notes or textbook chapters
    - Ask questions and get answers based on your material
    - Learn: chunking, retrieval quality, evaluating answers

18. **Code Documentation Helper**
    - Index a GitHub repo or documentation site
    - Answer questions about the code
    - Learn: advanced retrieval techniques, chunking strategies

### 📚 Concepts to Focus On
- Embeddings: turning text into numbers
- Vector similarity search: finding "similar" documents
- Chunking strategies: how to break up text
- The RAG pipeline: retrieve → augment → generate
- Evaluation: how to know if your RAG is working well?

---

## General Learning Principles

### 🧭 Mindset
- **Build, don't just watch.** Tutorials give you a false sense of competence. The learning happens when you get stuck and figure it out.
- **Embrace the error messages.** They are your teachers. Read them fully before Googling.
- **Ship broken versions first.** A working-but-ugly program teaches you more than a perfect plan that never runs.
- **Talk about what you built.** Explaining your project (even to yourself) reveals gaps in understanding.

### 🔍 Resource Recommendations
- **Documentation reading:** Get comfortable with [requests.readthedocs.io](https://requests.readthedocs.io) and [httpx.readthedocs.io](https://www.python-httpx.org/)
- **API playgrounds:** [Postman](https://postman.com), [Insomnia](https://insomnia.rest)
- **Free APIs for practice:** JSONPlaceholder, OpenWeatherMap, CoinGecko, TheMovieDB, OpenLibrary, SerpAPI (free tier), DuckDuckGo
- **LLM practice:** Ollama (runs models locally for free), OpenAI playground (small costs)

### ⚠️ Common Beginner Traps
- **Tutorial hell:** Watching/reading without building. Break out by starting a project on day one.
- **Skipping error handling:** Always handle network failures, timeouts, and bad responses.
- **Hardcoding API keys:** Learn about environment variables from the start (`.env` files).
- **Ignoring documentation:** API docs are written for humans. Read them.
- **Comparing yourself to others:** Everyone builds on what they know. You're building the foundation now.

### 📈 Progress Checkpoints
- Can you explain what happens when you type a URL into a browser? → Phase 1 complete
- Can you fetch data from an API, parse it, and filter it? → Phase 2 complete
- Can you send data to an API and handle authentication? → Phase 3 complete
- Can you build and call your own API? → Phase 4 complete
- Can you send a prompt to an LLM and get a response? → Phase 5 complete
- Can you retrieve relevant context and use it to answer a question? → Phase 6 complete

---

## Remember

> "The expert in anything was once a beginner."

You don't need to rush. Spend as long as you need on each phase. The projects are designed so that finishing one makes the next feel natural. By the time you reach RAG, HTTP requests will feel as basic as opening a file — because at that point, they will be.

Happy building! 🚀
