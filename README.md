# Pre-Commit | ASH

## Set-up steps:

1. ASH
2. pre-commit-ash
3. Notes

## 1. ASH

Source: [ASH](https://github.com/awslabs/automated-security-helper?tab=readme-ov-file)

ASH installation example:
``` 
# Set up some variables
REPO_DIR="${HOME}"/Documents/repos/reference
REPO_NAME=automated-security-helper

# Create a folder to hold reference git repositories
mkdir -p ${REPO_DIR}

# Clone the repository into the reference area
git clone https://github.com/awslabs/automated-security-helper "${REPO_DIR}/${REPO_NAME}"

# Set the repo path in your shell for easier access
#
# Add this (and the variable settings above) to
# your ~/.bashrc, ~/.bash_profile, ~/.zshrc, or similar
# start-up scripts so that the ash tool is in your PATH
# after re-starting or starting a new shell.
#
export PATH="${PATH}:${REPO_DIR}/${REPO_NAME}"

# Execute the ash tool
ash --version
```

## 2. pre-commit-ash

Configure your .pre-commit-config.yaml file to include ash:

```
# Custom ASH hook 
  - repo: git@git.tech.theverygroup.com:tech/information-security/pre-commit-ash.git
    rev: v0.1.0
    hooks:
    - id: ash
      name: ASH (Automated Security Helper)
      description: Runs 'ash'command 
      entry: ash-go # This should be modified to use the relevant version required
      verbose: true
      stages: [commit, merge-commit, push, manual]
      language: script
```

## 3. Notes:

⚠️ Please ensure you add 'ash/' to your .gitignore file to avoid uploading the findings to your remote repo! ⚠️

To start using ash please make sure to install and configure the following:

Tools installed to run Linux containers, such as Finch, Rancher Desktop, Podman Desktop, or Docker Desktop.
This can be any command-line interface (CLI) + container engine combination; there is nothing in ASH that requires a specific container runtime.
If on Windows, you will also likely need Windows Subsystem for Linux (WSL) installed as a prerequisite for the listed container engine tools. Please see the specific instructions for the tool of choice regarding Windows-specific prerequisites.