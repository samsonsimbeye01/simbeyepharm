# Contributing to Simbeye Pharmacy Platform

Thank you for your interest in contributing to Simbeye Pharmacy Online! We welcome contributions from developers, designers, and community members. This guide will help you get started.

---

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Contribution Workflow](#contribution-workflow)
- [Coding Standards](#coding-standards)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Pull Request Process](#pull-request-process)
- [Reporting Issues](#reporting-issues)
- [Feature Requests](#feature-requests)
- [Documentation](#documentation)

---

## 🤝 Code of Conduct

We are committed to providing a welcoming and inclusive environment for all contributors. Please be respectful and constructive in all interactions.

**Expected Behavior:**
- Use inclusive language
- Be respectful of different opinions
- Focus on constructive criticism
- Help and support other contributors
- Report inappropriate behavior to maintainers

**Unacceptable Behavior:**
- Harassment, discrimination, or offensive comments
- Trolling or intentional disruption
- Sharing others' private information
- Any form of abuse

---

## 🚀 Getting Started

### Prerequisites
- Node.js v16 or higher
- npm or yarn package manager
- Git
- GitHub account

### Fork & Clone
```bash
# 1. Fork the repository on GitHub
# Click the "Fork" button on https://github.com/samsonsimbeye01/simbeyepharm

# 2. Clone your fork locally
git clone https://github.com/YOUR-USERNAME/simbeyepharm.git
cd simbeyepharm

# 3. Add upstream remote
git remote add upstream https://github.com/samsonsimbeye01/simbeyepharm.git

# 4. Keep your fork synced
git fetch upstream
git rebase upstream/main
```

---

## 💻 Development Setup

### Backend Setup
```bash
cd server
npm install

# Create .env file if needed
# Add environment variables here

# Start development server
npm run dev

# Run tests
npm test
```

### Frontend Setup
```bash
cd client
npm install

# Start development server
npm start

# Build for production
npm run build

# Run tests
npm test
```

### Database Initialization
```bash
cd server
npm run seed
```

---

## 📝 Contribution Workflow

### 1. Create a Feature Branch
```bash
# Update main branch
git checkout main
git pull upstream main

# Create feature branch with descriptive name
git checkout -b feature/add-medicine-search
# or
git checkout -b fix/prescription-validation
# or
git checkout -b docs/update-readme
```

### 2. Make Changes
- Write clean, readable code
- Follow the coding standards (see below)
- Add tests for new features
- Update documentation if needed

### 3. Commit Your Changes
```bash
# Stage changes
git add .

# Commit with meaningful message (see guidelines below)
git commit -m "feat: add medicine search functionality"

# Push to your fork
git push origin feature/add-medicine-search
```

### 4. Create Pull Request
- Go to your fork on GitHub
- Click "New Pull Request"
- Select `main` branch as base
- Provide detailed PR description
- Reference any related issues

---

## 📐 Coding Standards

### TypeScript
- **Use strict types** - Avoid `any` type
- **Export interfaces** - Define and export data types
- **Use meaningful names** - Variables, functions, components should be self-documenting
- **Add JSDoc comments** - Document functions and complex logic

```typescript
// Good ✅
interface Medicine {
  id: string
  name: string
  price: number
  stock: number
}

/**
 * Fetches medicines from the server
 * @param category - Optional category filter
 * @returns Promise<Medicine[]>
 */
export async function fetchMedicines(category?: string): Promise<Medicine[]> {
  // Implementation
}

// Bad ❌
async function fetch(cat) {
  // Implementation
}
```

### React Components
- **Use functional components** - Prefer hooks over class components
- **Props interface** - Define component props with TypeScript interfaces
- **Meaningful component names** - Use PascalCase
- **Separate concerns** - One component per file

```typescript
// Good ✅
interface ProductCardProps {
  id: string
  name: string
  price: number
  onAddToCart: (id: string) => void
}

export function ProductCard({ id, name, price, onAddToCart }: ProductCardProps) {
  return (
    <div className="product-card">
      <h3>{name}</h3>
      <p>${price}</p>
      <button onClick={() => onAddToCart(id)}>Add to Cart</button>
    </div>
  )
}

// Bad ❌
export function PC(props) {
  return (
    <div>
      <h3>{props.name}</h3>
      <button onClick={() => props.onClick(props.id)}>Add</button>
    </div>
  )
}
```

### Express Routes
- **Clear route names** - Use RESTful conventions
- **Validate input** - Check request data
- **Error handling** - Return proper HTTP status codes
- **Documentation** - Comment route purposes

```typescript
// Good ✅
/**
 * GET /catalogue/products
 * Fetches all medicines or filters by category
 */
router.get('/products', (req, res) => {
  const { category } = req.query
  
  if (category && typeof category !== 'string') {
    return res.status(400).json({ error: 'Invalid category' })
  }
  
  // Implementation
})

// Bad ❌
router.get('/products', (req, res) => {
  // No documentation, no validation
})
```

### Styling
- **Use Tailwind CSS classes** - Not inline styles
- **Responsive design** - Mobile-first approach
- **Consistent spacing** - Use Tailwind spacing scale
- **Dark mode support** - Add `dark:` variants when appropriate

```jsx
// Good ✅
<div className="flex items-center justify-between p-4 bg-white dark:bg-gray-900 rounded-lg shadow">
  <h2 className="text-xl font-bold text-gray-900 dark:text-white">Product</h2>
  <button className="px-4 py-2 bg-blue-600 hover:bg-blue-700 text-white rounded transition">
    Add to Cart
  </button>
</div>

// Bad ❌
<div style={{ display: 'flex', padding: '16px', backgroundColor: 'white' }}>
  <h2 style={{ fontSize: '20px', fontWeight: 'bold' }}>Product</h2>
  <button style={{ padding: '8px 16px', backgroundColor: 'blue', color: 'white' }}>
    Add to Cart
  </button>
</div>
```

---

## 📌 Commit Message Guidelines

Follow the Conventional Commits format:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types
- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation changes
- **style**: Code style changes (formatting, missing semicolons, etc.)
- **refactor**: Code refactoring without feature changes
- **perf**: Performance improvements
- **test**: Adding or updating tests
- **chore**: Build process, dependencies, etc.

### Examples
```bash
# Feature
git commit -m "feat(admin): add order filtering by status"

# Bug fix
git commit -m "fix(checkout): resolve payment validation error"

# Documentation
git commit -m "docs(readme): update installation instructions"

# Multiple line commit
git commit -m "feat(cart): add quantity adjustment

- Allow users to increase/decrease item quantity
- Update cart total automatically
- Add input validation for quantity

Closes #123"
```

---

## 🔄 Pull Request Process

### Before Submitting

1. **Test your changes**
   ```bash
   npm test
   npm run lint  # if available
   ```

2. **Update documentation**
   - Update README.md if API changes
   - Update OVERVIEW.md for architecture changes
   - Add JSDoc comments for new functions

3. **Sync with upstream**
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

4. **Push to your fork**
   ```bash
   git push origin feature/your-feature
   ```

### PR Description Template

```markdown
## Description
Brief description of what this PR does

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Related Issues
Fixes #123
Related to #124

## Changes Made
- Change 1
- Change 2
- Change 3

## Testing
How to test these changes:
1. Step 1
2. Step 2

## Screenshots (if applicable)
<!-- Add screenshots for UI changes -->

## Checklist
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] Commits follow guidelines
- [ ] No console errors/warnings
- [ ] Code follows style guidelines
```

### Review Process

1. **Automated checks** - GitHub Actions will run tests
2. **Code review** - Maintainers will review your code
3. **Address feedback** - Make requested changes
4. **Approval** - PR will be approved and merged

---

## 🐛 Reporting Issues

### Before Reporting
- Search existing issues to avoid duplicates
- Check documentation and FAQs
- Try troubleshooting steps

### Issue Template

**Use this format when reporting bugs:**

```markdown
## Description
Clear description of the issue

## Steps to Reproduce
1. Step 1
2. Step 2
3. Step 3

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Environment
- OS: [e.g., Windows 10]
- Node.js version: [e.g., 16.13.0]
- Browser: [e.g., Chrome 95]

## Additional Context
Screenshots, logs, or other relevant info
```

---

## 💡 Feature Requests

### Submission Format

```markdown
## Description
Clear description of the requested feature

## Problem It Solves
Explain the use case and benefits

## Proposed Solution
How you envision it working

## Example Usage
Code snippet or user flow showing how it would be used

## Additional Context
Why this feature would be valuable
```

---

## 📚 Documentation

### README.md
- Quick start guide
- Installation instructions
- Basic usage examples

### OVERVIEW.md
- Architecture explanation
- File structure
- API documentation
- Data models

### Code Comments
- Explain the "why", not the "what"
- Use JSDoc for functions
- Keep comments up-to-date

```typescript
// Good - explains why
// We fetch all products first, then filter client-side
// to reduce server load and improve UX
const allProducts = await fetchProducts()
const filtered = filterByCategory(allProducts, category)

// Bad - obvious from code
// Get all products
const allProducts = await fetchProducts()
// Filter by category
const filtered = filterByCategory(allProducts, category)
```

---

## 🔗 Useful Links

- **Main Repository:** https://github.com/samsonsimbeye01/simbeyepharm
- **Issues:** https://github.com/samsonsimbeye01/simbeyepharm/issues
- **Discussions:** https://github.com/samsonsimbeye01/simbeyepharm/discussions
- **Pull Requests:** https://github.com/samsonsimbeye01/simbeyepharm/pulls

---

## 📧 Questions?

- **GitHub Discussions:** Ask questions in Discussions tab
- **GitHub Issues:** Report bugs or request features
- **Email:** samsonsimbeye01@gmail.com

---

## 🎉 Thank You!

Your contributions help make Simbeye Pharmacy Platform better for everyone. Whether it's code, documentation, bug reports, or feature ideas—we appreciate your involvement!

**Happy coding!** 💻🚀
