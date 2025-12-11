# VS Code Configuration

This directory contains VS Code settings, keybindings, and prompts.

## Structure

```
config-vscode/
├── README.md                      # This file
├── settings.json                  # User settings
├── keybindings.json               # Custom key bindings
├── extensions.txt                 # List of extensions
└── prompts/                       # Custom AI prompts
```

## Configuration

### Configuration Locations

The VS Code user configuration directory varies by operating system:

- **macOS**: `~/Library/Application Support/Code/User/`
- **Linux**: `~/.config/Code/User/`
- **Windows**: `%APPDATA%\Code\User\`

### Installation

Copy the configuration files to your VS Code user directory (see
locations above):
```
settings.json -> {VS Code User Directory}/settings.json
keybindings.json -> {VS Code User Directory}/keybindings.json
```

## AI Instructions Setup

### Prerequisites

This setup integrates with a centralized AI configuration directory at
`~/dotfiles/config-ai/` that contains shared instruction files
(SYSTEM.md).

### Configuration Steps

1. **Configure VS Code to locate instruction files:**
   Add the following to your settings.json:
   ```json
   "chat.instructionsFilesLocations": [
       "{User Directory}/.github/instructions"
   ]
   ```
   Note that chat.instructionsFilesLocations does not understand "~" for
   the home directory.

2. **Create symlink to shared instructions:**
   ```bash
   mkdir -p ~/.github/instructions
   ln -s ~/dotfiles/config-ai/SYSTEM.md \
       ~/.github/instructions/copilot.instructions.md
   ```
   This makes the centralized SYSTEM.md file available to Copilot Chat.
