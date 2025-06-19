# What is Jupyterbook?

We use JupyterBook for documentation and sharing computational notebooks. [Here](https://www.nature.com/articles/d41586-018-07196-1) is a nice article for motivation.

📑 The documentation: https://jupyterbook.org/en/stable/intro.html


## Quick start
- have your repo cloned and run this to generate a starting template:
```python
jupyter-book create --cookiecutter YourClonedRepo/
```

## OR Build from the template provided in this Repo!

(1) Use and adapt the two template files (_toc.yml, _config.yml) to your main code base, and be sure to keep the `docs` structure, i.e.,
```
/docs
├── /images
│   └── logo.png         # add logo here
├── intro.md             # main welcome page

```
(2) write in markdown (or myst) your docs, as usual:
- for an example: https://github.com/DeepLabCut/DeepLabCut/blob/mmain/docs/intro.md

(3) to build your docs & hosting see here: https://jupyterbook.org/en/stable/publish/gh-pages.html

TL;DR in the main repo run:
```python
jupyter-book build .
```
and then follow terminal prompt (check errors, etc)- viola!


## Deployment:

To then deploy the book live, see: https://jupyterbook.org/en/stable/publish/gh-pages.html#automatically-host-your-book-with-github-actions

In short, Go to Settings > Pages and set up anaction to deploy to a new branch (that you never merge) called `gh-pages`:

![Screen Shot 2025-06-17 at 2 20 19 PM](https://github.com/user-attachments/assets/17d13802-6543-4859-ac09-7abbd491277d)
