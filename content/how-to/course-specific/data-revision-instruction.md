---
title: Data revision instructions
linktitle: Data revision
author: huaqing
toc: true
type: docs
date: "2016-09-30"
draft: false
menu:
  course-specific:
    parent: Course specific
    weight: 4

weight: 4
---
As our project develops into a database, it is important for us to ensure the accuracy of our content. One important step of this revision is to check one specific element/section/div across the full run of the Digital Egyptian Gazette.

## 1. Preparation
Before you start revising our project, you will need to have your fork of the
content repository updated. ([You can do it through pull request](/how-to/digitization/github-instructions/#5-how-do-i-make-sure-that-my-content-fork-is-up-to-date)). Download your folk of content repository trough Github Desktop and make a project or worksheet in your Oxygen XML Editor that covers all the former file you want to look at. Then, choose the element/section/div that you might want to revise, and find the template for it on our website.

List that feature or element on this [spreadsheet](https://docs.google.com/spreadsheets/d/187JP5PY11SP4sV1WWrDV3aC8riTQScX7tz6WF7_l_34/edit?usp=sharing), to be sure that you are not duplicating someone else's work.

## 2.  Search and Compare
Look at the template and think about the possible values that might appear if someone just copied the template and left it unchanged. Use the characteristics (such as type/element/feature/xml:id/scope) that defined your targeted div to do XPath queries.

For example, you can search `//table[@xml:id="deg-ta-shli01"]` to find all the specific tables in all files that associated with the xml id of "deg-ta-shli01".

Use more specific queries to search for the possible values that might appear. For example, the first value in the Share List (template 1) on our website is "13 13/16". And it is always in the 3rd cell of the 1st row of the first table of the Share List. Thus, we can use `//div[table[@xml:id="deg-ta-shli01"]/row[1]/cell[3]/measure` to locate all the unchanged "13 13/16" in our files by using Find/Replace in Files.

After you get all the possible result, compare more values in your targets and make sure that you only deal with those unchanged ones. Keep it mind that it is very possible that your result has the same value with the template by accident. Play with other values or queries to get the best result.

## 3. Replace and Update
Once you find a good query that allows you to locate all unchanged divs, you will need to add a comment in the very beginning of them to let others know the risk of using such bad sources. Here is an easy way to add comments to all of them instead of doing that manually.

Using the Share List part as an example, you can use `//div[child::table[@xml:id="deg-ta-shli01"]/row[1]/cell[3]/measure[contains(., "13 13/16")]]` in the Find/Replace in File tool to tell Oxygen to look at the div itself instead of the table inside the div.

Then, you can use this query to find `<head>` in the div and replace it with `<!-- incorrect value -->\n<head>`. Please remember to enable the regular expression. (See details in the image).

![replace example](data-revision-example.png)

After you add a comment for individual divs, you can search you comment to find these divs and update them according to the page-images on our website.

## 4. Submission
Once you finish the former process, it is time to submit those changes through your Github Desktop and open a pull request for them.
