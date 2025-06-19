# Style Guide for Projects in the MLAI


## Well before a publication:

Please see our overall guide on code & project formatting [here](https://github.com/AdaptiveMotorControlLab/WorkspaceTemplate/blob/main/README.md).

### Main Principles 🔨 Organize your code & data:
- For experimental and ML projects, please use [DataJoint/databases](https://www.datajoint.com/)
- Be sure you work under a lab repo, typically called "https://github.com/AdaptiveMotorControlLab/YourName_workspace".
- For larger projects (DLC, CEBRA, ExperimentalPipelines, you should be sure your "final" work gets into a pipeline; talk to Mackenzie about this)
- Lab Specific: please check the [CommonHelperCode](https://github.com/AdaptiveMotorControlLab/CommonHelperCode) for useful tips & scripts, and contribute your own!

### Main Principles 🚧 Format your code & documentation:
- In the lab we use the [Google Style Guide](https://google.github.io/styleguide/pyguide.html) for code. Please review this.
- In the lab we use the [semantic versioning of code](https://semver.org/). Please review this.
- In the lab we use the code formatting we outline in the main README [here](https://github.com/AdaptiveMotorControlLab/WorkspaceTemplate/blob/main/README.md).
- As soon as you start a repo, start a JupterBook! Please see [here](https://github.com/AdaptiveMotorControlLab/WorkspaceTemplate/blob/main/README.md), and this repo has the template.



## Ready to write up your work and share your hard work, data, & code?
Here is how to do so most efficiently with me.

- 🚨 First, I recommend having a one-on-one so we can lay out the paper sketch, authors, data and code sharing plan together if not already done.
- 📝  I ask that we use [overleaf](https://www.overleaf.com/project) for **manuscripts**! Please ask me to start a template to share with you.
- 🗺 I ask we use [figma](https://www.figma.com/) for **figures**; you can start a free educational group (or ask me to start one). Please then link this in the paper basecamp group.
- If you have a deadline (ICCV/NeurIPS, etc), you must have everything ready **1 week before the deadline** and schedule a meeting to go over it (see Timeline below).

### How to organize this all with Basecamp:
- 🔗 Please link the development code repo code in basecamp
- 🔗 Please link the overleaf
- 🔗 Please link the figma file

Collectively, your basecamp project should look like this:
![demo](https://github.com/user-attachments/assets/e21bdee1-ede6-4463-a65f-0d1dff3d224f)



## Styles for plots, figures, and how to produce them
- We use `matplotlib` and `seaborn` in python.
- **Every plot in a paper must be reproducible in a Jupyter Notebook**. This means it loads the data (from datajoint/ possible later figshare or zenodo), plots it, and saves it.
- By the time we are ready to submit a paper, it must have a `AMCL\PaperName-figures` repo.
  - Here are examples from the lab:
    -  CellSeg3D: https://github.com/C-Achard/cellseg3d-figures
    -  CEBRA: https://github.com/AdaptiveMotorControlLab/CEBRA-demos
- I really like the plots in [CEBRA](https://www.nature.com/articles/s41586-023-06031-6), which you can find here: https://github.com/AdaptiveMotorControlLab/cebra-figures

### Example plotting style:
- Here is an example, be sure to note the **font, size, broken axis, transparency output**, etc:

```python
plt.figure(figsize=(3.5, 3.5), dpi = 200)
ax = plt.subplot(111)

keys = ['cebra', 'pivae', 'autolfads', 'tsne', 'umap']
df = pd.DataFrame(synthetic_scores)
sns.stripplot(data=df[keys] * 100, color="black", s=3, zorder=1, jitter=0.15)
sns.scatterplot(data=df[keys].median() * 100, color="orange", s=50)
plt.ylabel("$R^2$", fontsize=20)
plt.yticks(
    np.linspace(0, 100, 11, dtype=int), np.linspace(0, 100, 11, dtype=int), fontsize=20
)
plt.ylim(70, 100)
ax.spines["right"].set_visible(False)
ax.spines["top"].set_visible(False)
ax.tick_params(axis="both", which="major", labelsize=15)
ax.tick_params(axis = 'x',   rotation = 45)
ax.set_xticklabels(
  ['CEBRA', 'piVAE', 'autoLFADS', 'tSNE', 'UMAP'],
)
sns.despine(
    left=False,
    right=True,
    bottom=False,
    top=True,
    trim=True,
    offset={"bottom": 40, "left": 15},
)
plt.savefig('figure1_synthetic_comparison.jpg', bbox_inches = "tight", transparent = True)
plt.savefig('figure1_synthetic_comparison.svg', bbox_inches = "tight", transparent = True)
```
#### THEN: 🚨 Put the SVG into figma, AND for the final versions, make a white axis page & versions 🙏:

Modify by adding:
```python
for spine in ax.spines.values():
    spine.set_color("white")
ax.tick_params(colors="white")
ax.yaxis.label.set_color("white")
ax.xaxis.label.set_color("white")
```


### Timeline Major Point:

For conference submissions, all papers must be in final form 1 week prior to the deadline.
There will be no exceptions going forward.
This gives us needed time to reflect, refine writing, get some distance, and ask colleagues for feedback.
It also gives us time to prepare the code submission, and potentially arXiv the work -- which is always preferred.
We should not be submitting manuscripts to conferences we would not want publicly read!
