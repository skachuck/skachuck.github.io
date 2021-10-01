---
layout: mathpost
title:  "Getting Started with Notebooks"
date:   2021-02-23 11:42:44 -0500
type: teaching
categories: 474 climate modeling
course: 'CLIMATE474: Ice sheets and Climate'
---

# Getting started with the Jupyter Notebook

Welcome to this introduction to [Jupyter Notebooks](https://jupyter.org/)! The advantage of notebooks is that they can include explanatory text, code, and plots in the same document.

**This makes of notebooks an ideal playground for explaining and learning new things without having to jump between several documents. Thanks to binder, you can run them in your web browser without requiring to install anything!**

This document itself is a notebook. It is a simple text file with a `.ipynb` file path ending. If you opened this notebook via an OGGM-Edu Binder link, it is opened in a platform which is called [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/). "JupyterLab" is the development environment allowing you to navigate between notebooks (navigation bar on the left), (re-)start them, and much more. Here, we will focus on the notebooks themselves.

## First steps

At first sight the notebook looks like a text editor. Below this line, you can see a **cell**. The default purpose of a cell is to write code:


```python
# Click on this cell, so that its frame gets highlighted
m = 'Hello'
print(m)
```

You can write one or more lines of code in a cell. You can **run** this code by clicking on the "Run" button from the toolbar above when the cell's frame is highlighted. Try it now! 

Clicking "play" through a notebook is possible, but it is much faster to use the keybord shortcut instead: `[Shift+Enter]`. Once you have executed a cell, the next cell is selected. You can **insert** cells in a notebook with the `+` button in the toolbar. Again, it is much faster to learn the keybord shortcut for this: `[Ctrl+m]` or `[ESC]` to enter in command mode (blue frame) then press `[a]` to insert a cell "above" the active cell or `[b]` for "below".

Create a few empty cells above and below the current one and try to create some variables.  Instead of clicking on a cell to enter in edit mode press `[Enter]`.

You can **delete** a cell by clicking "Delete" in the "Edit" menu, or you can use the shortcut: `[Ctrl+m]` to enter in command mode then press `[d]` two times!

## More cell editing

When you have a look into the "Edit" menu, you will see that there are more possibilities to edit cells, like:
- **copy** / **cut** and **paste**
- **splitting** and **merging** cells 

and more.


```python
a = 'This cell needs to be splitted.'

b = 'Put the cursor in the row between the variables a and b, then choose [split cell] in the "Edit" menu!'
```

Another helpful command is "Undo delete cell', which is sometimes needed when the key `[d]` was pressed too fast. 

## Writing and executing code

The variables created in one cell can be used (or overwritten) in subsequent cells:


```python
s = 'Hello'
print(s)
```


```python
s = s + ' Python!'
# Lines which start with # are not executed. These are for comments.
s
```

Note that we ommited the `print` commmand above (this is OK if you want to print something at the end of the cell only).

In jupyter notebooks, **code autocompletion** is supported. This is very useful when writing code. Variable names, functions and methods can be completed by pressing `[TAB]`.


```python
# Let's define a random sentence as string.
sentence = 'How Are You?'
```


```python
# Now try autocompletion! Put the cursor behind the 'se' in the next row and press [TAB].
se
```


```python
# Call methods of the string by typing "sentence." and pressing [TAB].
sentence.
```


```python
# Choose for example the method lower() and see what happens when you execute the cell!
sentence.lower()
```

An advantage of notebooks is that each single cell can be executed separately. That provides an easy way to execute code step by step, one cell after another. It is important to notice that the order in which you execute the cells is the order with which the jupyter notebook calculates and saves variables - the execution order therfore depends on **you**, not on the order of the cells in the document. That means that it makes a difference, whether you execute the cells top down one after another, or whether you mix them (cell 1, then cell 5, then cell 2 etc.).

The numbers on the left of each cell show you your order of execution. When a calculation is running longer, you will see an asterisk in the place of the number. That leads us to the next topic:

## Restart or interrupt the kernel

Sometimes calculations last too long and you want to **interrupt** them. You can do this by clicking the "Stop button" in the toolbar.

The "**kernel**" of a notebook is the actual python interpreter which runs your code. There is one kernel per opened notebook (i.e. the notebooks cannot share data or variable between each other). In certain situations (for example, if you got confused about the order of your cells and variable and want a fresh state), you might want to **retart the kernel**. You can do so (as well as other options such as **clearing the output** of a notebook) in the "Kernel" menu in the top jupyterlab bar.

## Errors in a cell 

Sometimes, a piece of code in a cell won't run properly. This happens to everyone! Here is an example:


```python
# This will produce a "NameError"
test = 1 + 3
print(tesT)
```

When a cell ends with an error, don't panic! Nothing we cannot recover from. First of all, the other cells will still run (unless they depend on the output of the failing cell): i.e., your kernel is still active. I you want to recover from the error, adress the problem (here a capsize issue) and re-run the cell. 

## Displaying plots with matplotlib

The most widely used plotting tool for Python is [Matplotlib](http://matplotlib.org/). Its syntax is inspired from Matlab and might be familiar to a few:


```python
# First we need the next line to tell the notebook: display plots in the notebook.
%matplotlib inline

# Now, we import matplotlib:
import matplotlib.pyplot as plt

# We import also the package called numpy (that helps us to play with numbers).
import numpy as np
```


```python
# Let's plot something nice:

# Define a square function of x
x = np.linspace(-1, 1)
y = np.sqrt(1-x**2)
# Plot it.
plt.plot(x, y)
plt.title('My first plot in a notebook');
```

## Interactive plots with Bokeh

[Bokeh](http://bokeh.org) is a plottling library made for the web. It uses another syntax than matplotlib and can be used to display interactive plots. In OGGM-Edu, we sometimes prefer to use interactive plots as they allow to explore the data after plotting it. Here is an example: 


```python
# hvplot is a plotting library relying on bokeh
# you'll need to install it alongside with pandas for this cell to work
import hvplot.pandas

# pandas is a very useful data analysis library
import pandas as pd

# This makes the plot
ts = pd.Series(index=x, data=y)
ts.hvplot().opts(title='An interactive plot', width=500)
```

## Formatting your notebook with text, titles and formulas

The default role of a cell is to run code, but you can tell the notebook to format a cell as "text" by clicking in the menu bar on "Cell", choose "Cell Type" $\rightarrow$ "Markdown". The current cell will now be transformed to a normal text.
Again, there is a keyboard shortcut for this: press `[Ctrl+m]` to enter in command mode and then `[m]` to convert the active cell to text. The opposite (converting a text cell to code) can be done with `[Ctrl+m]` to enter in command mode and then `[y]`.

As we have seen, the notebook editor has two simple modes: the "command mode" to navigate between cells and activate them, and the "edit mode" to edit their content. To edit a cell you have two choices:
- press `[enter]` on a selected (highlighted) cell 
- double click on a cell (any cell)

Now, try to edit the cell below!

A text cell is formatted with the [Markdown](https://en.wikipedia.org/wiki/Markdown) format, e.g. it is possible to write lists:
- item 1
- item 2

Numbered lists:
1. part a
2. part b

Titles with the `#` syntax (the number of `#` indicating the level of the title:

#### This is a level 4 title (with 4 `#` symbols)

Mathematical formulas can be written down with the familiar Latex notation:

$$ E = m c^2$$

You can also write text in **bold** or *cursive*.

## Download a notebook

Jupyter notebooks can be downloaded in various formats:

- Standard notebook (`*.ipynb`): a text file only useful within the Jupyter framework
- Python (`*.py`): a python script that can be executed separately. 
- HTML (`*.html`): an html text file that can be opened in any web browser (doens't require python or jupyter!) 
- ... and a number of other formats that may or may not work depending on your installation

**To download a jupyter notebook in the notebook format** (`.ipynb`), select the file on the left-hand side bar, right-click and select "Download". Try it now!

**For all other formats**, go to the "File" menu, then "Export notebook as..."

## Take home points 

- jupyter notebooks consist of cells, which can be either code or text (not both)
- one can navigate between cells in "control mode" (`[ctrl+m]`) and edit them in "edit mode" (`[enter]` or double click)
- to exectute a cell, do: `[shift+enter]`
- the order of execution of cells *does* matter
- a text cell is written in markdown format, which allows lots of fancy formatting

These were the most important features of jupyter-notebook. In the notebook's menu bar the tab "Help" provides links to the documentation. Keyboard shortcuts are listed in the "Palette" icon on the left-hand side toolbar. Furthermore, there are more tutorials [on the Jupyter website](https://jupyter.org/try). 

But with the few commands you learned today, you are already well prepared for the OGGM-Edu experiments!

[Back to the OGGM-Edu table of contents](welcome.ipynb)
