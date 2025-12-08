# DoY Data Handbook

Dynamics of Youth (DoY) has the ambition to make all projects within the strategic theme as FAIR (Findable, Accessible, Interoperable, Reusable) as possible.

The DoY Data Handbook is a guide on RDM and FAIRifying data, tailored to the DoY community. It is not meant to reinvent the wheel of existing information, but curate what is available in a brief and practical manner, as well as incorporate resources already circulating within the DoY community.

This repository hosts the source files and configuration used to publish the DoY Data Handbook at https://utrechtuniversity.github.io/doy-data-handbook/.

## Repository Structure

```
/
├── book/                        # All chapters of the handbook (each is a .qmd file)
│   ├── introduction.qmd
│   ├── data-management.qmd
│   ├── privacy.qmd
│   └── ...
│
├── images/                      # Figures and static assets
│
├── styles/                      # Optional custom CSS / styling
│
├── _quarto.yml                  # Main configuration file for the Quarto Book
│                                # (title, chapters, settings, formats)
│
├── DoY-Data-Handbook.Rproj      # R project file
│
├── README.md
└── .github/workflows/           # GitHub Actions for automated rendering + deployment
```

## Required Tools

To work with this repository, you will need:

- **R**: required for working within the RStudio/Quarto environment
- **RStudio**: recommended editing environment, but other environments are also usable
- **Quarto**: required to build and preview the book locally
- **Git & GitHub**: to clone the project and push updates + deploy website

### Installation

Most of these tools are available via the UU Software Center.

- **R**: https://cran.r-project.org/
- **RStudio**: https://posit.co/download/rstudio-desktop/
- **Quarto**: https://quarto.org
- **Git**: https://git-scm.com

## Getting Started

1. Clone the repository

```
git clone https://github.com/UtrechtUniversity/doy-data-handbook.git
cd doy-data-handbook
```

2. Open the project in RStudio

Double-click: `DoY-Data-Handbook.Rproj`
This ensures the correct working directory and integrates RStudio with Quarto.

## Working With the Handbook

The handbook is structured as a Quarto Book, where each chapter is a `.qmd` file located in the `book/` directory.

### Adding a New Chapter

_Step 1_ — Create the chapter

Add a new `.qmd` file inside the `book/` directory, for example:

`book/my-new-chapter.qmd`

_Step 2_ — Register the chapter in `_quarto.yml`

Open the `_quarto.yml` file and find the `chapters:` section.

Add your chapter to the list, in the correct order:

```
chapters:
  - introduction.qmd
  - data-management.qmd
  - my-new-chapter.qmd
```

This determines the chapter sequence in the rendered book.

_Step 2_ — Use Markdown to write the chapter

For hints on how to use Markdown, see: https://www.markdownguide.org/ 
Note that any images or assets should be saved in their respective folder.

### Previewing the Handbook

There are two ways you can preview the book locally to check layout, navigation, and formatting.

1. From the Terminal in RStudio:

`quarto preview`

2. Using the _Render → Preview_ Book button in RStudio.

This opens a live-reloading preview in your browser.

### Rendering and Deployment

This repository uses GitHub Actions to render and deploy the book automatically.
Whenever you push changes to the main branch:

-> GitHub Actions starts running
-> The book is rendered to HTML using Quarto
-> The book is deployed via GitHub Pages

To trigger deployment, simply push your changes to the repository:

```
git add .
git commit -m "Update chapter(s)"
git push
```

The deployed site will update automatically once the workflow completes.

Reference

For more information on Quarto Books, please refer to the extensive documentation: https://quarto.org/docs/books/
