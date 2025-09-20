# Development Tools

> Essential tools for agent engineering development workflow

## Code Editors & IDEs

### VS Code (Recommended)
**Why VS Code**: Excellent Python support, extensive extensions, integrated terminal

**Essential Extensions:**
- **Python** - Official Python language support
- **Pylance** - Advanced Python language server
- **GitLens** - Enhanced Git capabilities
- **Thunder Client** - API testing within VS Code
- **Docker** - Container development support
- **GitHub Copilot** - AI-powered code completion

**Configuration:**
```json
// settings.json
{
    "python.defaultInterpreterPath": "./venv/bin/python",
    "python.linting.enabled": true,
    "python.linting.pylintEnabled": true,
    "python.formatting.provider": "black",
    "editor.formatOnSave": true
}
```

### PyCharm
**When to Use**: Heavy Python development, advanced debugging needs

**Features:**
- Intelligent code completion
- Advanced debugging tools
- Database integration
- Built-in version control

### Cursor (AI-Enhanced)
**When to Use**: AI-assisted development, rapid prototyping

**Features:**
- AI code generation
- Natural language programming
- Context-aware suggestions
- Integrated chat interface

## Version Control

### Git Essentials
**Basic Workflow:**
```bash
# Initialize repository
git init
git add .
git commit -m "Initial commit"

# Branch management
git checkout -b feature/new-agent
git add .
git commit -m "Add new agent functionality"
git push origin feature/new-agent
```

**Useful Git Commands:**
```bash
# Check status
git status

# View differences
git diff

# Undo changes
git checkout -- filename.py

# Reset to previous commit
git reset --hard HEAD~1

# Interactive rebase
git rebase -i HEAD~3
```

### GitHub Features
- **Issues** - Bug tracking and feature requests
- **Pull Requests** - Code review and collaboration
- **Actions** - CI/CD automation
- **Projects** - Task management

## Package Management

### pip (Standard)
```bash
# Install packages
pip install langchain openai anthropic

# Install from requirements
pip install -r requirements.txt

# Generate requirements
pip freeze > requirements.txt

# Install in development mode
pip install -e .
```

### pipenv (Environment + Packages)
```bash
# Create environment and install
pipenv install langchain openai

# Activate environment
pipenv shell

# Install dev dependencies
pipenv install pytest --dev

# Generate lock file
pipenv lock
```

### conda (Data Science Focused)
```bash
# Create environment
conda create -n agent-env python=3.9

# Activate environment
conda activate agent-env

# Install packages
conda install numpy pandas
pip install langchain
```

## Testing & Quality Tools

### pytest (Testing Framework)
```python
# test_agent.py
import pytest
from src.agent import ChatAgent

def test_agent_response():
    agent = ChatAgent()
    response = agent.process_message("Hello")
    assert response is not None
    assert len(response) > 0

@pytest.fixture
def agent():
    return ChatAgent(config={"model": "gpt-3.5-turbo"})

def test_agent_with_fixture(agent):
    response = agent.process_message("Test")
    assert "error" not in response.lower()
```

**Running Tests:**
```bash
# Run all tests
pytest

# Run specific test file
pytest tests/test_agent.py

# Run with coverage
pytest --cov=src

# Run with verbose output
pytest -v
```

### Code Formatting & Linting

#### Black (Code Formatter)
```bash
# Format all Python files
black .

# Check what would be formatted
black --check .

# Format specific file
black src/agent.py
```

#### flake8 (Linter)
```bash
# Check code quality
flake8 src/

# With specific rules
flake8 --max-line-length=88 --ignore=E203,W503 src/
```

#### mypy (Type Checker)
```bash
# Type check
mypy src/

# With strict mode
mypy --strict src/
```

### Pre-commit Hooks
```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/psf/black
    rev: 22.3.0
    hooks:
      - id: black
  - repo: https://github.com/pycqa/flake8
    rev: 4.0.1
    hooks:
      - id: flake8
  - repo: https://github.com/pre-commit/mirrors-mypy
    rev: v0.950
    hooks:
      - id: mypy
```

## Debugging Tools

