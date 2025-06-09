# Latex(lualatex)

## 各種サンプル

### 日本語レポート用プリアンブル
```
\PassOptionsToPackage{margin=30truemm}{geometry}
\documentclass[a4paper]{bxjsreport}
%package
\usepackage{amsmath, amssymb}
\usepackage{unicode-math}
\usepackage{mathcomp}
\usepackage{textcomp}
\usepackage{geometry}
\usepackage{graphicx}
\usepackage{float}
\usepackage{rotating}
\usepackage{multirow}
%westernLanguage
\usepackage{fontspec}
\setmainfont[Ligatures={Rare,TeX}]{Times New Roman}
\setsansfont[Ligatures={Rare,TeX}]{Times New Roman}
%japaneseLanguage
\usepackage{luatexja-fontspec}
\setmainjfont[
  BoldFont           = MS-Mincho,
  BoldFeatures       = {FakeBold=2},
  ItalicFont         = MS-Mincho,
  ItalicFeatures     = {FakeSlant=0.33},
  BoldItalicFont     = MS-Mincho,
  BoldItalicFeatures = {FakeBold=2, FakeSlant=0.33}
]{MS-Mincho}
\setsansjfont[
  BoldFont           = MS-Mincho,
  BoldFeatures       = {FakeBold=2},
  ItalicFont         = MS-Mincho,
  ItalicFeatures     = {FakeSlant=0.33},
  BoldItalicFont     = MS-Mincho,
  BoldItalicFeatures = {FakeBold=2, FakeSlant=0.33}
]{MS-Mincho}
%caption
\usepackage{caption}
\usepackage{subcaption}
\captionsetup{labelsep=space}
%cite
\usepackage[super]{cite}
\renewcommand\citeform[1]{[\thechapter-#1]}
\usepackage{chngcntr}
\counterwithin{enumiv}{chapter}
\renewcommand{\bibname}{}
\makeatletter
\renewenvironment{thebibliography}[1]{%
  \begin{list}{[\thechapter-\@biblabelnum]}{%
      \setlength{\leftmargin}{2em}%
      \usecounter{enumiv}%
      \let\p@enumiv\@empty
      \def\@biblabelnum{\arabic{enumiv}}%
    }%
}{%
  \end{list}%
}
\makeatother
%URL
\usepackage{url}
\renewcommand{\UrlFont}{\fontspec{Times New Roman}}
%chapter
\numberwithin{figure}{chapter}
\numberwithin{table}{chapter}
%10.5ptOutput
\makeatletter
\AtBeginDocument{\fontsize{10.5pt}{16pt}\selectfont}
\makeatother
%chapter
\makeatletter
\def\@makechapterhead#1{%
  {\parindent \z@ \raggedright \normalfont
    \Large\bfseries \thechapter\quad #1\par\nobreak\vskip 20pt}} % ←ここでサイズ指定
\def\@makeschapterhead#1{%
  \vspace*{20pt}%
  {\parindent \z@ \raggedright \normalfont
    \Large\bfseries #1\par\nobreak\vskip 20pt}} % ←番号なし章（*付き）
\makeatother
```

### テキスト幅の半分の画像を挿入する
```
\begin{figure}[H]
  \centering
  \vspace{\baselineskip}
  \includegraphics[keepaspectratio, width=0.5\textwidth]{figure/FILENAME}
  \caption{CAPTION}
  \label{fig:LABEL}
  \vspace{\baselineskip}
\end{figure}
```

### 横並びで2つ画像を挿入する
```
\begin{figure}[H]
  \centering
  \vspace{\baselineskip}
  \begin{minipage}[h]{0.45\linewidth}
    \centering
    \includegraphics[keepaspectratio, width=\textwidth]{figure/FILENAME}
    \caption{CAPTION1}
    \label{fig:LABEL1}
  \end{minipage}
  \begin{minipage}[h]{0.45\linewidth}
    \centering
    \includegraphics[keepaspectratio, width=\textwidth]{figure/FILENAME}
    \caption{CAPTION2}
    \label{fig:LABEL2}
  \end{minipage}
  \vspace{\baselineskip}
\end{figure}
```

### 表を挿入する
```
\begin{table}[H]
  \centering
  \vspace{\baselineskip}
  \caption{CAPTION}
  \label{tab:LABEL}
  \begin{tabular}{|c|c|c|} \hline
    a & b & c \\ \hline \hline
    1 & 2 & 3 \\ \hline
    4 & 5 & 6 \\ \hline
  \end{tabular}
  \vspace{\baselineskip}
\end{table}
```

### 横並びで2つ表を挿入する
```
\begin{table}[H]
  \centering
  \vspace{\baselineskip}
  \begin{minipage}[h]{0.45\linewidth}
    \centering
    \caption{CAPTION1}
    \label{tab:LABEL1}
    \begin{tabular}{|c|c|c|} \hline
      a & b & c \\ \hline \hline
      1 & 2 & 3 \\ \hline
      4 & 5 & 6 \\ \hline
    \end{tabular}
  \end{minipage}
  \begin{minipage}[h]{0.45\linewidth}
    \centering
    \caption{CAPTION2}
    \label{tab:LABEL2}
    \begin{tabular}{|c|c|c|} \hline
      d & e & f \\ \hline \hline
      1 & 2 & 3 \\ \hline
      4 & 5 & 6 \\ \hline
    \end{tabular}
  \end{minipage}
  \vspace{\baselineskip}
\end{table}
```

### 参考文献リストを作成する
```
\section{参考文献}
\begin{minipage}{0.95\textwidth}
\begin{thebibliography}{99}
\bibitem{CITEKEY} AUTHOR, "TITLE", \url{URL}, 閲覧日2025-MM-DD
\end{thebibliography}
\end{minipage}
```
citeで文献参照
```
\cite{CITEKEY}
```
