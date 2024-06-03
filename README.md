# Pre-Commit | ASH

## Set-up steps:

1. ASH

## 1. ASH

Source: [ASH](https://github.com/awslabs/automated-security-helper?tab=readme-ov-file

ASH Installation:
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