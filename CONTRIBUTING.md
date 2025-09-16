# Contributing to AI Career Coach 🤝

Thank you for considering contributing to AI Career Coach! We welcome contributions from the community and are excited to see what you can bring to this project.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Style Guidelines](#style-guidelines)
- [Commit Messages](#commit-messages)
- [Pull Request Process](#pull-request-process)
- [Testing](#testing)
- [Documentation](#documentation)
- [Community](#community)

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check the [existing issues](https://github.com/your-username/ai-career-coach/issues) to see if the problem has already been reported.

**When filing a bug report, please include:**
- **Clear description** of the issue
- **Steps to reproduce** the behavior
- **Expected behavior** vs actual behavior
- **Screenshots** if applicable
- **Environment details** (OS, browser, Node.js version)
- **Error messages** or console logs

**Use this template for bug reports:**

```markdown
**Bug Description**
A clear and concise description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

**Expected Behavior**
A clear description of what you expected to happen.

**Screenshots**
If applicable, add screenshots to help explain your problem.

**Environment**
- OS: [e.g. Windows 11, macOS 13.0]
- Browser: [e.g. Chrome 120, Safari 16]
- Node.js Version: [e.g. 18.17.0]
- Project Version: [e.g. 1.0.0]

**Additional Context**
Add any other context about the problem here.
```

### 💡 Suggesting Enhancements

Enhancement suggestions are welcome! Please provide:
- **Clear description** of the enhancement
- **Use case** and why it would be beneficial
- **Possible implementation** approach
- **Mockups or examples** if applicable

### 🔧 Code Contributions

We love code contributions! Here are areas where you can help:

#### 🎯 Priority Areas
- **AI Integration**: Improve AI prompts and responses
- **UI/UX**: Enhance user interface and experience
- **Performance**: Optimize loading times and responsiveness
- **Testing**: Add unit tests and integration tests
- **Accessibility**: Improve accessibility features
- **Mobile**: Enhance mobile responsiveness
- **Security**: Strengthen security measures

#### 🆕 Feature Ideas
- Advanced resume templates
- Interview practice with video recording
- Career path recommendations
- Skill gap analysis
- Networking features
- Job search integration
- Portfolio builder
- Certification tracking

## Getting Started

### Prerequisites

- **Node.js** (v18.0.0 or higher)
- **npm** or **pnpm** (pnpm recommended)
- **Git**
- **PostgreSQL** or Neon account

### 1. Fork and Clone

```bash
# Fork the repository on GitHub, then clone your fork
git clone https://github.com/YOUR_USERNAME/ai-career-coach.git
cd ai-career-coach

# Add the original repository as upstream
git remote add upstream https://github.com/original-username/ai-career-coach.git
```

### 2. Install Dependencies

```bash
# Using pnpm (recommended)
pnpm install

# Or using npm
npm install
```

### 3. Environment Setup

```bash
# Copy the example environment file
cp .env.example .env.local

# Fill in your environment variables
# See README.md for detailed instructions
```

### 4. Database Setup

```bash
# Generate Prisma client
npx prisma generate

# Run migrations
npx prisma migrate dev

# Optional: Seed the database
npx prisma db seed
```

### 5. Start Development Server

```bash
# Start the development server
pnpm dev

# Open http://localhost:3000
```

## Development Workflow

### 1. Create a Feature Branch

```bash
# Update your main branch
git checkout main
git pull upstream main

# Create a new feature branch
git checkout -b feature/your-feature-name

# Or for bug fixes
git checkout -b fix/issue-description
```

### 2. Make Your Changes

- Write clean, readable code
- Follow the existing code style
- Add tests for new functionality
- Update documentation as needed

### 3. Test Your Changes

```bash
# Run linting
pnpm lint

# Run type checking
pnpm type-check

# Run tests (when available)
pnpm test

# Build the project
pnpm build
```

### 4. Commit Your Changes

```bash
# Stage your changes
git add .

# Commit with a descriptive message
git commit -m "feat: add resume template selector"
```

### 5. Push and Create Pull Request

```bash
# Push to your fork
git push origin feature/your-feature-name

# Go to GitHub and create a Pull Request
```

## Style Guidelines

### 📝 Code Style

#### JavaScript/TypeScript
```javascript
// ✅ Good
const getUserProfile = async (userId) => {
  try {
    const user = await prisma.user.findUnique({
      where: { id: userId },
      include: { resume: true }
    });
    return user;
  } catch (error) {
    console.error('Error fetching user:', error);
    throw error;
  }
};

// ❌ Avoid
const getUser = async (id) => {
  const user = await prisma.user.findUnique({where: {id}});
  return user;
};
```

#### React Components
```jsx
// ✅ Good
const ResumeBuilder = ({ userId, onSave }) => {
  const [isLoading, setIsLoading] = useState(false);
  const [resume, setResume] = useState(null);

  const handleSave = async () => {
    setIsLoading(true);
    try {
      await onSave(resume);
    } finally {
      setIsLoading(false);
    }
  };

  return (
    <div className="space-y-4">
      {/* Component content */}
    </div>
  );
};

// ❌ Avoid
const resumeBuilder = (props) => {
  return <div>{/* content */}</div>;
};
```

#### CSS/Tailwind
```jsx
// ✅ Good - Logical grouping and consistent spacing
<div className="flex flex-col space-y-4 p-6 bg-white rounded-lg shadow-md">
  <h2 className="text-2xl font-bold text-gray-900">
    Resume Builder
  </h2>
</div>

// ❌ Avoid - Random order and inconsistent spacing
<div className="shadow-md rounded-lg bg-white flex p-6 space-y-4 flex-col">
  <h2 className="font-bold text-gray-900 text-2xl">Resume Builder</h2>
</div>
```

### 📁 File Naming

- **Components**: PascalCase (`ResumeBuilder.jsx`)
- **Pages**: kebab-case (`cover-letter.jsx`)
- **Utilities**: camelCase (`formatDate.js`)
- **Constants**: UPPER_SNAKE_CASE (`API_ENDPOINTS.js`)

### 📦 Import Order

```javascript
// 1. React imports
import React, { useState, useEffect } from 'react';

// 2. Third-party libraries
import { format } from 'date-fns';
import { toast } from 'sonner';

// 3. Internal utilities
import { cn } from '@/lib/utils';
import { prisma } from '@/lib/prisma';

// 4. Internal components
import { Button } from '@/components/ui/button';
import { Card } from '@/components/ui/card';

// 5. Relative imports
import './Component.css';
```

## Commit Messages

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

### Format
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Types
- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that do not affect the meaning of the code
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **perf**: A code change that improves performance
- **test**: Adding missing tests or correcting existing tests
- **chore**: Changes to the build process or auxiliary tools

### Examples
```bash
# Feature
git commit -m "feat(resume): add ATS score calculator"

# Bug fix
git commit -m "fix(auth): resolve sign-in redirect issue"

# Documentation
git commit -m "docs: update API documentation"

# Style
git commit -m "style(components): format button component"

# Breaking change
git commit -m "feat(api)!: change user endpoint response format"
```

## Pull Request Process

### 1. Before Submitting

- [ ] Fork the repository and create your branch from `main`
- [ ] Ensure your code follows the style guidelines
- [ ] Add tests for new functionality
- [ ] Update documentation if needed
- [ ] Run the linter and fix any issues
- [ ] Test your changes thoroughly

### 2. PR Description Template

```markdown
## Description
Brief description of what this PR does.

## Type of Change
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Code refactoring

## Testing
- [ ] Unit tests added/updated
- [ ] Integration tests added/updated
- [ ] Manual testing completed
- [ ] All tests pass

## Screenshots (if applicable)
Include screenshots of your changes.

## Checklist
- [ ] My code follows the style guidelines of this project
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] Any dependent changes have been merged and published
```

### 3. Review Process

1. **Automated Checks**: All CI checks must pass
2. **Code Review**: At least one maintainer must approve
3. **Testing**: Changes must be tested thoroughly
4. **Documentation**: Updates must be included if needed

## Testing

### Running Tests

```bash
# Run all tests
pnpm test

# Run tests in watch mode
pnpm test:watch

# Run tests with coverage
pnpm test:coverage

# Run specific test file
pnpm test path/to/test.spec.js
```

### Writing Tests

#### Unit Tests
```javascript
// components/__tests__/Button.test.jsx
import { render, screen, fireEvent } from '@testing-library/react';
import { Button } from '../Button';

describe('Button Component', () => {
  it('renders correctly', () => {
    render(<Button>Click me</Button>);
    expect(screen.getByRole('button', { name: 'Click me' })).toBeInTheDocument();
  });

  it('handles click events', () => {
    const handleClick = jest.fn();
    render(<Button onClick={handleClick}>Click me</Button>);
    
    fireEvent.click(screen.getByRole('button'));
    expect(handleClick).toHaveBeenCalledTimes(1);
  });
});
```

#### Integration Tests
```javascript
// __tests__/api/resume.test.js
import { createMocks } from 'node-mocks-http';
import handler from '../api/resume';

describe('/api/resume', () => {
  it('creates a new resume', async () => {
    const { req, res } = createMocks({
      method: 'POST',
      body: { content: 'Resume content', userId: 'user123' },
    });

    await handler(req, res);

    expect(res._getStatusCode()).toBe(201);
    expect(JSON.parse(res._getData())).toMatchObject({
      message: 'Resume created successfully',
    });
  });
});
```

## Documentation

### Updating Documentation

When making changes, please update relevant documentation:

- **README.md**: For major features or setup changes
- **API docs**: For API endpoint changes
- **Component docs**: For component prop changes
- **Code comments**: For complex logic

### Documentation Style

```javascript
/**
 * Calculates the ATS score for a resume
 * @param {string} resumeContent - The resume content in markdown
 * @param {string[]} keywords - Array of job keywords to match
 * @returns {Promise<number>} ATS score between 0 and 100
 */
const calculateATSScore = async (resumeContent, keywords) => {
  // Implementation here
};
```

## Community

### Getting Help

- **GitHub Discussions**: General questions and discussions
- **Issues**: Bug reports and feature requests
- **Discord**: Real-time chat with the community
- **Email**: Direct contact with maintainers

### Recognition

Contributors will be recognized in:
- **README.md**: All contributors list
- **CHANGELOG.md**: Release notes
- **GitHub**: Contributor graphs and stats

### Mentorship

New contributors can request mentorship by:
1. Opening an issue with the `mentorship` label
2. Joining our Discord community
3. Participating in "good first issue" discussions

## Thank You! 🙏

Your contributions make AI Career Coach better for everyone. We appreciate your time and effort in helping improve this project.

---

**Happy Contributing!** 🚀

For questions, reach out to the maintainers or open a discussion on GitHub.