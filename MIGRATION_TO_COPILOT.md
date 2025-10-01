# Migration from Gemini CLI to GitHub Copilot CLI

This document summarizes the changes made to migrate the academic paper generation system from Gemini CLI to GitHub Copilot CLI.

## Summary of Changes

### 1. Python Script (`docs/process_inputs.py`)
- **Configuration**: Changed `GEMINI_MODEL = "gemini-2.5-flash"` to `COPILOT_MODEL = "gpt-4"`
- **Command Structure**: Updated from `gemini` command to `gh copilot chat` command
- **Command Arguments**: Modified command structure to use GitHub Copilot CLI syntax:
  - Old: `["gemini", final_prompt, "-m", GEMINI_MODEL, "-y"]`
  - New: `["gh", "copilot", "chat", "--model", COPILOT_MODEL, final_prompt]`
- **Error Messages**: Updated error messages to reference GitHub CLI and Copilot extension installation

### 2. Prompt File (`docs/prompt.txt`)
- **Removed Gemini-specific instructions**: Removed the shell command help reference that was specific to Gemini CLI
- **Kept core instructions**: All main academic writing instructions remain unchanged

### 3. Documentation Updates
- **GEMINI.md → COPILOT.md**: Renamed and updated file to reflect GitHub Copilot usage
- **README.md**: Updated all references from Gemini to GitHub Copilot CLI
- **AGENTS.md**: Updated to describe GitHub Copilot CLI instead of Gemini agent
- **Installation Requirements**: Added specific instructions for installing GitHub CLI and Copilot extension

### 4. Key Dependencies Changed
- **Before**: Required Gemini CLI installation and PATH configuration
- **After**: Requires:
  - GitHub CLI (`gh`)
  - GitHub Copilot extension (`gh extension install github/gh-copilot`)
  - GitHub authentication (`gh auth login`)

## Installation Instructions for Users

To use the updated system, ensure you have:

1. **GitHub CLI**: Install from https://cli.github.com/
2. **Copilot Extension**: Run `gh extension install github/gh-copilot`
3. **Authentication**: Run `gh auth login` and authenticate with your GitHub account
4. **Copilot Subscription**: Ensure you have an active GitHub Copilot subscription

## Usage Remains the Same

The user workflow remains identical:
1. Place raw files in `docs/input-RawFiles/`
2. Run `python docs/process_inputs.py`
3. Compile the result with `rmarkdown::render("docs/template.Rmd")`

## Benefits of Migration

- **Better Integration**: Leverages GitHub's ecosystem and authentication
- **Improved Model Access**: Access to GPT-4 and other OpenAI models through Copilot
- **Consistent Tooling**: Uses the same CLI that developers use for code assistance
- **Better Support**: GitHub Copilot has extensive documentation and support