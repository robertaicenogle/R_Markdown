# R_Markdown
Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents.

# Purpose
R Markdown files are the source code for rich, reproducible documents.


# Background
R Markdown files are designed to be used with the rmarkdown package. rmarkdown comes installed with the RStudio IDE, but you can acquire your own copy of rmarkdown from CRAN with the command { install.packages("rmarkdown") }


### Overview
  - Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents
  - Markdown documents provide quick, reproducible reporting from R


### Basic Process
  - Write the document in markdown and embed executable R code chunks with the knitr syntax
  - Update the document at any time by re-knitting the code chunks
  - Convert the document into several common formats


# Definitions
You can transform an R Markdown file in two ways:

1. **knit** - You can knit the file. The rmarkdown package will call the knitr package. knitr will run each chunk of R code in the document and append the results of the code to the document next to the code chunk. This workflow saves time and facilitates reproducible reports.

    - Consider how authors typically include graphs (or tables, or numbers) in a report. The author makes the graph, saves it as a file, and then copy and pastes it into the final report. This process relies on manual labor. If the data changes, the author must repeat the entire process to update the graph.

    - In the R Markdown paradigm, each report contains the code it needs to make its own graphs, tables, numbers, etc. The author can automatically update the report by re-knitting.


2. **convert** - You can convert the file. The rmarkdown package will use the pandoc program to transform the file into a new format. For example, you can convert your .Rmd file into an HTML, PDF, or Microsoft Word file. You can even turn the file into an HTML5 or PDF slideshow. rmarkdown will preserve the text, code results, and formatting contained in your original .Rmd file.

    - Conversion lets you do your original work in markdown, which is very easy to use. You can include R code to knit, and you can share your document in a variety of formats.

    - Consider how authors typically include graphs (or tables, or numbers) in a report. The author makes the graph, saves it as a file, and then copy and pastes it into the final report. This process relies on manual labor. If the data changes, the author must repeat the entire process to update the graph.

    - In the R Markdown paradigm, each report contains the code it needs to make its own graphs, tables, numbers, etc. The author can automatically update the report by re-knitting.

In practice, authors almost always knit and convert their documents at the same time. In this article, I will use the term render to refer to the two step process of knitting and converting an R Markdown file.


# Procedure

### Getting Started
To create an R Markdown report, open a plain text file and save it with the extension .Rmd. You can open a plain text file in your scripts editor by clicking File > New File > Text File in the RStudio toolbar.

![](pic_1.PNG)

Be sure to save the file with the extension .Rmd. The RStudio IDE enables several helpful buttons when you save the file with the .Rmd extension. You can save your file by clicking File > Save in the RStudio toolbar.

![](pic_2.PNG)

R Markdown reports rely on three frameworks

  1. markdown for formatted text
  2. knitr for embedded R code
  3. YAML for render parameters

The sections below describe each framework.


## Markdown for formatted text
.Rmd files are meant to contain text written in markdown. Markdown is a set of conventions for formatting plain text. You can use markdown to indicate

- bold and italic text
- lists
- headers (e.g., section titles)
- hyperlinks
- and much more

The conventions of markdown are very unobtrusive, which make Markdown files easy to read. The file below uses several of the most useful markdown conventions.

![](pic_1.PNG)

# Say Hello to markdown

Markdown is an **easy to use** format for writing reports. It resembles what you naturally write every time you compose an email. In fact, you may have already used markdown *without realizing it*. These websites all rely on markdown formatting

* [Github](www.github.com)
* [StackOverflow](www.stackoverflow.com)
* [Reddit](www.reddit.com)

The file demonstrates how to use markdown to indicate:

  **1.** headers - Place one or more hashtags at the start of a line that will be a header (or sub-header). For example, # Say Hello to markdown. A single hashtag creates a first level header. Two hashtags, ##, creates a second level header, and so on.

  **2.** italicized and bold text - Surround italicized text with asterisks, like this *without realizing it*. Surround bold text with two asterisks, like this **easy to use**.

  **3.** lists - Group lines into bullet points that begin with asterisks. Leave a blank line before the first bullet, like this
  
