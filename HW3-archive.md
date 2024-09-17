# Homework 3 - Web Archiving, part 1
**Due:** Sunday, October 20, 2024 by 11:59pm  

This assignment is going to take time. Read through the entire assignment before starting.  *Do not wait until the last minute to start working on it!* 

## Assignment

Write a report that contains the answers and *explains how you arrived at the answers* to the following questions.  Be sure to address any questions that are asked (indicated by "*Q: ...?*" in italics). Include any interesting findings that you discover from your analysis.  

Before starting, review the [HW report guidelines](getting-started/reports.md).  Name your report for this assignment `HW3-report` with the proper file extension. 

**Note about Programming Tasks:** For several of the programming tasks this semester, you will be asked to write code to operate on 100s or 1000s of data elements.  If you have not done this type of development before, I *strongly encourage* you to start small and work your way up.  Especially when you are using new tools or APIs, start on a small test dataset to make sure you understand how to use the tool and that your processing scripts are working before ramping up to the full set. *This will save you an enormous amount of time.*
 
### Q1. Get TimeMaps for Each URI.

Obtain the [TimeMaps](http://www.mementoweb.org/guide/quick-intro/) for each of the unique URIs you collected in HW1 using the [MemGator Memento Aggregator](https://github.com/oduwsdl/MemGator).  

*Do **not** use memgator.cs.odu.edu this assignment. You must download and install a local version of MemGator.*

There are two options for running MemGator locally:
* Install a stand-alone version of MemGator on your own machine, see <https://github.com/oduwsdl/MemGator/releases>
  * This was described in [EC-memgator](https://github.com/odu-cs432-websci/public-spr24/blob/main/getting-started/EC-memgator.md)
* Install [Docker Desktop](https://www.docker.com/products/docker-desktop) and run MemGator as a Docker Container, see notes at <https://github.com/oduwsdl/MemGator/blob/master/README.md>

Here's an example:

`./memgator-darwin-amd64 -c "ODU CS432/532 YOUR_EMAIL_ADDRESS" -a https://raw.githubusercontent.com/odu-cs432-websci/public/main/archives.json -F 2 -f JSON https://www.cs.odu.edu/~mweigle/ > mweigle-tm.json`

Notes:
* As described in [EC-memgator](https://github.com/odu-cs432-websci/public-spr24/blob/main/getting-started/EC-memgator.md), you **must** include the `-c` and `-a` options to specify your contact information and to use the alternate `archives.json` file.
* When running this for all of your URIs, you might want to use the MD5 hash that you recorded earlier as part of the filename to help keep track of which TimeMaps you have.
* You will want to add a sleep (at least 10-20 seconds) between each call to MemGator because if you make too many requests too quickly, you will get "connection refused" errors (or worse, get blocked by an archive). 

**Important:** Obtaining TimeMaps requires contacting several different web archives for each URI-R.  *This process will take time.*

Look at the MemGator options and figure out how to process the output before running the entire process. 

Note that if there are no mementos for a URI-R, MemGator will return nothing. *Don't be surprised if many of your URI-Rs return 0 mementos.*  Remember the ["How Much of the Web is Archived" slides](https://docs.google.com/presentation/d/132sObERXgzGbxVETIc8QblUyuXB6X7lDbrbhCKmAKzU/edit#slide=id.g80c031ceb5_0_91) -- there are lots of things on the web that are not archived.  If you want to do a sanity check on a few, you can manually use the Wayback Machine and see what you get from the Internet Archive.  (Remember though that MemGator is going to query several web archives, not only the Internet Archive.)

If you uncover TimeMaps that are very large (e.g., for popular sites like <https://www.cnn.com/>) and swamp your filesystem, you have two options:
* Manually remove those URI-Rs from your dataset (but note this in your report), or
* Compress each TimeMap file individually (using pipe to `gzip` in the same command when downloading or after the download is completed). These compressed files can be used for further analysis by decompressing on the fly using commands like `zcat` or `zless` (or using gzip libraries in Python).

Finally, upload the TimeMaps to your GitHub repo -- you'll also use these for Q2 and HW4.  Put them in a separate folder, not the same folder as your report.
* To upload/commit a large number of files to GitHub, [use the command line](https://docs.github.com/en/github/managing-files-in-a-repository/adding-a-file-to-a-repository-using-the-command-line).

### Q2. Analyze Mementos Per URI-R.

Use the TimeMaps you saved in Q1 to analyze how well the URIs you collected in HW1 are archived.

Create a table showing how many URI-Rs have certain number of mementos.  For example

|Mementos | URI-Rs |
|---------:|--------:|
|   0     |  250   |
|   1     |  100   |
|   7     |   50   |
|   12     |   25   |
|   19     |   25   |
|   24     |  20  |
|   30     |   27   |
|  57     |    3   |

If you are using LaTeX, you should create a [LaTeX table](https://www.overleaf.com/learn/latex/tables) -- don't submit a spreadsheet or image of a table created in something else.  If you are using Markdown, you can view the source of this file for an example of how to generate a table.

If you will end up with a very large table of memento counts, you can bin the number of mementos.  Just make sure that the bin sizes are reasonable and that you specify how many had 0 mementos individually. The target is to have no more than 15-20 rows so that your table can fit on a single page.  For example

|Mementos | URI-Rs |
|---------:|--------:|
|   0     |  250   |
|   1-10     |  150   |
|   11-20     |   50   |
|   21-30     |   47   |
|  57     |    3   |

*Q: What URI-Rs had the most mementos?  Did that surprise you?*
 

## Submission

You should be working in the private GitHub repo that I created for you in the [odu-cs432-websci organization](https://github.com/odu-cs432-websci/) (your repo URL should look something like https<nolink>://github.com/odu-cs432-websci/spr24-*username*/). 

If you are working locally, make sure that you have committed and pushed your local repo, including `HW3-report.md` and any images you reference, to GitHub. 

Submit the URL of your report (*not the URL of your repo*) in Canvas under HW3. This should be something like  
https<nolink>://github.com/odu-cs432-websci/spr24-*username*/blob/main/HW3-report.md

*If you make changes to your report after submitting in Canvas, I will use the last commit time in your repo as your assignment submission time.*
