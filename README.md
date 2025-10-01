# Academic Paper Template

This repository provides a powerful and flexible template for creating academic papers using R Markdown and LaTeX. It automates the process of turning research notes into a fully formatted, publication-ready document using GitHub Copilot CLI.

## ✨ Features

- **Automated Content Generation**: Transform raw notes into structured academic papers
- **Professional LaTeX Formatting**: Beautiful, publication-ready output
- **Flexible Bibliography Management**: Automatic BibTeX generation and formatting
- **Customizable Templates**: Easy to adapt for different institutions and requirements
- **AI-Powered**: Uses GitHub Copilot CLI for intelligent content processing
- **Multi-language Support**: Easily customizable for different languages

## 🚀 Quick Start

### Option 1: Use as Template (Recommended)
1. Click the "**Use this template**" button above
2. Create your new repository
3. Clone to your local machine
4. Follow the setup guide below

### Option 2: GitHub CLI
```bash
gh repo create MyAcademicPaper --public --template [YourUsername]/Academic-Paper-Template --clone
```

## 📁 Project Structure

```
├── docs/
│   ├── template.Rmd              # Main R Markdown template
│   ├── Headers.tex               # LaTeX headers and styling
│   ├── BeforeBody.tex           # Title page and front matter
│   ├── process_inputs.py        # Automation script
│   ├── prompt.txt               # AI prompt template
│   ├── input-RawFiles/          # Your research materials go here
│   │   ├── Datos.txt           # Personal/course information
│   │   ├── sample-notes.md     # Example research notes
│   │   └── README.md           # Input files guide
│   └── sage-plots-for-template.tex/
│       └── Bibliografia.bib     # Bibliography file
├── SETUP.md                     # Detailed setup guide
└── README.md                    # This file
```

## 🔧 Setup

### Prerequisites
- **Python 3.x**
- **GitHub CLI** with Copilot extension
- **R and RStudio**
- **LaTeX distribution** (MiKTeX, TeX Live, etc.)
- **R packages**: `rmarkdown`, `knitr`, etc.

### Installation Steps

1. **Install GitHub CLI and Copilot**:
   ```bash
   # Install GitHub CLI: https://cli.github.com/
   gh extension install github/gh-copilot
   gh auth login
   ```

2. **Install R packages**:
   ```r
   install.packages(c("rmarkdown", "knitr", "tidyverse", "kableExtra"))
   ```

3. **Customize for your institution**:
   - Update `docs/input-RawFiles/Datos.txt` with your information
   - Modify university details in `docs/Headers.tex`
   - Replace logos in `docs/sage-plots-for-template.tex/Logos/`

## 📝 Usage

### Step 1: Prepare Your Materials
1. Add your research notes, drafts, and bibliographies to `docs/input-RawFiles/`
2. Update `Datos.txt` with your personal and course information
3. See `docs/input-RawFiles/README.md` for detailed guidance

### Step 2: Generate Content
```bash
cd docs
python process_inputs.py
```

### Step 3: Compile to PDF
```r
rmarkdown::render("docs/template.Rmd")
```

## 🤖 How It Works

1. **Input Analysis**: The system reads all files in `input-RawFiles/`
2. **AI Processing**: GitHub Copilot CLI analyzes content and extracts key information
3. **Template Population**: Metadata and content are inserted into the R Markdown template
4. **Bibliography Generation**: References are formatted and added to the `.bib` file
5. **Content Structuring**: Raw notes are organized into academic sections
6. **PDF Generation**: R Markdown compiles everything into a professional PDF

## 📖 Documentation

- [`SETUP.md`](SETUP.md) - Detailed setup and customization guide
- [`docs/COPILOT.md`](docs/COPILOT.md) - AI automation details
- [`docs/input-RawFiles/README.md`](docs/input-RawFiles/README.md) - Input file guide

## 🎨 Customization

The template is highly customizable:

- **Styling**: Modify LaTeX formatting in `Headers.tex`
- **Layout**: Adjust page geometry and spacing
- **Colors**: Change the color scheme
- **Fonts**: Update font selections
- **Language**: Adapt for different languages
- **Institution**: Add your university's branding

See `SETUP.md` for detailed customization instructions.

## 📋 Example Output

The template generates professional academic papers with:
- Custom title page with university branding
- Automated table of contents, figures, and tables
- Properly formatted citations and bibliography
- Professional headers and footers
- Consistent academic styling throughout

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your improvements
4. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Issues**: Use GitHub Issues for bug reports and feature requests
- **Discussions**: Use GitHub Discussions for questions and community support
- **Documentation**: Check the docs folder for detailed guides

## 🙏 Acknowledgments

- Built for academic researchers and students
- Powered by GitHub Copilot CLI
- Uses R Markdown and LaTeX for professional formatting
- Inspired by the need for automated academic writing workflows