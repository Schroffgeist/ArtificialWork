# GitHub Copilot CLI Instructions (for Academic Paper Generation)

## 1. Objective

## User Information

*   **GitHub Username**: [Your-Username]

The primary goal is to automate the creation of a well-structured academic paper in PDF format. This process is driven by a Python script that orchestrates the analysis and modification of the document by GitHub Copilot CLI.

## 2. Project File Structure

- **`COPILOT.md`**: This file. Contains the high-level instructions for the LLM.
- **`process_inputs.py`**: The main Python script that automates the entire workflow.
- **`prompt.txt`**: A template file containing the detailed instructions for GitHub Copilot CLI.
- **`input-RawFiles/`**: A directory where the user places all their raw notes, data, and reference files.
- **`template.Rmd`**: The main R Markdown template file that will be modified.
- **`sage-plots-for-template.tex/Bibliografia.bib`**: The bibliography file that will be updated.

## 3. Automated Workflow

This project uses an automated script, `process_inputs.py`, to manage the paper generation process. The script performs the following actions:

1.  **Scans for Inputs**: It searches the `input-RawFiles/` directory for all user-provided files.
2.  **Constructs Prompt**: It reads the instructions from `prompt.txt` and appends the list of found file paths to it.
3.  **Executes GitHub Copilot CLI**: It calls the GitHub Copilot CLI (`gh copilot chat`), feeding it the constructed prompt. This instructs Copilot to perform the core content generation and file editing tasks.

### GitHub Copilot's Role

When executed by the script, GitHub Copilot CLI will perform the following based on the instructions in `prompt.txt`:

1.  **Parse All Inputs**: Read and analyze the content from all the file paths provided in the prompt.
2.  **Extract & Update Bibliography**: Identify references and append them as correctly formatted BibTeX entries to `sage-plots-for-template.tex/Bibliografia.bib`.
3.  **Extract & Update Rmd**: Identify personal info, document metadata, and the core content. Use this to replace the placeholder values in the YAML header and body of `template.Rmd`.
4.  **Extract & update Headers**: Identify information that need parametrization and complement changes from `template.Rmd` to match in `Headers.tex`.
5.  **Structure and Enhance Content**: This is the most critical step. The LLM will:
    -   Organize the raw notes into a standard academic structure (Introduction, Main Body, Conclusion, etc.).
    -   Write missing sections (like the introduction or conclusion) if they are not present in the notes.
    -   Ensure a coherent flow by writing transition sentences and rephrasing content for clarity and an academic tone.
    -   Integrate LaTeX-style citations (`[@key]`) throughout the text, linking to the entries in the `.bib` file.

### Final Step: Manual Compilation

After the script and GitHub Copilot CLI have finished, the user must manually compile the final PDF using their R environment:

```R
rmarkdown::render("template.Rmd")
```