### Python Debugger (pdb)
```python
import pdb

def problematic_function():
    x = 10
    y = 0
    pdb.set_trace()  # Breakpoint
    result = x / y
    return result
```

**Debugger Commands:**
- `n` - Next line
- `s` - Step into function
- `c` - Continue execution
- `l` - List code
- `p variable_name` - Print variable
- `q` - Quit debugger

### VS Code Debugger
```json
// launch.json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Python: Current File",
            "type": "python",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal"
        }
    ]
}
```

### Logging Setup
```python
import logging

# Configure logging
logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    handlers=[
        logging.FileHandler('agent.log'),
        logging.StreamHandler()
    ]
)

logger = logging.getLogger(__name__)

# Use in code
logger.info("Agent started")
logger.error("Failed to process message", exc_info=True)
```

## API Development & Testing

### FastAPI Development
```python
# main.py
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI(title="Agent API", version="1.0.0")

app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)

@app.post("/chat")
async def chat_endpoint(message: str):
    # Agent logic here
    return {"response": "Hello from agent"}

# Run with: uvicorn main:app --reload
```

### API Testing Tools

#### Thunder Client (VS Code)
- Built into VS Code
- REST client with collections
- Environment variables support
- Response history

#### Postman
- Comprehensive API testing
- Team collaboration features
- Automated testing scripts
- Mock servers

#### curl (Command Line)
```bash
# GET request
curl -X GET "http://localhost:8000/health"

# POST request with JSON
curl -X POST "http://localhost:8000/chat" \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello agent"}'

# With authentication
curl -X POST "http://localhost:8000/chat" \
  -H "Authorization: Bearer your-token" \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello"}'
```

## Environment Management

### Virtual Environments
```bash
# Create virtual environment
python -m venv agent-env

# Activate (Linux/Mac)
source agent-env/bin/activate

# Activate (Windows)
agent-env\Scripts\activate

# Deactivate
deactivate

# Remove environment
rm -rf agent-env
```

### Environment Variables
```bash
# .env file
OPENAI_API_KEY=your_key_here
ANTHROPIC_API_KEY=your_key_here
DATABASE_URL=postgresql://user:pass@localhost/db
DEBUG=True

# .env.example (template)
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key
DATABASE_URL=your_database_url
DEBUG=False
```

```python
# Loading environment variables
from dotenv import load_dotenv
import os

load_dotenv()

openai_key = os.getenv("OPENAI_API_KEY")
debug_mode = os.getenv("DEBUG", "False").lower() == "true"
```

## Performance & Monitoring

### Memory Profiling
```python
# memory_profiler
from memory_profiler import profile

@profile
def memory_intensive_function():
    # Function implementation
    pass

# Run with: python -m memory_profiler script.py
```

### Performance Timing
```python
import time
from functools import wraps

def timer(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"{func.__name__} took {end - start:.2f} seconds")
        return result
    return wrapper

@timer
def slow_function():
    time.sleep(1)
    return "Done"
```

## Development Workflow

### Project Setup Checklist
- [ ] Create virtual environment
- [ ] Install dependencies
- [ ] Set up environment variables
- [ ] Configure git repository
- [ ] Set up pre-commit hooks
- [ ] Write initial tests
- [ ] Configure IDE/editor
- [ ] Set up debugging configuration

### Daily Development Workflow
1. **Start**: Activate virtual environment
2. **Code**: Write and test incrementally
3. **Test**: Run tests frequently
4. **Commit**: Make atomic commits
5. **Review**: Check code quality
6. **Document**: Update documentation

### Code Review Checklist
- [ ] Code follows style guidelines
- [ ] Tests are included and passing
- [ ] Documentation is updated
- [ ] No sensitive information exposed
- [ ] Error handling is appropriate
- [ ] Performance considerations addressed

---

**Tool Recommendations by Experience Level:**

**Beginner:**
- VS Code with Python extension
- Git basics
- pip for package management
- pytest for testing

**Intermediate:**
- Add linting (flake8) and formatting (black)
- Use virtual environments consistently
- Implement logging
- Learn debugging tools

**Advanced:**
- Set up pre-commit hooks
- Use type checking (mypy)
- Implement comprehensive testing
- Add performance monitoring