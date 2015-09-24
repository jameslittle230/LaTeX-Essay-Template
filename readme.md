#LaTeX Essay Template

Ever get that feeling like you want to write an essay, but you don't have the proper LaTeX template to do so? No? Just me?

This repository is a template for writing humanities papers in MLA format. It provides a set of reasonable but lightweight defaults in terms of packages and styling that complies (almost perfectly I think) to the MLA standard that nearly every school uses. This is for humanities papers only, meaning there's nothing here for math or diagrams or code or anything else. That goes in a different repository.

## Download

If you're starting a new project, you're not going to want to clone the repository and start writing there. This turns your LaTeX-Essay-Template repository into your essay repository and then it just gets messy. Instead, clone this repository (if you haven't already) and copy `essay.tex`, `main.tex`, and `preamble.tex` into a new folder. That new folder then becomes a completely independent Git repository. Don't make this any harder than it has to be.

## LaTeX Packages

This template uses a couple of packages that might not come standard with your computer. (I'm using BasicTeX, a stripped down version of MacTeX, and so I had to install a few packages on my own.) Your download of LaTeX should come with `tlmgr`, the TeX Live package manager. (If it didn't, I'm not sure how to help.) Use this to install the packages `fontspec`, `microtype`, `setspace`, and `fancyhdr`. Or copy and paste this at your terminal if you're lazy:

```
$ tlmgr install fontspec microtype setspace fancyhdr
```

## Usage

Since this uses `fontspec` to get Times New Roman (or in my case, FreeSerif since I like its ligatures better) as the main font, this template needs to be compiled with `XeLaTeX` or `LuaLaTeX`.

Write things in `essay.tex`. That file just has to include your essay, no extraneous code. I recommend putting custom commands in `main.tex` just to get them out of the way. When you want to compile the document, compile `main.tex`.

## Extra Credit

*Note: If you're not on a Mac, I can't make any promises about what's about to go down.*

I like to set it up so that it compiles `main.tex` whenever I save any `.tex` file in the folder. I do that with a terminal program called `entr` which can be installed with Homebrew (`brew install entr`). After you `cd` into the folder in which the essay is stored, you can run the command

```
$ ls *.tex | entr lualatex main.tex
```

This will compile the document (using LuaLaTeX — use XeLaTeX if you want to be different) and then wait until there's a change in any `.tex` file, at which point it will compile it again.

I also like to use the PDF viewer Skim, which can be set to auto-update when the PDF file changes after it's compiled, which Preview doesn't like doing if it's not the program in focus (which it rarely is when you're writing in a text editor).
