# ee106a_jupyterbook
Online textbook for 106A.

## Converting LaTeX to markdown files
You can use PanDoc as an automatic file converter to go from your .tex files to markdown, which is what the JupyterBook uses.
Install pandoc [here](https://pandoc.org/installing.html).\
Once you have pandoc installed, you can convert a file from .tex to .md with the following command:
```
pandoc -s example4.tex -o example5.md
```
Note that there still is some reformatting you'll have to do after using this, but on the whole it saves you a lot of time! One big change-
you'll have to add blank spaces in between your math align blocks and the surrounding text, otherwise it won't render correctly.

## Doing math in markdown
Math in markdown works pretty much the same as in LaTex. You can use dollar signs to do inline math, for example: $\int_0^\infty x^2 dx$.
You can use double dollar signs to start an "align" environment. Make sure to include an extra space between your text and the align block on either end.
For example:

$$
\sum_{i = 0}^{\infty}\frac{1}{i^2}
$$

In the file example_md_file.md, I've included a couple more examples of how to do this. Note that you *shouldn't* use the option to compile ams mathd
directly. This messes a bunch of stuff up with the inline representations. It's much simpler to just use the normal markdown representation, 
especially since we can run the pandoc converter to do the conversion for us.

Note that we have a theorem package imported that allows us to represent theorems in markdown. Feel free to check out the syntax for this 
[here](https://sphinx-proof.readthedocs.io/en/latest/syntax.html#lemmas).

## Adding new files
If you add a new markdown file to the textbook, you have to update the table of contents file (_toc.yml) to make it visible. To insert it 
where you wish in the table of contents, under the "chapters:" section, you can add files as follows:
```
- file
- file2
- yournewfile
```
Note that you should just give the file name and not the extension. It automatically adds .md to the end of each.

## Building your changes
Once you've added your file or made the changes you want, you'll have to build the book to see your changes take effect. To build, go 
one folder out of the ee106a_jupyterbook repository and run the following:
```
jupyter-book build ./ee106a_jupyterbook/
```
Once you run this, the compiler will build the book. It will also provide you with a file extension you can paste into your browser. If you paste this
into your browser, you'll be able to preview what your changes will look like without actually updating the website.

## Publishing changes to the website
Note: your edits should be made in the master branch, not the gh-pages branch!
When you're ready to publish your changes to the website, you should first push your edits to master.
```
git add .
git commit -m "I made these edits"
git push origin master
```
Once you've pushed your changes to the master branch, you'll be ready to upload your changes to the github pages site, where the book is hosted online.
To do this, go to the root folder of your github repository (.../ee106a_jupyterbook) and run the following:
```
ghp-import -n -p -f _build/html
```
This will update your build changes to the website. Note that it might take a few minutes for the changes to take effect.
