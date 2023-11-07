## Changed files
The following files are changed in for my style modification of moderncv:
- moderncvbodi.sty
- moderncvheadii.sty
- moderncvcolorblue.sty
- moderncv.cls

They are marked as "author==LLdaniel" to easily find them.

## Why changes?
I fell in love with moderncv but wished slightly different look. Therefore I added them to match my needs.

## Features:
- heading bar is symmetric in moderncvbodi.sty
```
% original cvitem:
  %\cvitem[0ex]{\strut\raggedleft\raisebox{\baseletterheight}{\color{color1}\rule{\hintscolumnwidth}{0.95ex}}}{\strut\sectionstyle{#2}}%
  \cvitem[0ex]{\strut\raggedleft\raisebox{\baseletterheight}{\color{color1}\rule{\hintscolumnwidth}{0.95ex}}}{\strut\sectionstyle{#2}\sectionendingbar}% added section heading bar author=LLdaniel


% commands for section ending bar: author=LLdaniel
\newlength{\barheight}
\setlength{\barheight}{0.95ex}
\newlength{\missinglength}
\newcommand{\sectionendingbar}{\hspace{\separatorcolumnwidth}\color{color1}\rule[\baseletterheight]{\maincolumnwidth-\separatorcolumnwidth-\missinglength}{\barheight}}
\newcommand{\measuresection}[1]{\settowidth{\missinglength}{\sectionstyle{#1}}} % measure the current section length
```
- \today date in for a german format in moderncv.cls
```
% classical \today definition
\def\today{\ifcase\month\or
  January\or February\or March\or April\or May\or June\or
  July\or August\or September\or October\or November\or December\fi
  \space\number\day, \number\year}

% german \today definition author=LLdaniel
\def\today{\number\day.\space\ifcase\month\or
  Januar\or Februar\or M\"{a}rz\or April\or Mai\or Juni\or
  Juli\or August\or September\or Oktober\or November\or Dezember\fi
  \space\number\year}
```
- different color: `+\definecolor{color1}{rgb}{0.0,0.18,0.39}% dark blue` in moderncvcolorblue.sty