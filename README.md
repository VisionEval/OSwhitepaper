# OSwhitepaper
White paper on open source principles and practical applications for VisionEval 

View the rendered [HTML version of the whitepaper here](http://htmlpreview.github.io/?https://github.com/VisionEval/OSwhitepaper/blob/master/VEwhitepaper.html)

See the [Word version here](https://github.com/VisionEval/OSwhitepaper/blob/master/VEwhitepaper.docx?raw=true).

## How to contribute comments or edits

If you are logged in and a contributor to this repostory, you can add comments or edits to the white paper using the following methods:

1. Directly edit the `VEwhitepaper.md` file on GitHub. Changes will be tracked in the git history
+ On GitHub, select the `VEwhitepaper.md` file 
+ Click the pencil icon to make edits to the text
+ Make changes directly to the text
+ Scroll down to the bottom of the page and add a comment about what the changes entail
+ Click 'Commit changes' to commit changes to the master branch.
+ Alternatively, can make edits and create a pull request

2. Create an Issue to make a general comment, for example regarding overall structure or the direction of the white paper 
+ Click on the Issues tab at the top of the page
+ Title the comment with a brief description
+ Add comment
+ Optionally assign a specific person to address this issue 

3. Add a comment in the `VEwhitepaper.md` file by enclosing the comment in the following characters:

    `<!-- Add comment here -->`

<!-- For example, this is a comment here -->

+ This adds a comment just as you would comment a line of R code using the \# symbol.
+ The comment will be placed in the `whitepaper.md` file, but not rendered.

4. Alternatively, clone this repostitory and modify on your computer

+ Open `.md` files in RStudio or other editors
+ Make changes, push commits to master or create pull request as for other code
+ Issues need to be created on GitHub, however

[See this page](https://help.github.com/articles/basic-writing-and-formatting-syntax/) for additional tips on formatting a markdown document. Additional markdown topics are covered [here](https://guides.github.com/features/mastering-markdown/).

## Working with references

References are in [`bibtex`](http://www.bibtex.org/) format, in the `refs` folder. This is an open source format for organizing citations. The software [JabRef](https://github.com/JabRef/jabref/releases/tag/v3.8.2) provides a cross-platform tool for storing and organizing citations in a `.bib` refrence library.
