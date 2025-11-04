# AI-Powered Customer Experience Platform

This project is a full-stack proof-of-concept demonstrating an AI-Powered Customer Experience (CX) platform. It features real-time analytics, an AI assistant for dynamic support, and conceptual modules for immersive technologies like AR and live video support.

The AI assistant is powered by the Google Generative AI (Gemini) API, specifically configured as a stock broker AI for demonstration purposes.

## Key Features

- **Gemini AI Chat Backend**: An Express server (`server.js`) that handles API requests and interacts with the gemini-1.5-flash model.
- **Specialized AI Persona**: The AI is initialized with a system prompt to function as a stock broker AI giving a solution for the stock market.
- **API Resilience**: Includes rate limiting (10 requests per minute) and retry logic with exponential backoff to handle transient API errors and service unavailability.
- **Interactive Frontend**: A single-page HTML dashboard with dynamic sections for Analytics, AI Assistant, and Immersive Experience.
- **Immersive Concepts**: JavaScript functions to simulate AR Product Visualization and demonstrate Video Customer Support using the browser's getUserMedia API.

## ⚙️ Setup and Installation

Follow these steps to get the project running on your local machine.

### 1. Prerequisites

You must have Node.js (version 18 or later) installed and a Google Generative AI (Gemini) API Key.

### 2. Clone the Repository

```bash
git clone YOUR_REPO_URL
cd ai-customer-experience-platform
```

### 3. Install Dependencies

Install the required Node.js packages:

```bash
npm install
```

### 4. Configure Your API Key

Create a file named `.env` in the root directory of the project and add your Gemini API key:

```code
GEMINI_API_KEY=YOUR_GEMINI_API_KEY_HERE
```

 **Security Warning**: The `.gitignore` file is set up to ignore the `.env` file, ensuring your key is never committed to GitHub.

### 5. Start the Backend Server

Run the server using the start script defined in `package.json`:

```bash
npm start
```

The server will start on port 3000:

```
AI chatbot backend listening at http://localhost:3000
```

### 6. Access the Platform

Open the `index.html` file directly in your web browser.

Once the frontend is loaded, navigate to the "AI Assistant" tab to interact with the chatbot powered by your running server.

## API Endpoints

The Express server exposes the following endpoints on `http://localhost:3000`:

| Endpoint    | Method | Description                                                                              | Request Body            |
| ----------- | ------ | ---------------------------------------------------------------------------------------- | ----------------------- |
| `/chat`     | POST   | Primary chat endpoint. Sends the user message to the Gemini AI and returns the response. | `{"message": "string"}` |
| `/health`   | GET    | Simple server health check.                                                              | N/A                     |
| `/test-api` | GET    | Verifies connectivity with the Google Generative AI API.                                 | N/A                     |

##  Testing Your Setup

You can verify your API key and setup using the dedicated test script:

```bash
node test.js
```

This script attempts a basic call to the Gemini API and will confirm if your key and model setup are functional.
