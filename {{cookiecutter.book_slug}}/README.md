# CLI
 
`jupyter-book clean [OPTIONS] PATH_BOOK`

% Manipulate MyST markdown files
`jupyter-book myst [OPTIONS] COMMAND [ARGS]...`

% Add Jupytext metadata for your markdown file(s),
`jupyter-book myst init [OPTIONS] [PATH]...`

`jupyter-book create [OPTIONS] PATH_BOOK` 
`--cookiecutter`

<!-- Generate a Sphinx conf.py representation of the build configuration. -->

`jupyter-book config sphinx [OPTIONS] PATH_SOURCE`

## Template

- [ascii codes](https://www.ascii-code.com/)
- [ascii table](https://www.asciitable.com/)

An example template created by this cookiecutter is shown below:

```
my_book
├── hooks
├── .github
│   └── workflows
│       └── deploy.yml
├── tests
│
├── my_book
│   ├── _static
│   ├── _templates
│   ├── _images
│   │   ├── favicon.ico
│   │   └── logo.png
│   │ 
│   ├── 01_setup
│   │   ├── setup.md
│   │   ├── installation.md
│   │   └── configuration.md
│   │ 
│   ├── 02_basic_usage
│   │   ├── basic_usage.md
│   │   └── basic_examples.md
│   │ 
│   ├── 03_advanced_usage
│   │   ├── advanced_usage.md
│   │   └── advanced_examples.md
│   │ 
│   ├── _config.yml
│   ├── _toc.yml
│   ├── intro.md
│   └── references.bib
│   
├── .gitignore
├── cookiecutter.json
├── LICENSE
├── README.md
└── requirements.txt
```