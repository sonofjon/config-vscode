# VS Code Configuration

This directory contains VS Code settings, keybindings, and custom Copilot
instructions.

## Structure

```
config-vscode/
├── README.md                    # This file
├── settings.json                # User settings
├── keybindings.json             # Custom key bindings
└── instructions/                # Custom Copilot instructions
    ├── general.instructions.md  # General programming guidelines
    ├── python.instructions.md   # Python-specific guidelines
    └── elisp.instructions.md    # Emacs Lisp guidelines
```

## Installation

### VS Code Configuration Locations

The VS Code user configuration directory varies by operating system:

- **macOS**: `~/Library/Application Support/Code/User/`
- **Linux**: `~/.config/Code/User/`
- **Windows**: `%APPDATA%\Code\User\`

### Manual Setup

1. **Settings and Keybindings:**
   Copy the configuration files to your VS Code user directory (see
   locations above):
   ```
   settings.json → {VS Code User Directory}/settings.json
   keybindings.json → {VS Code User Directory}/keybindings.json
   ```

2. **Custom Instructions:**
   Copy the instruction files to the prompts subdirectory:
   ```
   instructions/*.instructions.md → {VS Code User Directory}/prompts/
   ```

   **Note:** You may need to create the `prompts` directory if it doesn't exist.
