# Contributing to Matrix.Core.Workspace

Thank you for your interest in contributing to Matrix.Core.Workspace! This document provides guidelines and instructions for contributing.

## Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md) to keep our community approachable and respectable.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When creating a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples to demonstrate the steps**
- **Describe the behavior you observed and what you expected**
- **Include screenshots or code samples if applicable**
- **Specify which version you're using**
- **Include environment details** (OS, .NET version, etc.)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description of the suggested enhancement**
- **Explain why this enhancement would be useful**
- **List any alternative solutions you've considered**

### Pull Requests

1. **Fork the repository** and create your branch from `main`
2. **Follow the coding style** used in the project
3. **Write clear commit messages** following conventional commits format:
   - `feat:` for new features
   - `fix:` for bug fixes
   - `docs:` for documentation changes
   - `style:` for formatting changes
   - `refactor:` for code refactoring
   - `test:` for adding tests
   - `chore:` for maintenance tasks

4. **Update documentation** if you've made changes to functionality
5. **Add tests** if applicable
6. **Ensure all tests pass** before submitting
7. **Submit your pull request**

## Working with Submodules

Since this is a workspace repository managing multiple submodules:

### Making Changes to Submodules

1. Navigate to the submodule directory
2. Create a feature branch
3. Make your changes
4. Commit and push to the submodule repository
5. Return to the workspace root
6. Update the submodule reference
7. Create a PR in the workspace repository

### Example Workflow

```bash
# Navigate to submodule
cd Matrix.Core

# Create feature branch
git checkout -b feature/my-new-feature

# Make changes
# ... edit files ...

# Commit changes
git add .
git commit -m "feat: add new feature"

# Push to submodule repository
git push origin feature/my-new-feature

# Return to workspace root
cd ..

# Update submodule reference
git add Matrix.Core
git commit -m "chore: update Matrix.Core submodule reference"

# Push workspace changes
git push origin your-workspace-branch
```

## Development Workflow

### Setup Development Environment

1. Clone the repository with submodules:
   ```bash
   git clone --recursive https://github.com/codenamelab/Matrix.Core.Workspace.git
   cd Matrix.Core.Workspace
   ```

2. Install required tools (refer to individual submodule READMEs)

3. Ensure you can build all submodules successfully

### Branch Naming Convention

- Feature branches: `feature/description`
- Bug fix branches: `fix/description`
- Documentation: `docs/description`
- Refactoring: `refactor/description`

### Commit Message Guidelines

Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Examples:
- `feat: add new authentication module`
- `fix: resolve null reference in data layer`
- `docs: update README with build instructions`
- `refactor: simplify repository pattern implementation`

## Coding Standards

### General Guidelines

- Write clean, readable, and maintainable code
- Follow SOLID principles
- Keep methods small and focused
- Use meaningful variable and method names
- Add comments for complex logic
- Remove commented-out code before committing
- Avoid premature optimization

### C# Specific Guidelines

- Follow [Microsoft C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
- Use PascalCase for class names and method names
- Use camelCase for local variables and parameters
- Use `_camelCase` for private fields
- Use `async`/`await` for asynchronous operations
- Dispose of resources properly using `using` statements
- Prefer `var` when the type is obvious

### Documentation

- Add XML documentation comments for public APIs
- Keep documentation up to date with code changes
- Include examples in documentation where helpful
- Document complex algorithms or business logic

## Testing

- Write unit tests for new features
- Ensure existing tests pass
- Aim for meaningful test coverage
- Use descriptive test names
- Follow the Arrange-Act-Assert pattern

## Review Process

1. All submissions require review
2. Reviewers may request changes
3. Address review comments promptly
4. Once approved, maintainers will merge your PR

## Questions?

Feel free to open an issue with your question or reach out to the maintainers.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Recognition

Contributors will be recognized in the project's release notes and documentation.

Thank you for contributing to Matrix.Core.Workspace! 🎉
