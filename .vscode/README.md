# VS Code Workspace Setup

This directory contains VS Code workspace configuration files for the Community Forensics project.

## Files Included

### 1. `Community-Forensics.code-workspace`
The main workspace file that contains all settings, recommended extensions, and launch configurations in one file. You can open this file directly in VS Code using:
```bash
code Community-Forensics.code-workspace
```

### 2. `.vscode/` Directory
Contains individual configuration files:
- **`settings.json`**: Editor and Python-specific settings
- **`extensions.json`**: Recommended VS Code extensions
- **`launch.json`**: Debug configurations for training and evaluation

## Recommended Extensions

The workspace recommends the following VS Code extensions:
- **Python**: Core Python support
- **Pylance**: Advanced Python language server
- **Black Formatter**: Python code formatting
- **Jupyter**: Jupyter notebook support and related extensions

When you open the workspace, VS Code will prompt you to install these extensions if they're not already installed.

## Debug Configurations

The workspace includes three pre-configured debug setups:

### 1. Python: Train (Debug)
Runs the training script with minimal arguments for quick testing:
- 1 GPU
- 1 epoch
- Small batch size (8)
- Uses HuggingFace Small dataset

### 2. Python: Eval (Debug)
Runs the evaluation script:
- 1 GPU
- Small batch size (8)
- Uses pre-trained model from HuggingFace

### 3. Python: Current File
Debug the currently open Python file.

## Python Settings

The workspace is configured with:
- **Type checking**: Basic level
- **Auto-imports**: Enabled
- **Format on save**: Disabled (to preserve existing code style)
- **Virtual environment**: Assumes `.venv` directory (adjust as needed)
  - **Note**: The default path uses Unix-style paths (`.venv/bin/python`)
  - **Windows users**: Update to `.venv/Scripts/python.exe` in settings.json
- **Excluded files**: Caches, build artifacts, and wandb logs

## Getting Started

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Open the workspace:
   ```bash
   code Community-Forensics.code-workspace
   ```

3. Install recommended extensions when prompted

4. Configure your Python interpreter if needed:
   - Default: `.venv/bin/python` (Unix/Linux/macOS)
   - Windows: `.venv/Scripts/python.exe`
   - You can change this in `.vscode/settings.json`

5. Use the debug configurations from the Run and Debug panel (Ctrl+Shift+D / Cmd+Shift+D)

## Customization

Feel free to customize the workspace settings in:
- `.vscode/settings.json` for project-wide settings
- `.vscode/launch.json` for debug configurations
- Or use your personal VS Code settings

## Gitignore

The `.gitignore` file has been configured to exclude:
- Python cache files (`__pycache__`, `*.pyc`)
- Virtual environments (`.venv`, `venv`, etc.)
- Model weights and checkpoints (`*.pt`, `*.pth`, `*.ckpt`)
- Weights & Biases logs (`wandb/`)
- HuggingFace cache (`.cache/`)
- IDE-specific files
- Temporary files
