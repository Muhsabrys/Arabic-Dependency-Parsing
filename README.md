
# Arabic Dependency Parsing with CAMeL Parser

This repository provides a Jupyter notebook to guide users in setting up an environment for Arabic dependency parsing using the CAMeL Parser. It also addresses some common challenges that users may face when using CAMeL tools, specifically related to installation and setup.

## Overview

The CAMeL Parser is a tool for syntactic parsing of Arabic text, helping users to derive grammatical relationships between words. This repository aims to simplify the installation process and to provide step-by-step instructions for configuring dependencies that are essential for running the CAMeL Parser effectively. 

### Key Features
- Sets up a Python 3.9 environment for compatibility with CAMeL Parser dependencies.
- Fixes common dependency issues by removing conflicting packages and manually installing critical components.
- Provides a detailed walkthrough for configuring and using a virtual environment.

## Notebook Contents

### 1. **System Setup and Dependencies**
The initial part of the notebook prepares your system by updating package lists and installing basic build tools. It then:
- **Installs Python 3.9** using the deadsnakes PPA, which provides various Python versions.
- **Creates a virtual environment (`myenv`)** using Python 3.9 to avoid conflicts with the default Python installation.

### 2. **Activating the Virtual Environment**
- The virtual environment is activated, and `pip` is upgraded to ensure compatibility with the rest of the dependencies.
  
### 3. **Cloning the CAMeL Parser Repository**
- The notebook clones the CAMeL Parser repository from GitHub.
- It **removes certain lines** from the `requirements.txt` file to avoid compilation errors. Specifically, it removes references to problematic packages like `camel-kenlm` and `camel-tools`.

### 4. **Installing Dependencies**
- **Installs the necessary dependencies** using the modified `requirements.txt` file within the virtual environment.
- Manually installs `camel-kenlm` and `camel-tools` after the main installation to ensure compatibility.

### 5. **Handling Installation Errors**
- Since some packages are difficult to install in the virtual environment, the notebook uses a workaround:
  - It installs `camel-tools` and `camel-kenlm` using the default Python environment and then **copies these installed packages** into the Python 3.9 virtual environment (`myenv`). This solves issues that occur during installation when trying to use the virtual environment directly.

## Challenges Addressed
### 1. **Dependency Issues with `camel-kenlm` and `camel-tools`**
The CAMeL Parser's `requirements.txt` includes certain packages that can cause installation errors when run on some platforms. To address this:
- The notebook automatically **removes problematic lines** from the `requirements.txt`.
- It then **installs the problematic packages manually** to ensure that the versions are compatible with the virtual environment.

### 2. **Virtual Environment Compatibility**
- Certain CAMeL Parser dependencies need to be installed using Python's default installation because they do not compile properly in virtual environments.
- To solve this, the notebook uses `shutil` to **copy the installed packages** into the virtual environment, ensuring a successful setup.

## How to Use the Notebook
### Step 1: Environment Setup
Run the first few cells to set up Python 3.9 and create the virtual environment.

### Step 2: Clone and Modify CAMeL Parser
The notebook will handle cloning the CAMeL Parser repository and modifying the `requirements.txt` file to avoid installation errors.

### Step 3: Install Dependencies
The dependencies are installed using a combination of virtual environment tools and manual installations.

### Step 4: Test the Parser
Once all dependencies are successfully installed, you can proceed to use the CAMeL Parser for Arabic dependency parsing tasks.

## Requirements
- **Operating System**: Linux (preferably a Debian-based system, as it uses `apt` commands)
- **Python**: Python 3.9
- **Virtual Environment**: The installation process requires the use of a virtual environment to avoid conflicts with system Python packages.

## Notes
- The installation process includes using some root commands (`sudo`) to install system packages. Ensure you have administrative privileges on your machine.
- The manual handling of the `camel-kenlm` and `camel-tools` installations helps in avoiding compilation errors commonly faced with virtual environments.

## Troubleshooting
- **Virtual Environment Issues**: If you face issues related to activating the environment, ensure the paths are correct and that all commands are run within the correct directory.
- **Dependency Compilation Errors**: Some dependencies may fail due to system compatibility. The manual steps included in the notebook are designed to address these issues.

## License
This repository is licensed under the MIT License.
