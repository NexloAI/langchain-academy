
# Dev Container Setup Instructions for LangGraph Project

## Prerequisites

1. **Install Docker Desktop:**
   - [Windows/Mac](https://www.docker.com/products/docker-desktop)
   - Linux: Follow distribution-specific instructions

3. **Install "Remote - Containers" extension in VS Code:**
   - Open VS Code
   - Go to Extensions view (Ctrl+Shift+X or Cmd+Shift+X on Mac)
   - Search for "Remote - Containers"
   - Click "Install"

## Setting Up API Keys

1. **Create a `.env` file in the project root directory:**

   - Copy the `.env.example` file to the project root and rename it to `.env`.

2. **Edit the `.env` file to set your API keys:**

   ```plaintext
   OPENAI_API_KEY=your_openai_api_key_here
   TAVILY_API_KEY=your_tavily_api_key_here