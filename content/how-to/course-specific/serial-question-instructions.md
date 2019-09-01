---
title: Serial question instructions
linktitle: Serial question
toc: true
type: docs
date: "2016-09-30"
draft: false
menu:
  course-specific:
    parent: Course specific
    weight: 3

weight: 3
---
Your final project is to consider a theme or question that recurs across many issues of the *Egyptian Gazette*

Part of your work is to compose a serial question that makes sense and can be answered by the dataset. Explain this question (supplying, for instance, the xpath formula you will use), and explain how you extract the results. For guidance on queries, consult the [tutorial](https://dig-eg-gaz.github.io/how-to/query-instructions).

To consult previous serial analysis projects, see this [directory](https://dig-eg-gaz.github.io/analysis/analysis).

<div class="panel radius" markdown="1">
**Contents**
{: #toc }
*  TOC
{:toc}
</div>

## How do I submit material?

Fork the [analysis](https://github.com/dig-eg-gaz/analysis) repository, add your analysis and images, and send a pull request. Do this at least twice: once you've finished your question, and a second time once you've written your analysis. It is fine to do it more often too, sending partial material or drafts. I will make comments, and you can revise them.

Make sure that *every* file name starts with your name (so that we don't get confused by a whole bunch of `graph.jpg` files), and that you have no spaces in your file names--use dashes instead.

## How do I format my serial analysis?

Write it in markdown.

Use a header:

```
---
layout: page
title: <!--- insert title --->
permalink: /analysis/2018/yourname-analysis
author: YourName
---
```

Name it `yourname-analysis.md`.

## What about images?

Please produce data visualization(s) to accompany your analysis.

You may use a variety of tools:

- [Palladio](http://hdlab.stanford.edu/palladio/)
- [Google charts](https://developers.google.com/chart/)
- [Tableau](https://dig-eg-gaz.github.io/how-to/visualization-instructions/)

## How do I show these visualizations in my markdown page?

The easiest thing to do is to take a screenshot and include the static image using markdown's code: `![image title](image-file-name.png)`.

If, however, you have produced an [interactive visualization](https://dig-eg-gaz.github.io/how-to/visualization-instructions/) using Tableau or Google Charts, you need to do two things to embed data visualizations in your markdown github pages.

1. Host the visualization:
- For Tableau, you will need to upload your workbook to Tableau Public's server. Use the "server" drop down menu and follow instructions. You will need to sign up for an online account, and you might have to save your dataset.
- For Google Charts, perhaps the easiest thing to do is to post your code as a [gist](https://gist.github.com/), then render it using a link from [rawgit](http://rawgit.com/).

2. Embed the visualization:
- For Tableau, a complete version of embedding instructions is included in this [excellent tutorial](https://www.datavizforall.org/embed/tableau/). Briefly, you need to click the share icon at the bottom right hand side of your web-hosted visualization. Take the link that it offers and paste it into this code:

`<iframe src="https://public.tableau.com/views/YOURURLHERE?:showVizHome=no&:embed=true" align="center" width="90%" height="500"></iframe>`

(For the `YOURURLHERE` part, include everything to the right of `views/` and to the left of the question mark. Your line should look something like this: `<iframe src="https://public.tableau.com/views/MESAPresentation/Honorifics?:showVizHome=no&:embed=true" align="center" width="90%" height="500"></iframe>`.) Paste this code into your markdown file.
- For Google Charts, place this bit of code in a markdown file, and your visualization should appear: `<iframe src="your-rawgit-link" width="90%" height="400"/>`
