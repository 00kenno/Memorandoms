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
