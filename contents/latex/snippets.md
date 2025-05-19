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
      "\\usepackage[margin=30truemm]{geometry}",
      "\\usepackage{bm}",
      "\\usepackage{fontspec}",
      "\\usepackage{luatexja-fontspec}",
      "\\usepackage{graphicx}",
      "\\usepackage{subcaption}",
      "\\usepackage{hyperref}",
      "\\hypersetup{",
      "\tpdfborder={0 0 0}",
      "}",
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
      "]{MS-Mincho}",
      "\\renewcommand{\\UrlFont}{\\fontspec{Times-New-Roman}}"
    ]
  }
}
```

### テキスト幅の半分の画像を挿入する
```json
{
  "oneimage": {
    "prefix": "oneimage",
    "body": [
      "\\begin{figure}[htbp]",
      "\t\\centering",
      "\t\\includegraphics[keepaspectratio, width=0.5\\textwidth]{figure/image0001.png}",
      "\t\\caption{加工課題1}",
      "\t\\label{fig:kadai1_origin}",
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
      "\\begin{figure}[htbp]",
      "\t\\centering",
      "\t\\begin{minipage}[h]{0.45\\linewidth}",
      "\t\t\\includegraphics[keepaspectratio, width=\\textwidth]{figure/image0001.png}",
      "\t\\end{minipage}",
      "\t\\begin{minipage}[h]{0.45\\linewidth}",
      "\t\t\\includegraphics[keepaspectratio, width=\\textwidth]{figure/image0002.png}",
      "\t\\end{minipage}",
      "\t\\caption{加工課題2(3D-CAD図)}",
      "\t\\label{fig:kadai2_3d-cad}",
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
      "\\begin{table}",,
      "\t\\centering",
      "\t\\caption{各種工作機械の分類}",
      "\t\\vspace{0.3\\baselineskip}",
      "\t\\begin{tabular}{|c||cc|} \\hline",
      "\t\t種類 & NC装置 & ATC \\\\\\ \\hline",
      "\t\t汎用旋盤 & ✕ & ✕ \\\\\\",
      "\t\t汎用フライス盤 & ✕ & ✕ \\\\\\",
      "\t\tNC旋盤 & ○ & ✕ \\\\\\",
      "\t\tNCフライス盤 & ○ & ✕ \\\\\\",
      "\t\tターニングセンタ & ○ & ○ \\\\\\",
      "\t\tマシニングセンタ & ○ & ○ \\\\\\ \\hline",
      "\t\\end{tabular}",
      "\\end{table}"
    ]
  }
}
```