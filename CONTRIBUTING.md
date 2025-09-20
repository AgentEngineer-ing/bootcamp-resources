# Contributing to Agent Engineering Bootcamp Resources

Welcome! We're excited to have you contribute to our bootcamp resources. This guide will help you add valuable content that benefits all students and the broader community.

## How to Contribute

### Types of Contributions We Welcome

1. **📚 Learning Resources**
   - Articles and tutorials
   - Code examples and snippets
   - Project templates
   - API/SDK documentation

2. **🛠️ Tools & Utilities**
   - Helpful scripts and automation
   - Development environment configs
   - Testing frameworks
   - Debugging tools

3. **📝 Documentation**
   - README improvements
   - Setup guides
   - Troubleshooting guides
   - Best practices

4. **🐛 Bug Fixes**
   - Broken links
   - Outdated information
   - Code errors
   - Formatting issues

## Contribution Process

### 1. Fork & Clone
```bash
# Fork the repository on GitHub
# Then clone your fork
git clone https://github.com/YOUR_USERNAME/bootcamp-resources.git
cd bootcamp-resources
```

### 2. Create a Branch
```bash
# Create a descriptive branch name
git checkout -b add-langchain-examples
# or
git checkout -b fix-week2-readme
```

### 3. Make Your Changes
Follow our content guidelines below when adding new material.

### 4. Test Your Changes
- Verify all links work
- Test any code examples
- Check markdown formatting
- Ensure images display correctly

### 5. Commit & Push
```bash
git add .
git commit -m "Add LangChain examples for week 2 RAG section"
git push origin your-branch-name
```

### 6. Create Pull Request
- Use the pull request template
- Include clear description of changes
- Reference any relevant issues
- Add screenshots for visual changes

## Content Guidelines

### File Organization
- Follow the existing folder structure
- Place content in the most appropriate location
- Update relevant README files
- Add entries to navigation tables

### Naming Conventions
- Use kebab-case for folders: `context-engineering`
- Use descriptive filenames: `openai-api-setup.md`
- Include version numbers when relevant: `langchain-v0.1-guide.md`

### Documentation Standards

#### README Files
Each folder should have a README.md with:
```markdown
# Section Title

Brief description of the content.

## Contents
- [Item 1](./item1.md) - Description
- [Item 2](./item2.md) - Description

## Quick Start
Basic usage or setup instructions.

## Resources
- External links
- References
```

#### Code Examples
- Include clear comments
- Provide complete, runnable examples
- Add requirements/dependencies
- Include expected output
- Test all code before submitting

```python
# Good example
import openai
from dotenv import load_dotenv

# Load environment variables
load_dotenv()

def create_chat_completion(message: str) -> str:
    """
    Create a chat completion using OpenAI's API.
    
    Args:
        message: User input message
        
    Returns:
        AI response as string
    """
    # Implementation here
    pass
```

#### Article/Tutorial Format
```markdown
# Title

## Overview
Brief description and learning objectives.

## Prerequisites
- Required knowledge
- Tools needed
- Dependencies

## Step-by-Step Guide
### Step 1: Setup
### Step 2: Implementation
### Step 3: Testing

## Complete Example
Full working code example.

## Next Steps
- Related topics
- Advanced concepts
- Additional resources

## Resources
- Links to documentation
- Related articles
- Video tutorials
```

### Quality Standards

#### Content Quality
- Accurate and up-to-date information
- Clear, beginner-friendly explanations
- Practical, hands-on examples
- Well-structured and organized

#### Technical Standards
- Code follows PEP 8 (Python) or relevant style guides
- All dependencies clearly listed
- Error handling included
- Security best practices followed

#### Accessibility
- Alt text for images
- Clear headings hierarchy
- Descriptive link text
- Color-blind friendly examples

## Specific Contribution Areas

### Week-Based Content
When adding to specific weeks:
- Review week objectives first
- Ensure content matches difficulty level
- Cross-reference with topic-based organization
- Update weekly README files

### Topic-Based Content
When adding to topic folders:
- Check for existing similar content
- Ensure proper categorization
- Link to related topics
- Update main topic README

### Tools & APIs
When documenting new tools:
- Include installation instructions
- Provide basic usage examples
- Document common issues
- Add to quick reference tables

## Review Process

### What We Look For
1. **Relevance** - Fits bootcamp curriculum
2. **Quality** - Well-written and tested
3. **Uniqueness** - Adds new value
4. **Organization** - Follows established structure

### Review Timeline
- Initial review: 2-3 days
- Feedback incorporation: Ongoing
- Final approval: 1-2 days after updates

## Community Guidelines

### Be Respectful
- Constructive feedback only
- Inclusive language
- Credit original authors
- Respect licensing terms

### Be Collaborative
- Discuss major changes in issues first
- Help review others' contributions
- Share knowledge freely
- Support fellow contributors

## Recognition

### Contributors List
All contributors are recognized in:
- [CONTRIBUTORS.md](./CONTRIBUTORS.md)
- Monthly community highlights
- Special mentions in bootcamp sessions

### Attribution
- Code examples: Include author comments
- Articles: Byline and contact info
- Tools: Creator attribution

## Getting Help

### Questions?
- 💬 [GitHub Discussions](https://github.com/your-username/bootcamp-resources/discussions)
- 🐛 [Report Issues](https://github.com/your-username/bootcamp-resources/issues)
- 📧 Email: bootcamp@example.com
- 💬 Discord: #contributors channel

### Resources
- [Writing Guide](./writing-guide.md)
- [Code Style Guide](./code-style-guide.md)
- [Content Templates](./templates/)

Thank you for contributing to the Agent Engineering Bootcamp! Your contributions help build a valuable learning resource for the entire community.

---

**Remember**: Every contribution, no matter how small, makes a difference! 🚀