# Matrix.Core.Workspace

A workspace repository that brings together all Matrix.Core related projects using Git submodules.

## Overview

This repository serves as a centralized workspace for managing the Matrix.Core ecosystem, which includes:

- **Matrix.Core** - Core functionality and base implementations
- **Matrix.Core.Data** - Data access layer and repository patterns
- **Matrix.Core.Models** - Domain models and data transfer objects
- **Matrix.Core.Shared** - Shared utilities and common code

## Prerequisites

- Git 2.13 or higher
- .NET SDK (check individual submodule requirements)

## Getting Started

### Cloning the Repository

To clone this repository with all submodules:

```bash
git clone --recursive https://github.com/codenamelab/Matrix.Core.Workspace.git
```

If you've already cloned the repository without the `--recursive` flag, initialize the submodules:

```bash
git submodule update --init --recursive
```

### Updating Submodules

To update all submodules to their latest commits:

```bash
git submodule update --remote --merge
```

To update a specific submodule:

```bash
git submodule update --remote --merge Matrix.Core
```

### Working with Submodules

Each submodule is a separate Git repository. To make changes to a submodule:

1. Navigate to the submodule directory:
   ```bash
   cd Matrix.Core
   ```

2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. Make your changes and commit them:
   ```bash
   git add .
   git commit -m "Your commit message"
   ```

4. Push to the submodule's repository:
   ```bash
   git push origin feature/your-feature-name
   ```

5. Return to the workspace root and update the submodule reference:
   ```bash
   cd ..
   git add Matrix.Core
   git commit -m "Update Matrix.Core submodule reference"
   git push
   ```

## Project Structure

```
Matrix.Core.Workspace/
├── Matrix.Core/           # Core library submodule
├── Matrix.Core.Data/      # Data access layer submodule
├── Matrix.Core.Models/    # Domain models submodule
├── Matrix.Core.Shared/    # Shared utilities submodule
├── .gitignore            # Git ignore rules
├── .gitmodules           # Submodule configuration
└── README.md             # This file
```

## Building

Each submodule contains its own build instructions. Please refer to the README in each submodule directory for specific build steps.

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Submodule Repositories

- [Matrix.Core](https://github.com/codenamelab/Matrix.Core)
- [Matrix.Core.Data](https://github.com/codenamelab/Matrix.Core.Data)
- [Matrix.Core.Models](https://github.com/codenamelab/Matrix.Core.Models)
- [Matrix.Core.Shared](https://github.com/codenamelab/Matrix.Core.Shared)

## Support

For issues related to:
- This workspace repository: Open an issue here
- Individual submodules: Open an issue in the respective submodule repository

## Useful Commands

### Check Submodule Status
```bash
git submodule status
```

### Pull Latest Changes from All Submodules
```bash
git pull --recurse-submodules
```

### Execute Command in All Submodules
```bash
git submodule foreach 'git checkout main && git pull'
```

### Remove a Submodule
```bash
git submodule deinit -f <submodule-path>
git rm -f <submodule-path>
rm -rf .git/modules/<submodule-path>
```

## Troubleshooting

### Submodules Not Initialized

If you see empty submodule directories, run:
```bash
git submodule update --init --recursive
```

### Detached HEAD in Submodules

Submodules are checked out at specific commits by default. To work on a branch:
```bash
cd <submodule-directory>
git checkout main  # or your desired branch
```

### Submodule Update Conflicts

If you encounter conflicts when updating submodules:
```bash
git submodule update --remote --merge
# Resolve conflicts in the submodule
cd <submodule-directory>
# Fix conflicts and commit
git add .
git commit -m "Resolve merge conflicts"
cd ..
git add <submodule-directory>
git commit -m "Update submodule with conflict resolution"
```
