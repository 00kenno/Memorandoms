# Latex(lualatex)

## 各種スニペット

### 日本語レポート用プリアンブル
```json
{
	"preamble": {
		"prefix": "preamble",
		"body": [
			"\\documentclass[fontsize=10.5bp]{jlreq}",
			"\\usepackage{amsmath, amssymb}",
			"\\usepackage{unicode-math}",
			"\\usepackage{mathcomp}",
			"\\usepackage{textcomp}",
			"\\usepackage[margin=30truemm]{geometry}",
			"\\usepackage{bm}",
			"\\usepackage{fontspec}",
			"\\usepackage{luatexja-fontspec}",
			"\\usepackage{graphicx}",
			"\\usepackage{float}",
			"\\usepackage{subcaption}",
			"\\usepackage{multirow}",
			"\\usepackage[super]{cite}",
			"\\renewcommand\\citeform[1]{[#1]}",
			"\\usepackage{url}",
			"\\renewcommand{\\UrlFont}{\\fontspec{Times-New-Roman}}",
			"\\setmainfont[Ligatures={Rare,TeX}]{Times-New-Roman}",
			"\\setsansfont[Ligatures={Rare,TeX}]{Times-New-Roman}",
			"\\setmainjfont[",
    	"\tYokoFeatures       = {JFM=jlreq},",
    	"\tTateFeatures       = {JFM=jlreqv},",
    	"\tBoldFont           = MS-Mincho,",
    	"\tBoldFeatures       = {FakeBold=2},",
    	"\tItalicFont         = MS-Mincho,",
    	"\tItalicFeatures     = {FakeSlant=0.33},",
    	"\tBoldItalicFont     = MS-Mincho,",
    	"\tBoldItalicFeatures = {FakeBold=2, FakeSlant=0.33}",
			"]{MS-Mincho}",
			"\\setsansjfont[",
	    "\tYokoFeatures       = {JFM=jlreq},",
    	"\tTateFeatures       = {JFM=jlreqv},",
    	"\tBoldFont           = MS-Mincho,",
    	"\tBoldFeatures       = {FakeBold=2},",
    	"\tItalicFont         = MS-Mincho,",
    	"\tItalicFeatures     = {FakeSlant=0.33},",
    	"\tBoldItalicFont     = MS-Mincho,",
    	"\tBoldItalicFeatures = {FakeBold=2, FakeSlant=0.33}",
			"]{MS-Mincho}"
		]
	}
}
```

### テキスト幅の半分の画像を挿入する
```json
{
  "image": {
    "prefix": "image",
    "body": [
      "\\begin{figure}[H]",
      "\t\\centering",
      "\t\\vspace{\\baselineskip}",
      "\t\\includegraphics[keepaspectratio, width=0.5\\textwidth]{figure/FILENAME}",
      "\t\\caption{CAPTION}",
      "\t\\label{fig:LABEL}",
      "\t\\vspace{\\baselineskip}",
      "\\end{figure}"
		]
	}
}
```

### 横並びで2つ画像を挿入する
```json
{
	"twoimages": {
		"prefix": "twoimages",
		"body": [
			"\\begin{figure}[H]",
    	"\t\\centering",
      "\t\\vspace{\\baselineskip}",
    	"\t\\begin{minipage}[h]{0.45\\linewidth}",
    	"\t\t\\centering",
      "\t\t\\includegraphics[keepaspectratio, width=\\textwidth]{figure/FILENAME1}",
    	"\t\t\\caption{CAPTION1}",
    	"\t\t\\label{fig:LABEL1}",
    	"\t\\end{minipage}",
    	"\t\\begin{minipage}[h]{0.45\\linewidth}",
    	"\t\t\\centering",
      "\t\t\\includegraphics[keepaspectratio, width=\\textwidth]{figure/FILENAME2}",
    	"\t\t\\caption{CAPTION2}",
    	"\t\t\\label{fig:LABEL2}",
    	"\t\\end{minipage}",
      "\t\\vspace{\\baselineskip}",
			"\\end{figure}"
		]
	}
}
```

### 表を挿入する
```json
{
	"table": {
		"prefix": "table",
		"body": [
		  "\\begin{table}[H]",
      "\t\\centering",
      "\t\\vspace{\\baselineskip}",
      "\t\\caption{CAPTION}",
      "\t\\label{tab:LABEL}",
      "\t\\begin{tabular}{|c|c|c|} \\hline",
      "\t\ta & b & c \\\\\\ \\hline \\hline",
      "\t\t1 & 2 & 3 \\\\\\ \\hline",
      "\t\t4 & 5 & 6 \\\\\\ \\hline",
      "\t\\end{tabular}",
      "\t\\vspace{\\baselineskip}",
      "\\end{table}"
		]
	}
}
```

### 横並びで2つ表を挿入する
```json
{
	"twotables": {
		"prefix": "twotables",
		"body": [
			"\\begin{table}[H]",
    	"\t\\centering",
      "\t\\vspace{\\baselineskip}",
    	"\t\\begin{minipage}[h]{0.45\\linewidth}",
    	"\t\t\\centering",
    	"\t\t\\caption{CAPTION1}",
    	"\t\t\\label{tab:LABEL1}",
			"\t\t\\begin{tabular}{|c|c|c|} \\hline",
      "\t\t\ta & b & c \\\\\\ \\hline \\hline",
      "\t\t\t1 & 2 & 3 \\\\\\ \\hline",
      "\t\t\t4 & 5 & 6 \\\\\\ \\hline",
			"\t\t\\end{tabular}",
    	"\t\\end{minipage}",
    	"\t\\begin{minipage}[h]{0.45\\linewidth}",
    	"\t\t\\centering",
    	"\t\t\\caption{CAPTION2}",
    	"\t\t\\label{tab:LABEL2}",
			"\t\t\\begin{tabular}{|c|c|c|} \\hline",
      "\t\t\td & e & f \\\\\\ \\hline \\hline",
      "\t\t\t1 & 2 & 3 \\\\\\ \\hline",
      "\t\t\t4 & 5 & 6 \\\\\\ \\hline",
			"\t\t\\end{tabular}",
    	"\t\\end{minipage}",
      "\t\\vspace{\\baselineskip}",
			"\\end{table}"
		]
	}
}
```

### 参考文献リストを作成する
```json
{
  "bibliography": {
    "prefix": "bibliography",
    "body": [
			"\\section{参考文献}",
			"\\vspace{-3\\baselineskip}",
			"\\renewcommand{\\refname}{}",
			"\\begin{thebibliography}{99}",
  		"\\bibitem{CITEKEY} AUTHOR, \"TITLE\", \\url{URL}, 閲覧日2025-MM-DD",
      "\\end{thebibliography}"
		]
	}
}
```
citeで文献参照
```
\cite{CITEKEY}
```
