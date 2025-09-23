# A Fast Guide on Writing LaTeX with LaTeX Workshop in VS Code

## Series - Editors

A Fast Guide on Writing LaTeX with LaTeX Workshop in VS Code
There are dozens of TeX editors so far, such as Texpad and WinEdt.

## Step 1. Download & Install TeX Live

Mac users: download MacTeX.pkg [here](https://www.tug.org/mactex/mactex-download.html).

Here are some references for the installation:

(Installing MacTeX)[https://www.tug.org/mactex/mactex-download.html]

## Step 2. Download & Install Visual Studio Code

You can download it [here](https://code.visualstudio.com/). The installation is easy.

# Step 3. Install & Configure LaTeX Workshop

install the extension LaTeX Workshop.

Shift + Cmd + P (macOS) to show all commands. Then type Open User Settings JSON and open the first item.

open-jsonopen-json
Now copy and paste the following two snippets into your json file (inside the brackets {} of your file).

```json
"latex-workshop.latex.tools": [
 {
  "name": "latexmk",
  "command": "latexmk",
  "args": [
   "-synctex=1",
   "-interaction=nonstopmode",
   "-file-line-error",
   "-pdf",
   "-outdir=%OUTDIR%",
   "%DOC%"
  ],
  "env": {}
 },
 {
  "name": "xelatex",
  "command": "xelatex",
  "args": [
   "-synctex=1",
   "-interaction=nonstopmode",
   "-file-line-error",
   "%DOC%"
  ],
  "env": {}
 },
 {
  "name": "pdflatex",
  "command": "pdflatex",
  "args": [
   "-synctex=1",
   "-interaction=nonstopmode",
   "-file-line-error",
   "%DOC%"
  ],
  "env": {}
 },
 {
  "name": "bibtex",
  "command": "bibtex",
  "args": [
   "%DOCFILE%"
  ],
  "env": {}
 }
],
```

```json
"latex-workshop.latex.recipes": [
 {
  "name": "pdfLaTeX",
  "tools": [
   "pdflatex"
  ]
 },
 {
  "name": "latexmk 🔃",
  "tools": [
   "latexmk"
  ]
 },
 {
  "name": "xelatex",
  "tools": [
   "xelatex"
  ]
 },
 {
  "name": "pdflatex ➞ bibtex ➞ pdflatex`×2",
  "tools": [
   "pdflatex",
   "bibtex",
   "pdflatex",
   "pdflatex"
  ]
 },
 {
 "name": "xelatex ➞ bibtex ➞ xelatex`×2",
 "tools": [
   "xelatex",
   "bibtex",
   "xelatex",
   "xelatex"
  ]
 }
]
```

## Step 4. Write & Compile

Now you may open a tex file or create a new one. If you want to compile the file, press Ctrl + Alt + B (Windows) or option + Cmd + B (macOS). Moreover, you may choose another recipes from the sidebar. There is a button in the right top corner to preview PDF file.

tex-recipes
