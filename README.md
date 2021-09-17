# R_Markdown
Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents.

# Purpose
R Markdown files are the source code for rich, reproducible documents.

# Definitions
You can transform an R Markdown file in two ways.

1. **knit** - You can knit the file. The rmarkdown package will call the knitr package. knitr will run each chunk of R code in the document and append the results of the code to the document next to the code chunk. This workflow saves time and facilitates reproducible reports.

  - Consider how authors typically include graphs (or tables, or numbers) in a report. The author makes the graph, saves it as a file, and then copy and pastes it into the final report. This process relies on manual labor. If the data changes, the author must repeat the entire process to update the graph.

  - In the R Markdown paradigm, each report contains the code it needs to make its own graphs, tables, numbers, etc. The author can automatically update the report by re-knitting.

2. **convert** - You can convert the file. The rmarkdown package will use the pandoc program to transform the file into a new format. For example, you can convert your .Rmd file into an HTML, PDF, or Microsoft Word file. You can even turn the file into an HTML5 or PDF slideshow. rmarkdown will preserve the text, code results, and formatting contained in your original .Rmd file.

  - Conversion lets you do your original work in markdown, which is very easy to use. You can include R code to knit, and you can share your document in a variety of formats.

  - Consider how authors typically include graphs (or tables, or numbers) in a report. The author makes the graph, saves it as a file, and then copy and pastes it into the final report. This process relies on manual labor. If the data changes, the author must repeat the entire process to update the graph.

  - In the R Markdown paradigm, each report contains the code it needs to make its own graphs, tables, numbers, etc. The author can automatically update the report by re-knitting.


# Background
R Markdown files are designed to be used with the rmarkdown package. rmarkdown comes installed with the RStudio IDE, but you can acquire your own copy of rmarkdown from CRAN with the command

install.packages("rmarkdown")

### Overview
  - Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents
  - Markdown documents provide quick, reproducible reporting from R

### Basic Process
  - Write the document in markdown and embed executable R code chunks with the knitr syntax
  - Update the document at any time by re-knitting the code chunks
  - Convert the document into several common formats


# Procedure



# References
- https://rmarkdown.rstudio.com/articles_intro.html
- https://cran.r-project.org/web/packages/rmarkdown/vignettes/rmarkdown.html
