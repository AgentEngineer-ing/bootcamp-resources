# Starter Project Templates

> Ready-to-use project templates to accelerate your agent development

## Available Templates

### 🤖 Basic Conversational Agent
**[simple-chat-agent/](./simple-chat-agent/)**
- Basic OpenAI integration
- Simple conversation flow
- Memory management
- Error handling
- Perfect for beginners

### 📚 RAG-Powered Q&A System
**[rag-qa-system/](./rag-qa-system/)**
- Document ingestion pipeline
- Vector database integration
- Semantic search
- Context-aware responses
- Great for knowledge bases

### 🔧 Multi-Tool Agent
**[multi-tool-agent/](./multi-tool-agent/)**
- Multiple tool integrations
- Function calling patterns
- Tool selection logic
- Result processing
- Ideal for automation tasks

### 👥 Multi-Agent System
**[multi-agent-system/](./multi-agent-system/)**
- Agent coordination patterns
- Message passing protocols
- Role-based specialization
- Task distribution
- Advanced collaboration scenarios

### 🏢 Enterprise Agent Template
**[enterprise-agent/](./enterprise-agent/)**
- Production-ready structure
- Authentication and security
- Monitoring and logging
- Deployment configuration
- CI/CD pipeline setup

## Quick Start Guide

### 1. Choose Your Template
Select the template that best matches your project goals:
- **Learning**: Start with `simple-chat-agent`
- **Document Q&A**: Use `rag-qa-system`
- **Automation**: Choose `multi-tool-agent`
- **Collaboration**: Try `multi-agent-system`
- **Production**: Use `enterprise-agent`

### 2. Copy Template
```bash
# Copy template to your project directory
cp -r templates/starter-projects/simple-chat-agent my-agent-project
cd my-agent-project
```

### 3. Install Dependencies
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install requirements
pip install -r requirements.txt
```

### 4. Configure Environment
```bash
# Copy environment template
cp .env.example .env

# Add your API keys
# Edit .env file with your actual keys
```

### 5. Run the Template
```bash
# Start the agent
python main.py

# Or use the development server
python -m uvicorn app:app --reload
```

## Template Structure

### Standard Directory Layout
```
project-name/
├── README.md              # Project documentation
├── requirements.txt       # Python dependencies
├── .env.example          # Environment variables template
├── .gitignore           # Git ignore patterns
├── main.py              # Entry point
├── config/              # Configuration files
│   ├── __init__.py
│   ├── settings.py      # Application settings
│   └── prompts.py       # Prompt templates
├── src/                 # Source code
│   ├── __init__.py
│   ├── agent.py         # Main agent logic
│   ├── tools.py         # Tool implementations
│   ├── memory.py        # Memory management
│   └── utils.py         # Utility functions
├── tests/               # Test files
│   ├── __init__.py
│   ├── test_agent.py    # Agent tests
│   └── test_tools.py    # Tool tests
└── docs/                # Additional documentation
    ├── api.md           # API documentation
    └── deployment.md    # Deployment guide
```

### Core Components

#### Agent Class Structure
```python
class BaseAgent:
    def __init__(self, config):
        self.config = config
        self.memory = Memory()
        self.tools = ToolManager()
    
    def process_message(self, message):
        # Core processing logic
        pass
    
    def execute_tool(self, tool_name, params):
        # Tool execution logic
        pass
```

#### Configuration Management
```python
# config/settings.py
from pydantic import BaseSettings

class Settings(BaseSettings):
    openai_api_key: str
    model_name: str = "gpt-4"
    max_tokens: int = 1000
    temperature: float = 0.7
    
    class Config:
        env_file = ".env"
```

## Customization Guide

### Adding New Tools
1. Define tool function in `src/tools.py`
2. Add tool description for LLM
3. Register tool in ToolManager
4. Add tests in `tests/test_tools.py`

### Modifying Prompts
1. Edit prompt templates in `config/prompts.py`
2. Use Jinja2 templates for dynamic content
3. Test prompt variations
4. Document prompt changes

### Extending Memory
1. Choose memory backend (Redis, PostgreSQL, etc.)
2. Implement memory interface
3. Add persistence logic
4. Configure memory settings

### Adding Authentication
1. Choose auth method (API keys, OAuth, etc.)
2. Add middleware in FastAPI
3. Implement user management
4. Secure sensitive endpoints

## Template Details

### Simple Chat Agent
**Best for**: Learning, prototyping, basic conversations
```python
# Key features
- OpenAI integration
- Basic memory
- Simple conversation flow
- Error handling
- Logging
```

### RAG Q&A System
**Best for**: Document search, knowledge bases, research
```python
# Key features
- Document ingestion
- Vector embeddings
- Semantic search
- Context injection
- Source attribution
```

### Multi-Tool Agent
**Best for**: Automation, API integration, complex tasks
```python
# Key features
- Multiple tool support
- Function calling
- Tool selection logic
- Result aggregation
- Error recovery
```

### Multi-Agent System
**Best for**: Complex workflows, specialization, collaboration
```python
# Key features
- Agent orchestration
- Message passing
- Role assignment
- Task delegation
- Coordination protocols
```

### Enterprise Agent
**Best for**: Production deployment, scalability, security
```python
# Key features
- Authentication & authorization
- Monitoring & observability
- Horizontal scaling
- Database integration
- CI/CD pipeline
```

## Best Practices

### Development Workflow
1. **Start Small** - Begin with basic template
2. **Iterate Quickly** - Add features incrementally
3. **Test Early** - Write tests as you develop
4. **Document Changes** - Keep README updated

### Code Quality
- Follow PEP 8 style guidelines
- Use type hints consistently
- Write descriptive docstrings
- Implement proper error handling

### Security Considerations
- Never commit API keys
- Validate all inputs
- Implement rate limiting
- Use secure communication

### Performance Optimization
- Cache frequently accessed data
- Optimize prompt engineering
- Monitor token usage
- Implement request batching

## Getting Help

### Common Issues
- **Import Errors** - Check virtual environment activation
- **API Errors** - Verify API key configuration
- **Memory Issues** - Ensure proper cleanup
- **Tool Failures** - Add error handling and retries

### Resources
- [Template Documentation](../complete-examples/)
- [Code Examples](../code-snippets/)
- [Best Practices Guide](../../by-topic/project-management/best-practices/)
- [Troubleshooting Guide](../../tech-stack.md#troubleshooting)

---

**Ready to Start Building?**
1. Choose your template
2. Follow the setup guide
3. Customize for your needs
4. Deploy and iterate

These templates provide a solid foundation for your agent development journey!