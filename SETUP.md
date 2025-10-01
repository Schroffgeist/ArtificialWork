# Academic Paper Template Setup Guide

This guide will help you set up and customize the Academic Paper Template for your institution and specific needs.

## Quick Start

1. **Use this template** to create your own repository
2. **Update personal information** in the files listed below
3. **Replace example content** with your research materials
4. **Run the automation script** to generate your paper

## Files to Customize

### 1. Personal Information (`docs/input-RawFiles/Datos.txt`)
Update this file with your actual information:
- Student name and ID
- Course information
- Professor details
- Due dates
- Institution location

### 2. University Branding (`docs/Headers.tex`)
Replace the placeholder university information:
- University name
- Faculty/School name
- Division/Department
- Degree program
- Logo references (update to your institution's logos)

### 3. Document Metadata (`docs/template.Rmd`)
The YAML header contains default placeholders that will be populated automatically from your input files:
- `assignment_title`
- `subject_name`
- `prof_name`
- `student_name`
- etc.

### 4. Research Content (`docs/input-RawFiles/`)
Replace the example files with your actual research materials:
- Delete `sample-notes.md` and `bibliography-sources.txt`
- Add your research notes, bibliographies, and draft content
- Keep `Datos.txt` but update it with your information

## Logo Files

The template references two logo files in `docs/sage-plots-for-template.tex/Logos/`:
- `University-Logo-Blue` (main university logo)
- `Faculty-Logo-Blue` (faculty/school logo)

Replace these with your institution's logos, or update the references in `Headers.tex`.

## Language Customization

The template includes both English and Spanish elements. To fully customize for your language:

1. **Document language** - Update the `lang` parameter in `template.Rmd`
2. **Date formatting** - Modify the `datetime2` package settings in `Headers.tex`
3. **Static text** - Update labels like "Period:", "Subject:", "Student:", etc. in `Headers.tex`

## Bibliography Style

The template uses `biblatex` with `apalike` style. To change:
1. Update `biblio-style` in `template.Rmd`
2. Ensure your references in `.bib` files match the chosen style

## Testing Your Setup

1. Place your research files in `docs/input-RawFiles/`
2. Run: `python docs/process_inputs.py`
3. Compile: `rmarkdown::render("docs/template.Rmd")` in R

## Troubleshooting

### Common Issues:
- **Missing logos**: Update logo references or add placeholder images
- **LaTeX errors**: Check that all required packages are installed
- **Bibliography errors**: Ensure your `.bib` file has valid BibTeX format
- **Font issues**: The template uses specific fonts (Cousine, Noto Sans Math) - install these or change font settings

### Getting Help:
- Check the documentation in `docs/COPILOT.md`
- Review the example files for proper formatting
- Ensure all prerequisites are installed (see main README.md)

## Advanced Customization

For advanced users who want to modify the template further:
- **Page layout**: Modify geometry settings in `template.Rmd`
- **Color scheme**: Update color definitions in `Headers.tex`
- **Header/footer**: Customize the fancy page styles in `Headers.tex`
- **Table of contents**: Modify the ToC generation in `BeforeBody.tex`

## Contributing

If you improve this template, consider contributing back:
1. Fork the original repository
2. Make your improvements
3. Submit a pull request with your enhancements

This helps the community benefit from your customizations while keeping individual details private.