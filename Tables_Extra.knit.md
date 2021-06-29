---
title: "Tables"
author: "EE Holmes"
output:
  pdf_document: default
  html_document: default
  word_document: default
always_allow_html: yes
---

This is a more complex example of making tables.


```r
library(knitr)
library(kableExtra)
library(xtable)
output.type <- knitr::opts_knit$get('rmarkdown.pandoc.to')
output.type
```

```
## [1] "latex"
```

Here I'll use a data frame from from a R data set, but in practice your data frame would come from a function.

Note the first time you make a PDF, tinytex will load any needed packages and it can take a **long** time. You'll see a spinning wheel on the R Markdown tab.


```r
a <- mtcars[1:7, 1:6]
```

Default **kable** table.


```r
knitr::kable(a)
```


\begin{tabular}{l|r|r|r|r|r|r}
\hline
  & mpg & cyl & disp & hp & drat & wt\\
\hline
Mazda RX4 & 21.0 & 6 & 160 & 110 & 3.90 & 2.620\\
\hline
Mazda RX4 Wag & 21.0 & 6 & 160 & 110 & 3.90 & 2.875\\
\hline
Datsun 710 & 22.8 & 4 & 108 & 93 & 3.85 & 2.320\\
\hline
Hornet 4 Drive & 21.4 & 6 & 258 & 110 & 3.08 & 3.215\\
\hline
Hornet Sportabout & 18.7 & 8 & 360 & 175 & 3.15 & 3.440\\
\hline
Valiant & 18.1 & 6 & 225 & 105 & 2.76 & 3.460\\
\hline
Duster 360 & 14.3 & 8 & 360 & 245 & 3.21 & 3.570\\
\hline
\end{tabular}

This is the table with **xtable** for LaTeX and **kableExtra** for html.

\begin{table}[h]
\centering
\caption{My table caption 2021-06-29} 
\begin{tabular}{r|c|cccc}
  \hline
mpg & cyl & disp & hp & drat & wt \\ 
  \hline
21 & 6 & 160 & 110 & 4 & 3 \\ 
  21 & 6 & 160 & 110 & 4 & 3 \\ 
  23 & 4 & 108 & 93 & 4 & 2 \\ 
  21 & 6 & 258 & 110 & 3 & 3 \\ 
  19 & 8 & 360 & 175 & 3 & 3 \\ 
  18 & 6 & 225 & 105 & 3 & 3 \\ 
  14 & 8 & 360 & 245 & 3 & 4 \\ 
   \hline
\end{tabular}
\end{table}
\begin{landscape}\begin{table}[p]
\centering
\caption{My table caption 2021-06-29} 
\begin{tabular}{r|c|cccc}
  \hline
mpg & cyl & disp & hp & drat & wt \\ 
  \hline
21 & 6 & 160 & 110 & 4 & 3 \\ 
  21 & 6 & 160 & 110 & 4 & 3 \\ 
  23 & 4 & 108 & 93 & 4 & 2 \\ 
  21 & 6 & 258 & 110 & 3 & 3 \\ 
  19 & 8 & 360 & 175 & 3 & 3 \\ 
  18 & 6 & 225 & 105 & 3 & 3 \\ 
  14 & 8 & 360 & 245 & 3 & 4 \\ 
   \hline
\end{tabular}
\end{table}
\end{landscape}

