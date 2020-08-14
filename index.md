# Titulo


![](https://scitechdaily.com/images/Coronavirus-COVID-19-Animation.gif)

# Cells
A notebook is a list of cells. Cells contain either explanatory text or executable code and its output. Click a cell to select it.

## Code cells
Below is a **code cell**. Once the toolbar button indicates CONNECTED, click in the cell to select it and execute the contents in the following ways:

* Click the **Play icon** in the left gutter of the cell;
* Type **Cmd/Ctrl+Enter** to run the cell in place;
* Type **Shift+Enter** to run the cell and move focus to the next cell (adding one if none exists); or
* Type **Alt+Enter** to run the cell and insert a new code cell immediately below it.

There are additional options for running some or all cells in the **Runtime** menu.



```python
a = 10
a
```




    10



## Text cells
This is a **text cell**. You can **double-click** to edit this cell. Text cells
use markdown syntax. To learn more, see our [markdown
guide](/notebooks/markdown_guide.ipynb).

You can also add math to text cells using [LaTeX](http://www.latex-project.org/)
to be rendered by [MathJax](https://www.mathjax.org). Just place the statement
within a pair of **\$** signs. For example `$\sqrt{3x-1}+(1+x)^2$` becomes
$\sqrt{3x-1}+(1+x)^2.$


## Adding and moving cells
You can add new cells by using the **+ CODE** and **+ TEXT** buttons that show when you hover between cells. These buttons are also in the toolbar above the notebook where they can be used to add a cell below the currently selected cell.

You can move a cell by selecting it and clicking **Cell Up** or **Cell Down** in the top toolbar. 

Consecutive cells can be selected by "lasso selection" by dragging from outside one cell and through the group.  Non-adjacent cells can be selected concurrently by clicking one and then holding down Ctrl while clicking another.  Similarly, using Shift instead of Ctrl will select all intermediate cells.

# Working with python
Colaboratory is built on top of [Jupyter Notebook](https://jupyter.org/). Below are some examples of convenience functions provided.

Long running python processes can be interrupted. Run the following cell and select **Runtime -> Interrupt execution** (*hotkey: Cmd/Ctrl-M I*) to stop execution.


```python
import time
print("Sleeping")
time.sleep(30) # sleep for a while; interrupt me!
print("Done Sleeping")
```

    Sleeping



    ---------------------------------------------------------------------------
    KeyboardInterrupt                         Traceback (most recent call last)

    <ipython-input-3-626f81edbca4> in <module>()
          1 import time
          2 print "Sleeping"
    ----> 3 time.sleep(30) # sleep for a while; interrupt me!
          4 print "Done Sleeping"


    KeyboardInterrupt: 


## System aliases

Jupyter includes shortcuts for common operations, such as ls:


```python
!ls /bin
```

    [0m[01;36march[0m@      [01;32mdmesg[0m*          [01;32mls[0m*          [01;32mpwd[0m*        [01;32mtrue[0m*
    [01;36mawk[0m@       [01;32mdnsdomainname[0m*  [01;32mlsmod[0m*       [01;32mreadlink[0m*   [01;32mumount[0m*
    [01;36mbasename[0m@  [01;32mdomainname[0m*     [01;32mmail[0m*        [01;36mred[0m@        [01;32muname[0m*
    [01;32mbash[0m*      [01;32mecho[0m*           [01;32mmkdir[0m*       [01;32mrm[0m*         [01;32muncompress[0m*
    [01;36mbunzip2[0m@   [01;36med[0m@             [01;32mmknod[0m*       [01;32mrmdir[0m*      [01;32musleep[0m*
    [01;32mbusybox[0m*   [01;32megrep[0m*          [01;32mmktemp[0m*      [01;32mrun-parts[0m*  [01;32mver[0m*
    [01;36mbzip2[0m@     [01;32mfalse[0m*          [01;32mmore[0m*        [01;32msed[0m*        [01;32mwhich[0m*
    [01;32mcat[0m*       [01;32mfgrep[0m*          [01;32mmount[0m*       [01;36msh[0m@         [01;34mwrapper_checkpoints[0m/
    [01;32mchgrp[0m*     [01;36mgawk[0m@           [01;32mmountpoint[0m*  [01;32msleep[0m*      [01;32mzcat[0m*
    [01;32mchmod[0m*     [01;32mgrep[0m*           [01;32mmv[0m*          [01;36msort[0m@       [01;32mzcmp[0m*
    [01;32mchown[0m*     [01;32mgunzip[0m*         [01;32mnc[0m*          [01;32mstty[0m*       [01;32mzdiff[0m*
    [01;32mcp[0m*        [01;32mgzexe[0m*          [01;36mnetcat[0m@      [01;32msu[0m*         [01;32mzegrep[0m*
    [01;32mcpio[0m*      [01;32mgzip[0m*           [01;32mnetstat[0m*     [01;32msync[0m*       [01;32mzfgrep[0m*
    [01;36mcsh[0m@       [01;32mhostname[0m*       [01;36mnice[0m@        [01;32mtailf[0m*      [01;32mzforce[0m*
    [01;36mcut[0m@       [01;36migawk[0m@          [01;36mpidof[0m@       [01;32mtar[0m*        [01;32mzgrep[0m*
    [01;32mdate[0m*      [01;32mkill[0m*           [01;32mping[0m*        [01;36mtcsh[0m@       [01;32mzless[0m*
    [01;32mdd[0m*        [01;32mln[0m*             [01;32mping6[0m*       [01;32mtempfile[0m*   [01;32mzmore[0m*
    [01;32mdf[0m*        [01;32mlogin[0m*          [01;32mps[0m*          [01;32mtouch[0m*      [01;32mznew[0m*


That `!ls` probably generated a large output. You can select the cell and clear the output by either: 

1. Clicking on the clear output button (x) in the toolbar above the cell; or
2. Right clicking the left gutter of the output area and selecting "Clear output" from the context menu.

Execute any other process using `!` with string interpolation from python variables, and note the result can be assigned to a variable:


```python
message = 'Colaboratory is great!'
foo = !echo -e '$message\n$message'
foo
```




    ['Colaboratory is great!', 'Colaboratory is great!']



## Magics
Colaboratory shares the notion of magics from Jupyter. There are shorthand annotations that change how a cell's text is executed. To learn more, see [Jupyter's magics page](http://nbviewer.jupyter.org/github/ipython/ipython/blob/1.x/examples/notebooks/Cell%20Magics.ipynb). 



```python
%%html
<marquee style='width: 30%; color: blue;'><b>Whee!</b></marquee>
```


<marquee style='width: 30%; color: blue;'><b>Whee!</b></marquee>



```python
%%html
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 450 400" width="200" height="200">
  <rect x="80" y="60" width="250" height="250" rx="20" style="fill:red; stroke:black; fill-opacity:0.7" />
  <rect x="180" y="110" width="250" height="250" rx="40" style="fill:blue; stroke:black; fill-opacity:0.5;" />
</svg>
```


<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 450 400" width="200" height="200">
  <rect x="80" y="60" width="250" height="250" rx="20" style="fill:red; stroke:black; fill-opacity:0.7" />
  <rect x="180" y="110" width="250" height="250" rx="40" style="fill:blue; stroke:black; fill-opacity:0.5;" />
</svg>


## Tab-completion and exploring code

Colab provides tab completion to explore attributes of Python objects, as well as to quickly view documentation strings. As an example, first run the following cell to import the  [`numpy`](http://www.numpy.org) module.


```python
import numpy as np
```

If you now insert your cursor after ``np.random.`` and press **Tab**, you will see the list of available completions within the ``np.random`` submodule.


```python
np.random.
```

If you type an open parenthesis followed by the **Tab** key after any function or class in the module, you will see a pop-up of its documentation string:


```python
np.random.rand(
```

To open the documentation in a persistent pane at the bottom of your screen, add a **?** after the object or method name and execute the cell using **Shift+Enter**:


```python
np.random?
```

## Exception Formatting

Exceptions are formatted nicely in Colab outputs:


```python
x = 1
y = 4
z = y/(1-x)
```


    ---------------------------------------------------------------------------
    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-14-dc39888fd1d2> in <module>()
          1 x = 1
          2 y = 4
    ----> 3 z = y/(1-x)
    

    ZeroDivisionError: integer division or modulo by zero


## Rich, interactive outputs
Until now all of the generated outputs have been text, but they can be more interesting, like the chart below. 


```python
import numpy as np
from matplotlib import pyplot as plt

ys = 200 + np.random.randn(100)
x = [x for x in range(len(ys))]

plt.plot(x, ys, '-')
plt.fill_between(x, ys, 195, where=(ys > 195), facecolor='g', alpha=0.6)

plt.title("Fills and Alpha Example")
plt.show()
```


![png](output_27_0.png)


# Integration with Drive

Colaboratory is integrated with Google Drive. It allows you to share, comment, and collaborate on the same document with multiple people:

* The **SHARE** button (top-right of the toolbar) allows you to share the notebook and control permissions set on it.

* **File->Make a Copy** creates a copy of the notebook in Drive.

* **File->Save** saves the File to Drive. **File->Save and checkpoint** pins the version so it doesn't get deleted from the revision history. 

* **File->Revision history** shows the notebook's revision history. 

## Commenting on a cell
You can comment on a Colaboratory notebook like you would on a Google Document. Comments are attached to cells, and are displayed next to the cell they refer to. If you have **comment-only** permissions, you will see a comment button on the top right of the cell when you hover over it.

If you have edit or comment permissions you can comment on a cell in one of three ways: 

1. Select a cell and click the comment button in the toolbar above the top-right corner of the cell.
1. Right click a text cell and select **Add a comment** from the context menu.
3. Use the shortcut **Ctrl+Shift+M** to add a comment to the currently selected cell. 

You can resolve and reply to comments, and you can target comments to specific collaborators by typing *+[email address]* (e.g., `+user@domain.com`). Addressed collaborators will be emailed. 

The Comment button in the top-right corner of the page shows all comments attached to the notebook.
