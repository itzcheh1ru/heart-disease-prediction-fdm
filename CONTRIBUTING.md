# 🤝 Contributing Guidelines
## Heart Disease Prediction System

Thank you for your interest in contributing to the Heart Disease Prediction System! This document provides guidelines for contributing to our project.

---

## 📋 **Table of Contents**

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Contributing Process](#contributing-process)
- [Code Standards](#code-standards)
- [Testing Guidelines](#testing-guidelines)
- [Documentation](#documentation)
- [Issue Reporting](#issue-reporting)
- [Pull Request Process](#pull-request-process)

---

## 📜 **Code of Conduct**

### Our Pledge
We are committed to providing a welcoming and inclusive environment for all contributors. Please:

- Be respectful and inclusive
- Use welcoming and inclusive language
- Accept constructive criticism gracefully
- Focus on what's best for the community
- Show empathy towards other community members

### Our Standards
Examples of behavior that contributes to a positive environment:

- Using welcoming and inclusive language
- Being respectful of differing viewpoints
- Accepting constructive criticism
- Focusing on what's best for the community
- Showing empathy towards other community members

---

## 🚀 **Getting Started**

### Prerequisites
- Python 3.12 or higher
- Git
- pip (Python package installer)
- Basic knowledge of Django and machine learning

### Development Setup

1. **Fork the Repository**
   ```bash
   # Fork on GitHub, then clone your fork
   git clone https://github.com/your-username/heart-disease-prediction-fdm.git
   cd heart-disease-prediction-fdm
   ```

2. **Create Virtual Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Database Setup**
   ```bash
   python manage.py migrate
   python manage.py createsuperuser
   ```

5. **Run Development Server**
   ```bash
   python manage.py runserver
   ```

---

## 🔄 **Contributing Process**

### 1. **Choose an Issue**
- Browse open issues
- Look for "good first issue" labels
- Comment on the issue to express interest
- Wait for assignment before starting work

### 2. **Create Feature Branch**
```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/your-bug-fix
```

### 3. **Make Changes**
- Write clean, readable code
- Follow existing code style
- Add tests for new functionality
- Update documentation as needed

### 4. **Test Your Changes**
```bash
# Run tests
python manage.py test

# Check code style
flake8 .

# Run linting
pylint apps/
```

### 5. **Commit Changes**
```bash
git add .
git commit -m "Add: descriptive commit message"
```

### 6. **Push and Create PR**
```bash
git push origin feature/your-feature-name
# Create Pull Request on GitHub
```

---

## 📝 **Code Standards**

### Python Style Guide
- Follow PEP 8 style guide
- Use meaningful variable names
- Write docstrings for functions and classes
- Keep functions small and focused
- Use type hints where appropriate

### Django Best Practices
- Use Django's built-in features
- Follow Django's naming conventions
- Use Django's ORM efficiently
- Implement proper error handling
- Use Django's security features

### Machine Learning Code
- Document model parameters
- Include performance metrics
- Add model validation
- Implement proper data preprocessing
- Include feature importance analysis

---

## 🧪 **Testing Guidelines**

### Test Structure
```python
# Example test structure
class TestHeartDiseaseModel(unittest.TestCase):
    def setUp(self):
        """Set up test fixtures"""
        pass
    
    def test_model_prediction(self):
        """Test model prediction functionality"""
        pass
    
    def tearDown(self):
        """Clean up after tests"""
        pass
```

### Test Categories
- **Unit Tests**: Test individual functions
- **Integration Tests**: Test component interactions
- **Model Tests**: Test ML model functionality
- **API Tests**: Test Django views and endpoints

### Running Tests
```bash
# Run all tests
python manage.py test

# Run specific test
python manage.py test apps.core.health.tests

# Run with coverage
coverage run --source='.' manage.py test
coverage report
```

---

## 📚 **Documentation**

### Code Documentation
- Write clear docstrings
- Include parameter descriptions
- Add return value documentation
- Provide usage examples

### README Updates
- Update feature lists
- Include new installation steps
- Add new configuration options
- Update deployment instructions

### API Documentation
- Document all endpoints
- Include request/response examples
- Add authentication requirements
- Provide error code explanations

---

## 🐛 **Issue Reporting**

### Bug Reports
When reporting bugs, please include:

1. **Clear Description**
   - What happened?
   - What did you expect?
   - What actually happened?

2. **Reproduction Steps**
   - Step-by-step instructions
   - Minimal code example
   - Environment details

3. **Environment Information**
   - Python version
   - Django version
   - Operating system
   - Browser (if applicable)

### Feature Requests
When requesting features:

1. **Clear Description**
   - What feature do you want?
   - Why is it needed?
   - How should it work?

2. **Use Cases**
   - Who would use this feature?
   - What problems would it solve?
   - Any existing alternatives?

---

## 🔀 **Pull Request Process**

### Before Submitting
- [ ] Code follows style guidelines
- [ ] Tests pass locally
- [ ] Documentation updated
- [ ] No merge conflicts
- [ ] Commit messages are clear

### PR Template
```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Tests pass locally
- [ ] New tests added
- [ ] Manual testing completed

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No breaking changes
```

### Review Process
1. **Automated Checks**: CI/CD pipeline runs
2. **Code Review**: Team members review code
3. **Testing**: Manual testing if needed
4. **Approval**: Maintainer approves changes
5. **Merge**: Changes merged to main branch

---

## 🏷️ **Labels and Milestones**

### Issue Labels
- `bug`: Something isn't working
- `enhancement`: New feature or request
- `documentation`: Improvements to documentation
- `good first issue`: Good for newcomers
- `help wanted`: Extra attention needed
- `question`: Further information requested

### Milestones
- `v1.0.0`: Initial release
- `v1.1.0`: Feature updates
- `v1.2.0`: Major improvements
- `v2.0.0`: Major version update

---

## 👥 **Team Roles**

### Core Maintainers
- **Hirusha Thisayuru Ellawala**: Project Lead & Backend
- **Sandali Isidara Samarasinghe**: Frontend & UX
- **Shehan Dissanayake**: Machine Learning
- **Ishini Neha Amararathne**: QA & Documentation

### Contribution Areas
- **Backend Development**: Django, API, database
- **Frontend Development**: HTML, CSS, JavaScript
- **Machine Learning**: Model improvements, algorithms
- **Testing**: Unit tests, integration tests
- **Documentation**: README, API docs, guides
- **DevOps**: Deployment, CI/CD, monitoring

---

## 🎯 **Development Roadmap**

### Short Term (1-2 months)
- [ ] Performance optimizations
- [ ] Additional ML models
- [ ] API improvements
- [ ] Documentation updates

### Medium Term (3-6 months)
- [ ] Mobile app development
- [ ] Advanced analytics
- [ ] Multi-language support
- [ ] Cloud integration

### Long Term (6+ months)
- [ ] AI model improvements
- [ ] Telemedicine features
- [ ] Enterprise features
- [ ] International deployment

---

## 📞 **Getting Help**

### Communication Channels
- **GitHub Issues**: Bug reports and feature requests
- **GitHub Discussions**: General questions and ideas
- **Email**: Direct contact with maintainers
- **Documentation**: Check existing docs first

### Resources
- [Django Documentation](https://docs.djangoproject.com/)
- [scikit-learn Documentation](https://scikit-learn.org/)
- [Python Style Guide](https://pep8.org/)
- [Git Best Practices](https://git-scm.com/docs)

---

## 🙏 **Recognition**

### Contributors
We recognize all contributors in our README and release notes. Contributors are listed by:
- Number of contributions
- Impact of contributions
- Community engagement
- Code quality

### Hall of Fame
- **Top Contributors**: Most active contributors
- **Bug Hunters**: Found and fixed critical bugs
- **Feature Creators**: Implemented major features
- **Documentation Heroes**: Improved project documentation

---

## 📄 **License**

By contributing to this project, you agree that your contributions will be licensed under the same license as the project (MIT License).

---

**Thank you for contributing to the Heart Disease Prediction System! 🫀**

Together, we can make healthcare more accessible through technology.