NEED PICTURE
![](pic_1.PNG)

  **4.** hyperlinks - Surround links with brackets, and then provide the link target in parentheses, like this [Github](www.github.com).

You can learn about more of markdown’s conventions in the Markdown Quick Reference guide, which comes with the RStudio IDE.

To access the guide, open a .md or .Rmd file in RStudio. Then click the question mark that appears at the top of the scripts pane. Next, select “Markdown Quick Reference”. RStudio will open the Markdown Quick Reference guide in the Help pane.

NEED PICTURE
![](pic_1.PNG)


## Rendering
To transform your markdown file into an HTML, PDF, or Word document, click the “Knit” icon that appears above your file in the scripts editor. A drop down menu will let you select the type of output that you want.

NEED PICTURE
![](pic_1.PNG)


When you click the button, rmarkdown will duplicate your text in the new file format. rmarkdown will use the formatting instructions that you provided with markdown syntax.

Once the file is rendered, RStudio will show you a preview of the new output and save the output file in your working directory.

Here is how the markdown script above would look in each output format.

HTML
NEED PICTURE
![](pic_1.PNG)


PDF
NEED PICTURE
![](pic_1.PNG)

MS WORD
NEED PICTURE
![](pic_1.PNG)


## knitr for Embedded R Code
The knitr package extends the basic markdown syntax to include chunks of executable R code.

When you render the report, knitr will run the code and add the results to the output file. You can have the output display just the code, just the results, or both.

To embed a chunk of R code into your report, surround the code with two lines that each contain three backticks. After the first set of backticks, include {r}, which alerts knitr that you have included a chunk of R code. The result will look like this

NEED PICTURE
![](pic_1.PNG)

When you render your document, knitr will run the code and append the results to the code chunk. knitr will provide formatting and syntax highlighting to both the code and its results (where appropriate).

NEED PICTURE
![](pic_1.PNG)

As a result, the markdown snippet above will look like this when rendered (to HTML).

NEED PICTURE
![](pic_1.PNG)

To omit the results from your final report (and not run the code) add the argument eval = FALSE inside the brackets and after r. This will place a copy of your code into the report.

NEED PICTURE
![](pic_1.PNG)

To omit the code from the final report (while including the results) add the argument echo = FALSE. This will place a copy of the results into your report.

NEED PICTURE
![](pic_1.PNG)

echo = FALSE is very handy for adding plots to a report, since you usually do not want to see the code that generates the plot.

NEED PICTURE
![](pic_1.PNG)

echo and eval are not the only arguments that you can use to customize code chunks. You can learn more about formatting the output of code chunks at the rmarkdown and knitr websites.


## Inline Code
To embed R code in a line of text, surround the code with a pair of backticks and the letter r, like this.

Two plus two equals 4.

knitr will replace the inline code with its result in your final document (inline code is always replaced by its result). The result will appear as if it were part of the original text. For example, the snippet above will appear like this:

NEED PICTURE
![](pic_1.PNG)


## YAML for render parameters
You can use a YAML header to control how rmarkdown renders your .Rmd file. A YAML header is a section of key: value pairs surrounded by --- marks, like below

NEED PICTURE
![](pic_1.PNG)

The output: value determines what type of output to convert the file into when you call rmarkdown::render(). Note: you do not need to specify output: if you render your file with the RStudio IDE knit button.

output: recognizes the following values:

  - html_document, which will create HTML output (default)
  - pdf_document, which will create PDF output
  - word_document, which will create Word output

If you use the RStudio IDE knit button to render your file, the selection you make in the gui will override the output: setting.


## Slideshows
You can also use the output: value to render your document as a slideshow.

  - output: ioslides_presentation will create an ioslides (HTML5) slideshow
  - output: beamer_presentation will create a beamer (PDF) slideshow

Note: The knit button in the RStudio IDE will update to show slideshow options when you include one of the above output values and save your .Rmd file.

rmarkdown will convert your document into a slideshow by starting a new slide at each header or horizontal rule (e.g., ***).

Visit **rmakdown.rstudio.com** to learn about more YAML options that control the render process.


# References
- https://rmarkdown.rstudio.com/articles_intro.html
- https://cran.r-project.org/web/packages/rmarkdown/vignettes/rmarkdown.html
