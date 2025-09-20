# Tech Stack & Development Environment

> Essential tools, frameworks, and setup instructions for the Agent Engineering Bootcamp

## Required Development Environment

### Programming Languages
- **Python 3.8+** - Primary language for agent development
- **JavaScript/TypeScript** - Web interfaces and client-side logic
- **Shell/Bash** - Automation and scripting

### Core Development Tools

#### Code Editors & IDEs
- **VS Code** (Recommended) - With Python, AI, and Git extensions
- **PyCharm** - Alternative for Python-heavy projects
- **Cursor** - AI-powered coding assistant

#### Version Control
- **Git** - Version control system
- **GitHub** - Repository hosting and collaboration

#### Package Managers
- **pip/pipenv** - Python package management
- **npm/yarn** - Node.js package management
- **conda** - Alternative Python environment management

## AI/ML Framework Stack

### Language Model APIs
- **OpenAI API** - GPT models and embeddings
- **Anthropic Claude** - Advanced reasoning and safety
- **Google Gemini** - Multimodal capabilities
- **Cohere** - Enterprise-focused models

### Agent Development Frameworks
- **LangChain** - Comprehensive agent framework
- **LlamaIndex** - Data ingestion and RAG
- **AutoGen** - Multi-agent conversations
- **CrewAI** - Role-based agent teams

### Vector Databases & Search
- **Pinecone** - Managed vector database
- **Weaviate** - Open-source vector search
- **Chroma** - Lightweight embedding database
- **FAISS** - Facebook's similarity search

## Backend & Infrastructure

### Databases
- **PostgreSQL** - Primary relational database
- **Redis** - Caching and session storage
- **MongoDB** - Document storage for unstructured data

### Web Frameworks
- **FastAPI** - Python web API framework
- **Flask** - Lightweight Python web framework
- **Express.js** - Node.js web framework

### Cloud & Deployment
- **Docker** - Containerization
- **AWS/GCP/Azure** - Cloud platforms
- **Vercel/Netlify** - Frontend deployment
- **Railway/Render** - Backend deployment

## Development Workflow Tools

### Testing & Quality
- **pytest** - Python testing framework
- **black** - Python code formatting
- **flake8** - Python linting
- **mypy** - Python type checking

### Documentation
- **Sphinx** - Python documentation
- **MkDocs** - Markdown documentation
- **Jupyter Notebooks** - Interactive development

### Monitoring & Debugging
- **LangSmith** - LangChain debugging
- **Weights & Biases** - ML experiment tracking
- **Sentry** - Error tracking

## Setup Instructions

### 1. Python Environment
```bash
# Install Python 3.8+
python --version

# Create virtual environment
python -m venv agent-env
source agent-env/bin/activate  # On Windows: agent-env\Scripts\activate

# Install core packages
pip install langchain openai anthropic python-dotenv fastapi uvicorn
```

### 2. Node.js Environment
```bash
# Install Node.js 16+
node --version

# Install global tools
npm install -g typescript ts-node nodemon
```

### 3. Environment Configuration
```bash
# Create .env file
cp .env.example .env

# Add your API keys
OPENAI_API_KEY=your_key_here
ANTHROPIC_API_KEY=your_key_here
PINECONE_API_KEY=your_key_here
```

### 4. VS Code Extensions (Recommended)
- Python
- Pylance
- GitLens
- Thunder Client
- Docker
- GitHub Copilot

## Quick Start Checklist

- [ ] Python 3.8+ installed
- [ ] Node.js 16+ installed
- [ ] VS Code with extensions
- [ ] Git configured
- [ ] Virtual environment created
- [ ] Core packages installed
- [ ] API keys configured
- [ ] Docker installed (optional)

## Troubleshooting

### Common Issues
1. **Python version conflicts** - Use pyenv or conda for version management
2. **Package installation errors** - Upgrade pip: `pip install --upgrade pip`
3. **API key errors** - Verify keys in .env file and restart terminal
4. **Import errors** - Activate virtual environment before running code

### Getting Help
- Check the [troubleshooting guide](./troubleshooting.md)
- Ask in the bootcamp Discord/Slack
- Review error logs and stack traces
- Search GitHub issues for similar problems

---

**Last Updated**: September 19, 2025