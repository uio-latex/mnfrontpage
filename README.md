# mnfrontpage
The LaTeX package `mnfrontpage` is used to generate front pages
for documents with affiliation to the Faculty of Mathematics and Natural Sciences at the University of Oslo.
The background images are taken from the university's [design manual](http://www.uio.no/om/designmanual/nedlastinger/kompendier/mn/).

## Commands
The package collects information from the commands 
* `\author{...}`,
* `\title{...}`,
* `\subtitle{...}`.
* `\kind{...}`,

and the front page itself is created with the command `\mnfrontpage`. 

Usage of `\subtitle{...}` and `\kind{...}` is optional.
The latter command defines text to go under the author's name and can be anything.
As the name suggest,
this can be used to state what kind of document it is,
such as "Technical report".
If the option `master` is given,
this line is automatically set to "Master's Thesis, Semester Year" specified in the correct language,
but calling `\kind{...}` will overwrite it.

## Title
If there is not enough room for your title,
try one of the options `LongTitle` or `ExtraLongTitle`.

## Department
By default,
the department is set to the Faculty of Mathematics and Natural Sciences.
This can be changed with one of the options
* `AST`, *Institute of Theoretical Astrophysics*,
* `FRM`, *School of Pharmacy*,
* `FYS`, *Department of Physics*,
* `GEO`, *Department of Geosciences*,
* `IBV`, *Department of Biosciences*,
* `IFI`, *Department of Informatics*,
* `KJM`, *Department of Chemistry*,
* `MAT`, *Department of Mathematics*.

Changing the department will change the logo.
Also,
the background image is set to the background used in the university's design manual.
The background can be changed independently of the logo,
as explained in the next section.

## Background image
There are ten available background images.
By default,
the image is chosen to correspond with the department as dictated by the university's design manual,
but any combination of logo and background is possible.
To select a specific image,
enter one of the options `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9` or `10`.

## Screen or print version
Unless specified,
`mnfrontpage` will use an everyday, low-resolution version of the background image.
Before sending the document to print,
you should enter the option `print` for the original, higher-resolution edition of the image.
If the document is to be printed at the University Print Centre
– or bound similarly –
use the option `bound` instead.
This will shift Apollon, the logo and title to the right
to compensate for the cardboard rim added at the University Print Centre.

## Master's thesis
If you are using `mnfrontpage` for your master's thesis,
use the option `master` to write "Master's Thesis, Semester Year"
in the selected language below your name.
This line can be overwritten using the command `\kind{}`.

## Language
Language is preferably given as a document class option,
but can be passed as a package option.
The following language options are recognised:
`american`, `english`, `UKenglish`, `USenglish`, `norsk` and `nynorsk`.
If none of these are given,
`english` is chosen by default.

Choice of language will affect the logo,
and if the `master` option is used,
it will also influence the line "Master's Thesis, Semester Year".

## Blank page
Automatically,
`mnfrontpage` creates a blank page following the title page.
This can be turned off using the option `OnlyFrontpage`.
If you are using the document class `memoir`,
ignore the previous sentence.
In that case,
all blank pages are controlled entirely by the class settings. 

## Date
If necessary,
the date assumed by the `master` option can be changed
using the TeX primitives `\month = mm` and `\year = yyyy`
before calling `\usepackage{mnfrontpage}`.

## Compiler
If compiling with `xelatex`,
the grey and white banners will not be transparent.
Both `pdflatex` and `lualatex` work.

## Example
```latex
\documentclass[a4paper]{memoir}

\usepackage[MAT, 1]{mnfrontpage}

\title{Mathematical Analysis}

\author{Tom Lindstr{\o}m\hfill\the\year}

\begin{document}
    \mnfrontpage
\end{document}
```

![Example image](https://i.imgur.com/4IS3LUt.png)
