# Snippets_in_vim

1. Install texlive for working of latex in vim.

```
   sudo apt update

   sudo apt install texlive
```
2. Install vim
```
    sudo apt install vim
```
3. Install zathura
```
    sudo apt install zathura
```
4. Install :PlugInstall for Installing plugins to make snippets work
```
      curl -fLo ~/.vim/autoload/plug.vim --create-dirs \

      https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
5. Now go to vimrc file which is a configuration file for the vim. Press i. Then write:

```
    call plug#begin('~/.vim/plugged')
    Plug 'lervag/vimtex'
    Plug 'sirver/ultisnips'
    Plug 'honza/vim-snippets'
    call plug#end()
```
```
    let g:UltiSnipsExpandTrigger = '<c-s>'
    let g:UltiSnipsJumpForwardTrigger = '<c-j>'
    let g:UltiSnipsJumpBackwardTrigger = '<c-k>'
    let g:UltiSnipsListSnippets='<c-x><c-s>'
    let g:UltiSnipsRemoveDuplicates=1
    let g:tex_flavor='latex'
    let g:vimtex_view_method='zathura'
    let g:vimtex_quickfix_mode=0
    set conceallevel=1
    let g:tex_conceal='abdmg'

```

Then press esc key and write :wq, then enter.

6. Then we need to install YCM which means YouCompleteMe:
```
    apt install build-essential cmake vim-nox python3-dev

    sudo mkdir -p /etc/apt/keyrings

    curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg

    echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_current.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list

    apt install mono-complete golang nodejs openjdk-17-jdk openjdk-17-jre npm
```

7. Open Vim Editor:
```
    vim
```
Then write
```
    :UltiSnipsEdit
```
Here you will edit or add snippets you want, maybe some default snippets will be present there.

8. Write a snippet for example:
```
    snippet sign "Signature"
    Yours sincerely,

    Gilles Castel
    endsnippet
```
Then press esc and write
```
    :wq
```
Then again go to vim and press i and write sign and press ctrl+s. You will find the rest has been written by itself.

9. Then to convert a file of vim into pdf, remember the latex file have extension of .tex, now open vim, press i and write:

```
   \documentclass{article}
   \usepackage{amsmath} % For better mathematical formatting

   \begin{document}

   Here is the integral:

   \[
   \int x \, dx
   \]

   \end{document}
```
Press esc and write:
```
   :wq filename.tex
```
Then to convert this file into pdf by writing:
```
   pdflatex filename.tex
```
Then to view it in pdf viewer named zathura write:
```
zathura filename.pdf
```
REMEMBER TO CHANGE THE FILE EXTENSION ON WRITING ```zathura``` AS .pdf NOT .tex   

##Test yourself!

Use this code in vim and convert it into pdf and open it through pdf viewer, see it through zathura and share your experience!

```
\documentclass{article}
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}

\begin{document}

\title{A Comprehensive Overview of Mathematical Concepts}
\author{Your Name}
\date{\today}
\maketitle

\section{Introduction}
Mathematics is a vast field that encompasses various areas of study. In this document, we will explore some fundamental mathematical concepts and their applications.

\section{Algebra}
Algebra involves the study of symbols and the rules for manipulating these symbols. 

\subsection{Basic Algebraic Operations}
Consider the following algebraic expression:
\begin{equation}
    a^2 + b^2 = c^2
\end{equation}
This is the Pythagorean theorem, which is a fundamental relation in Euclidean geometry.

\subsection{Polynomial Functions}
A polynomial function is an expression of the form:
\begin{equation}
    P(x) = a_n x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0
\end{equation}
where \(a_i\) are coefficients and \(n\) is a non-negative integer.

\section{Calculus}
Calculus is concerned with change and motion. It has two main branches: differential calculus and integral calculus.

\subsection{Differentiation}
The derivative of a function \(f(x)\) measures how \(f(x)\) changes as \(x\) changes. The derivative is denoted by \(f'(x)\) or \(\frac{df}{dx}\):
\begin{equation}
    \frac{d}{dx} \left( x^n \right) = n x^{n-1}
\end{equation}

\subsection{Integration}
The integral of a function \(f(x)\) represents the area under the curve of \(f(x)\):
\begin{equation}
    \int_a^b f(x) \, dx
\end{equation}

\section{Linear Algebra}
Linear algebra deals with vector spaces and linear mappings between these spaces.

\subsection{Vectors}
A vector in \(\mathbb{R}^n\) is represented as:
\begin{equation}
    \mathbf{v} = \begin{pmatrix}
        v_1 \\
        v_2 \\
        \vdots \\
        v_n
    \end{pmatrix}
\end{equation}

\subsection{Matrices}
A matrix is a rectangular array of numbers arranged in rows and columns:
\begin{equation}
    A = \begin{pmatrix}
        a_{11} & a_{12} \\
        a_{21} & a_{22}
    \end{pmatrix}
\end{equation}

\section{Conclusion}
Mathematics provides a framework for understanding and solving complex problems. This document has touched on some of the core areas of mathematics.

\end{document}
```
