# Intro to LaTeX
Adapted by [Garret Christensen](http://www.ocf.berkeley.edu/~garret) from [materials](https://github.com/thehackerwithin/berkeley/tree/master/LaTeX) by Lawrence Lewis, Katy Huff, and Rachel Slaybaugh.

## 1. What is in this Directory?
There's a document, two presentations ('presentation'--an intro presentation and 'bodies'--some details on floats) and a poster (very alpha), which is meant to show the basics of LaTeX.


<!--## What is Markup?

### HTML

HTML is just hypertext markup language. It provides a plain text way to
describe objects and data that are encountered in the world wide web. Things
like urls, text rendering in webpages, etc. are all easy to describe in HTML.

### XML

XML is the extensible markup language. It generalizes where others specify. In
the way that all reductionist things fail to get the specifics right, XML is
great for general tasks in programming (input files, etc.), but not great for
writing documents, where the needs are very specific.

### MarkDown? RestructuredText? Where does it end?

There are a lot of markup languages. They all do different things. Restructured
text is the standard in the world of python documentation. Markdown is the
standard on github. Pick your poison.
-->
## 2. What is LaTeX and why would I want to use it?
LaTeX is a markup language for typesetting. It's not a WYSIWYG like most word processors (i.e MS Word). To some extent, you worry about the content and let the engine handle the layout. Really: it's like programming--if you put in the effort to get up the learning curve, you save time in the end by automating your document creation.

I use it because:
 1. LaTeX handles citations for you.
 2. LaTeX handles numbering, labels/references, table of contents, etc. for you.
 3. LaTeX does beautiful math.
 4. LaTeX is beautiful all around.
 5. LaTeX doesn't bog down with long docs like MS Word.


I still find it frustrating because:
  1. It's got a learning curve.
  2. Error messages feel cryptic. (But less cryptic than Word just doing something inexplicable. https://twitter.com/gossipgriII/status/713425874167537664)
  3. I haven't mastered collaborative editing yet, but solutions exist.

## 3. How do I install LaTeX?
[For some reason](http://tex.stackexchange.com/questions/974/why-is-the-mactex-distribution-so-large-is-there-anything-smaller-for-os-x), LaTeX takes up over a gigabyte, so installing may take a few minutes.

### Linux

Everything in linux is simple.

    sudo apt-get install texlive

Then you probably want a front end like [TeXWorks](https://www.tug.org/texworks/), which is available in the Software Center for Ubuntu users, or here more generally. I think the Mac and Windows distributions come with this already.

### OSX

You should use [MacTeX][mactex]. You can do this with macports or homebrew by downloading the whole shabang from
the website.

### Windows

Install [MikTeX](http://miktex.org/).

## 4. How do I write LaTeX?

http://tobi.oetiker.ch/lshort/lshort.pdf

### LyX

[LyX](https://www.lyx.org/) is a WYSIWYG editor for LaTeX. I used to use it until I needed to format my dissertation, and then I switched to  straight LaTeX. It has change tracking, however, which in my experience is crucial for collaborative paper writing.

### TeXShop/TeXWorks

[TeXShop](http://pages.uoregon.edu/koch/texshop/) (Mac only) and [TeXWorks](https://www.tug.org/texworks/) are simple front-ends for LaTeX that let you write the markup and see the rendering side by side.

### Text Editors

Some folks will find the text editor option the most extensible and glorious. More power to them, but I am not one of those folks. (You'd just type pdflatex *filename.tex* in the command line to compile.)

## 5. How do I pronounce LaTeX?

Check it out, the last letter is the Greek letter $$\Chi$$. So, it definitely has to end in a K sound. But, is it Lay or Lah? The developers say it's up to you.

## 6. Stuff we'll try to cover
  1. Make a basic doc
  2. documentclass (article, beamer, exam, letter, book, *others*)
  3. preamble
  4. include packages
  5. sections, subsections
  6. labels, refs
  7. itemize, enumerate
  8. math, equations
  8. include, includegraphics, input
  9. bibliography
  10. floats
    1. table
    2. figure


## 7. What are the Parts of a Document?

LaTeX documents have numerous parts.

### The Preamble

In the preamble, there is a basic set of information that must be included in
order to define the document. The real minimum set is just the "documentclass"
parameter. Options include "article," "book," and "letter." Options concerning
the paper format and the font can be specified in the square brackets while the
documentclass type should be listed in the  

    \documentclass[11pt]{article}

inclusion of any packages that you rely on. Standard packages include
"amsmath," "amsfonts," "amssymb," and graphicx.

    \usepackage{amsmath}
    \usepackage{amssymb}

If you are expecting a title to appear, parameters such as author and title
should be filled in.




### begin and end

You must begin and end the document.

    \documentclass[11pt]{article}

    \begin{document}

    <stuff>

    \end{document}


Now, that's it. To create a beautiful pdf, you can place this text in a file
called doc.tex, and type "pdflatex doc.tex". You can also use the "latex" command to make DVI output, but I don't know what that is or why you'd want to.

### The Title Elements

There are elements that help to define the title elements.


    \documentclass[11pt]{article}
    \author{The Hacker Within}
    \title{Our New Document}

    \begin{document}

    <stuff>

    \end{document}


Those variables are used by the maketitle command, which must be executed
within the document boundaries.


    \documentclass[11pt]{article}
    \author{The Hacker Within}
    \title{Our New Document}

    \begin{document}
    \maketitle

    \end{document}



### Books, Chapters, Sections, Subsections, Subsubsections, and Paragraphs

These are environments that define the hierarchy of your document.


### Include and input

Rather than keep everything in one big file, you can include and input other
latex files into a master. That acknowledgements section that you use in every
paper? Keep it in its own file.



[texSE]: http://tex.stackexchange.com/questions/41808/how-do-i-install-tex-latex-on-windows-7 "TeX Stack Exchange"
[mactex]: https://tug.org/mactex/ "mactex"
