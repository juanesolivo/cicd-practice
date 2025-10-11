# 🚀 CI/CD Practice with GitHub Actions

This project demonstrates **Continuous Integration (CI)** and **Continuous Deployment (CD)** using GitHub Actions. It's designed to help you learn the fundamental concepts and best practices of modern DevOps workflows.

## 📚 What You'll Learn

### CI/CD Concepts Covered:
- ✅ **Continuous Integration**: Automated testing, linting, and building
- ✅ **Continuous Deployment**: Automated deployment to staging and production
- ✅ **Code Quality**: ESLint, testing with Jest, coverage reporting
- ✅ **Security**: Dependency auditing and vulnerability scanning
- ✅ **Multi-environment Deployments**: Staging vs Production workflows
- ✅ **Release Management**: Automated releases with changelogs
- ✅ **Pull Request Workflows**: PR validation and checks

## 🏗️ Project Structure

```
cicd-practice/
├── .github/
│   └── workflows/           # GitHub Actions workflows
│       ├── ci-cd.yml       # Main CI/CD pipeline
│       ├── nightly.yml     # Nightly builds
│       ├── release.yml     # Release automation
│       └── pull-request.yml # PR-specific checks
├── src/
│   └── app.js              # Express.js application
├── tests/
│   └── app.test.js         # Jest test suite
├── package.json            # Node.js dependencies and scripts
├── jest.config.js          # Jest configuration
└── .eslintrc.js           # ESLint configuration
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- Git
- GitHub account

### Local Setup
```bash
# Clone the repository
git clone <your-repo-url>
cd cicd-practice

# Install dependencies
npm install

# Run the application locally
npm run dev

# Run tests
npm test

# Run linting
npm run lint
```

## 🔄 Workflow Explanations

### 1. Main CI/CD Pipeline (`.github/workflows/ci-cd.yml`)
**Triggers**: Push to `main`/`develop` branches, Pull Requests to `main`

**Jobs**:
- 🔍 **Code Quality**: Runs ESLint for code style consistency
- 🔒 **Security Audit**: Checks for vulnerabilities with `npm audit`
- 🧪 **Testing**: Runs Jest tests across multiple Node.js versions (16, 18, 20)
- 🏗️ **Build**: Compiles the application and creates artifacts
- 🚀 **Deploy Staging**: Deploys to staging when code is pushed to `develop`
- 🌟 **Deploy Production**: Deploys to production when code is pushed to `main`

### 2. Nightly Build (`.github/workflows/nightly.yml`)
**Triggers**: Every night at 2 AM UTC, or manual trigger

**Purpose**: Runs extended test suites and dependency checks to catch issues early

### 3. Release Workflow (`.github/workflows/release.yml`)
**Triggers**: When you push a version tag (e.g., `v1.0.0`)

**Features**:
- Creates GitHub releases automatically
- Generates changelogs from commit messages
- Uploads build artifacts

### 4. Pull Request Checks (`.github/workflows/pull-request.yml`)
**Triggers**: When PRs are opened or updated

**Features**:
- Validates PR title format (conventional commits)
- Checks for changes in sensitive files
- Reports test coverage in PR comments
- Analyzes bundle size impact

## 🌟 Key Features Demonstrated

### 🔄 Continuous Integration (CI)
- **Automated Testing**: Every code change triggers tests
- **Code Quality Gates**: Linting and formatting checks
- **Multi-Node Version Testing**: Ensures compatibility
- **Security Scanning**: Vulnerability detection
- **Build Verification**: Ensures code compiles successfully

### 🚀 Continuous Deployment (CD)
- **Environment-based Deployment**: Different workflows for staging/production
- **Artifact Management**: Build once, deploy anywhere
- **Deployment Gates**: Only deploy if all tests pass
- **Environment URLs**: Track where your code is deployed

### 🛡️ Security & Quality
- **Dependency Auditing**: Automatic vulnerability scanning
- **Code Coverage**: Track test coverage over time
- **Conventional Commits**: Enforce commit message standards
- **Sensitive File Detection**: Alert on critical file changes

## 🎯 Learning Exercises

### Exercise 1: Understanding the Pipeline
1. Make a small change to `src/app.js`
2. Commit and push to a new branch
3. Open a Pull Request and observe the checks
4. Merge to `develop` and watch staging deployment

### Exercise 2: Adding New Tests
1. Add a new API endpoint in `src/app.js`
2. Write tests for it in `tests/app.test.js`
3. Ensure coverage stays above 80%

### Exercise 3: Creating a Release
1. Make sure your changes are in `main` branch
2. Create a new tag: `git tag v1.1.0`
3. Push the tag: `git push origin v1.1.0`
4. Watch the automated release process

### Exercise 4: Customizing Workflows
1. Modify the nightly workflow to run additional checks
2. Add a new environment (e.g., "QA")
3. Create a workflow that runs only on specific file changes

## 📋 Available Scripts

```bash
npm start          # Start the application
npm run dev        # Start with nodemon for development
npm test           # Run Jest tests
npm run test:coverage  # Run tests with coverage report
npm run lint       # Run ESLint
npm run lint:fix   # Fix ESLint issues automatically
npm run build      # Build the application
```

## 🔧 Environment Variables

For production deployments, you might need:
- `PORT`: Server port (default: 3000)
- `NODE_ENV`: Environment (development/staging/production)

## 📈 Monitoring Your Pipeline

### GitHub Actions Dashboard
- Go to your repository → Actions tab
- View workflow runs, logs, and artifacts
- Monitor success/failure rates

### Coverage Reports
- Check the coverage folder after running tests
- View HTML reports in `coverage/lcov-report/index.html`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feat/new-feature`
3. Make your changes and add tests
4. Ensure all checks pass locally:
   ```bash
   npm run lint
   npm test
   npm run build
   ```
5. Commit using conventional commit format:
   ```bash
   git commit -m "feat: add new awesome feature"
   ```
6. Push and create a Pull Request

## 📚 Additional Resources

### GitHub Actions Documentation
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Workflow Syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)
- [Action Marketplace](https://github.com/marketplace?type=actions)

### CI/CD Best Practices
- [The Twelve-Factor App](https://12factor.net/)
- [GitFlow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [Conventional Commits](https://www.conventionalcommits.org/)

### Testing & Quality
- [Jest Documentation](https://jestjs.io/)
- [ESLint Rules](https://eslint.org/docs/rules/)
- [Node.js Testing Best Practices](https://github.com/goldbergyoni/nodebestpractices#-6-testing-and-overall-quality-practices)

## 🎯 Next Steps

Once you're comfortable with this setup, consider exploring:
- **Docker**: Containerize your application
- **Kubernetes**: Orchestrate containers
- **Terraform**: Infrastructure as Code
- **Monitoring**: Add logging and metrics
- **Advanced Testing**: E2E tests, performance tests
- **Multi-cloud Deployment**: AWS, Azure, GCP

---

Happy learning! 🎉 If you have questions or suggestions, feel free to open an issue or contribute to this project.
