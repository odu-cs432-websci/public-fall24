# Homework 4 - Web Archiving, part 2
**Due:** Sunday, October 27, 2024 by 11:59pm  

Read through the entire assignment before starting.  

## Assignment

Write a report that contains the answers and *explains how you arrived at the answers* to the following questions.  Be sure to address any questions that are asked (indicated by "*Q: ...?*" in italics). Include any interesting findings that you discover from your analysis.  

Before starting, review the [HW report guidelines](getting-started/reports.md).  Name your report for this assignment `HW4-report` with the proper file extension. 

**Important:** This assignment is a continuation of HW3. If you did not complete HW3 satisfactorily, contact me for instructions on how to proceed. This **cannot** be done at the last minute.

### Q1. Analyze Datetimes of Mementos.

For each of the URI-Rs from HW3, Q2 that had > 0 mementos, use the saved TimeMap to determine the datetime of the earliest memento. 

Create a scatterplot with the age of each URI-R (days between collection date and earliest memento datetime) on the x-axis and number of mementos for that URI-R on the y-axis.  For this graph, the item is the URI-R and the attributes are the estimated age of the URI-R (channel is horizontal position) and the number of mementos for that URI-R (channel is vertical position).

An example is shown below:

![hw4-scatterplot-example.png](hw4-scatterplot-example.png)

This scatterplot should be created using either R or Python, not Excel.

*Q: What can you say about the relationship between the age of a URI-R and the number of its mementos?*

*Q: What URI-R had the oldest memento? Did that surprise you?*

*Q: How many URI-Rs had an age of < 1 week, meaning that their first memento was captured the same week you collected the data?*                                                              
                                                                      
### Q2. Explore Conifer and ReplayWeb.Page

Create an account at [Conifer](https://conifer.rhizome.org) and create a collection.  Archive at least 10 webpages related to a common topic that you find interesting. Make the collection public and include the link to your collection in your report.

*Q: Why did you choose this particular topic?*

*Q: Did you have any issues in archiving the webpages?*

*Q: Do the archived webpages look like the original webpages?*

After creating your collection at Conifer, download the collection as a WARC file (see [Exporting or Downloading Content](https://guide.conifer.rhizome.org/docs/manage-sessions/exporting-warc/)).

Then load this WARC file into [ReplayWeb.page](https://replayweb.page), a tool from the Webrecorder Project (folks who developed Conifer).  From <https://webrecorder.net/tools>:

<blockquote>ReplayWeb.page provides a web archive replay system as a single web site (which also works offline), allowing users to view web archives from anywhere, including local computer or even Google Drive. See the <a href="https://replayweb.page/docs">User guide</a> for more info.</blockquote>

Once the WARC file has loaded, click on the "Pages" tab.  Take a screenshot that includes the list of pages and the browser address bar (showing `replayweb.page/?source=file%3A%2F%2F`..., which indicates that the WARC file is being loaded from your local computer).

Then click on the "URLs" tab and choose "All URLs" from the dropdown menu.  

*Q: How many URLs were archived in the WARC file?  How does this compare to the number of Pages?*

Create a bar chart showing the number of URLs in the WARC file for each of the file types in the dropdown menu.

*Q: Which file type had the most URLs?  Were you surprised by this?*

## Submission

You should be working in the private GitHub repo that I created for you in the [odu-cs432-websci organization](https://github.com/odu-cs432-websci/) (your repo URL should look something like https<nolink>://github.com/odu-cs432-websci/fall24-*username*/). 

If you are working locally, make sure that you have committed and pushed your local repo, including `HW4-report.md` and any images you reference, to GitHub. 

Submit the URL of your report (*not the URL of your repo*) in Canvas under HW4. This should be something like  
https<nolink>://github.com/odu-cs432-websci/fall24-*username*/blob/main/HW4-report.md

*If you make changes to your report after submitting in Canvas, I will use the last commit time in your repo as your assignment submission time.*
