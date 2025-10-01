# Agent Foundation

A collection of experiments demonstrating various Large Language Model (LLM) capabilities, patterns, and integrations. This project explores multi-model workflows, API integrations, generator-evaluator patterns, and custom tool implementations without relying on heavyweight frameworks.

## 📚 Project Overview

This repository contains four independent Jupyter notebooks, each showcasing different aspects of working with LLMs:

### 1. **Multi-LLM Flow** (`multi_llm_flow.ipynb`)
Demonstrates a chained LLM workflow using Google's Gemini model (gemini-2.0-flash):
- Explore multi-step reasoning and question refinement patterns

### 2. **Comfortable with Different APIs** (`comfortable_with_different_APIs.ipynb`)
Practice working with multiple LLM provider APIs:
- **Google Gemini** - Google's generative AI models
- **DeepSeek** - Advanced reasoning models
- **Groq** - High-performance inference
- Learn the nuances and patterns of different API structures

### 3. **LLMs Generator & Evaluator** (`llms_generator_evaluator.ipynb`)
Implements a generator-evaluator pattern with two different models:
- **OpenAI** as the generator - produces responses to queries
- **Gemini** as the evaluator - validates if responses meet specific criteria
- Automatic retry mechanism: if evaluation fails, re-runs the generator until requirements are met
- Demonstrates quality control and iterative improvement workflows

### 4. **LLMs with Tools** (`llms_with_tools.ipynb`)
Custom tool implementation without frameworks:
- Function calling using OpenAI's native tool API
- Records unknown questions via Pushover notifications
- Demonstrates a personal AI agent that:
  - Answers questions based on LinkedIn profile and summary
  - Stays in character as a specific person
  - Uses tools to record unanswered questions for later review
  - Includes Gradio interface for interactive chat

## 🚀 Getting Started

### Prerequisites

- Python 3.12 or higher
- [UV package manager](https://github.com/astral-sh/uv)

### Installation

1. **Install UV** (if you haven't already):
```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

2. **Clone the repository**:
```bash
git clone <your-repo-url>
cd agent-foundation
```

3. **Install dependencies**:
```bash
uv sync
```

### API Keys Setup

You'll need API keys from the following providers:

1. **OpenAI API Key**
   - Get it from: https://platform.openai.com/api-keys

2. **Google Gemini API Key**
   - Get it from: https://aistudio.google.com/app/apikey

3. **DeepSeek API Key**
   - Get it from: https://platform.deepseek.com/api_keys

4. **Groq API Key**
   - Get it from: https://console.groq.com/keys

5. **Pushover Credentials** (for `llms_with_tools.ipynb` only)
   - Get it from: https://pushover.net/

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_api_key_here
GOOGLE_API_KEY=your_gemini_api_key_here
DEEPSEEK_API_KEY=your_deepseek_api_key_here
GROQ_API_KEY=your_groq_api_key_here
PUSHOVER_TOKEN=your_pushover_token_here
PUSHOVER_USER=your_pushover_user_here
```

**⚠️ Important:** Never commit your `.env` file to version control. Add it to `.gitignore`:
```bash
echo ".env" >> .gitignore
```

## 📖 Usage

Launch Jupyter and run the notebooks cell by cell:

```bash
uv run jupyter notebook
# or
uv run jupyter lab
```

Then open any of the four notebooks and execute cells sequentially to explore each experiment.

### Running Individual Notebooks

- **multi_llm_flow.ipynb** - Start here to understand basic multi-step LLM workflows
- **comfortable_with_different_APIs.ipynb** - Explore different provider APIs
- **llms_generator_evaluator.ipynb** - Learn about quality control patterns
- **llms_with_tools.ipynb** - Advanced: custom tool implementation with Gradio UI

## 🛠️ Dependencies

This project uses the following key dependencies (managed via UV):

- `openai` - OpenAI API client
- `google-generativeai` - Google Gemini API
- `python-dotenv` - Environment variable management
- `gradio` - Interactive web interfaces
- `pypdf` - PDF processing (for personal agent)
- `requests` - HTTP requests (for Pushover notifications)
- `ipykernel` - Jupyter notebook support

See `pyproject.toml` for the complete list.

## 🎯 Learning Objectives

This project demonstrates:

- ✅ Multi-model orchestration and chaining
- ✅ Working with different LLM provider APIs
- ✅ Implementing generator-evaluator patterns for quality control
- ✅ Custom tool/function calling without frameworks
- ✅ Building interactive AI agents with Gradio
- ✅ Iterative refinement and validation workflows
- ✅ Best practices for API key management

## 📁 Project Structure

```
agent-foundation/
├── multi_llm_flow.ipynb                    # Multi-step Gemini workflow
├── comfortable_with_different_APIs.ipynb   # Multi-provider API exploration
├── llms_generator_evaluator.ipynb          # Generator-evaluator pattern
├── llms_with_tools.ipynb                   # Custom tool implementation
├── pyproject.toml                          # UV project configuration
├── .env                                    # API keys (create this, not in repo)
├── .gitignore                              # Git ignore file
└── README.md                               # This file
```

## 🤝 Contributing

This is a learning project. Feel free to fork and experiment with your own LLM patterns!

## 📝 License

[Choose your license - MIT, Apache 2.0, etc.]

## 🔗 Resources

- [OpenAI API Documentation](https://platform.openai.com/docs)
- [Google Gemini API Documentation](https://ai.google.dev/docs)
- [DeepSeek Documentation](https://platform.deepseek.com/docs)
- [Groq Documentation](https://console.groq.com/docs)
- [UV Package Manager](https://github.com/astral-sh/uv)

---

**Note:** This project is for educational and experimental purposes. Always follow API provider terms of service and rate limits.