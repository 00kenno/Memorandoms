# Latex(lualatex)

## 各種サンプル

### 日本語レポート用プリアンブル
```
\documentclass[fontsize=10.5bp]{jlreq}
\usepackage{amsmath, amssymb}
\usepackage{unicode-math}
\usepackage{mathcomp}
\usepackage{textcomp}
\usepackage[margin=30truemm]{geometry}
\usepackage{bm}
\usepackage{fontspec}
\usepackage{luatexja-fontspec}
\usepackage{graphicx}
\usepackage{float}
\usepackage{subcaption}
\usepackage{multirow}
\usepackage[super]{cite}
\renewcommand\citeform[1]{[#1]}
\usepackage{url}
\renewcommand{\UrlFont}{\fontspec{Times-New-Roman}}
\setmainfont[Ligatures={Rare,TeX}]{Times-New-Roman}
\setsansfont[Ligatures={Rare,TeX}]{Times-New-Roman}
\setmainjfont[
  YokoFeatures       = {JFM=jlreq},
  TateFeatures       = {JFM=jlreqv},
  BoldFont           = MS-Mincho,
  BoldFeatures       = {FakeBold=2},
  ItalicFont         = MS-Mincho,
  ItalicFeatures     = {FakeSlant=0.33},
  BoldItalicFont     = MS-Mincho,
  BoldItalicFeatures = {FakeBold=2, FakeSlant=0.33}
]{MS-Mincho}
\setsansjfont[
  YokoFeatures       = {JFM=jlreq},
  TateFeatures       = {JFM=jlreqv},
  BoldFont           = MS-Mincho,
  BoldFeatures       = {FakeBold=2},
  ItalicFont         = MS-Mincho,
  ItalicFeatures     = {FakeSlant=0.33},
  BoldItalicFont     = MS-Mincho,
  BoldItalicFeatures = {FakeBold=2, FakeSlant=0.33}
]{MS-Mincho}
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
\vspace{-3\baselineskip}
\renewcommand{\refname}{}
\begin{thebibliography}{99}
\bibitem{CITEKEY} AUTHOR, "TITLE", \url{URL}, 閲覧日2025-MM-DD
\end{thebibliography}
```
citeで文献参照
```
\cite{CITEKEY}
```
