# Homework 1 - Web Science Intro
**Due:** Sunday, September 15, 2024 by 11:59pm
 
*Read the entire assignment before starting.*

## Assignment

Write a report that contains the answers and *explains how you arrived at the answers* to the following questions. Before starting, review the [HW report guidelines](getting-started/reports.md).  Name your report for this assignment `HW1-report` with the proper file extension. 

### Q1
Consider the "bow-tie" structure of the web in the Broder et al. paper ["Graph Structure in the Web"](http://snap.stanford.edu/class/cs224w-readings/broder00bowtie.pdf) that was described in Module 1. 

Now consider the following links:

```text
A --> B
B --> A
B --> C
C --> D
C --> G
D --> A
D --> H
E --> F
E --> O
F --> G
G --> C
H --> L
J --> N
K --> I
M --> A
N --> L
O --> J
```

Draw the resulting [directed graph](https://en.wikipedia.org/wiki/Directed_graph) (either sketch on paper or use another tool) showing how the nodes are connected to each other and include an image in your report.  This does not need to fit into the bow-tie type diagram, but should look more similar to the graph on slide 24 from [Module-01 Web-Science-Architecture](https://docs.google.com/presentation/d/178GkNtFAPB5fzs1D-wdCnlOdbcTyhpAIz_wKxVUaHVk/edit#slide=id.ga9773ac230_0_799).

For the graph, list the nodes (in alphabetical order) that are each of the following categories:
* SCC: 
* IN: 
* OUT: 
* Tendrils: 
    * indicate if the tendril is reachable from IN or can reach OUT
* Tubes: 
    * explain how the nodes serve as tubes
* Disconnected:
    
    
### Q2
Demonstrate that you know how to use `curl` and are familiar with the available options.  Complete the following steps using https://www.cs.odu.edu/~mweigle/courses/cs532/ua_echo.php as the URI to request. Explain the results you get from each step.

a) First, load the webpage at the URI in your web browser.  The result should show the "User-Agent" HTTP request header that your web browser sends to the web server. Take a screenshot to include in your report.

b) Use a single `curl` command with the appropriate options to do the following:
  * request the URI
  * show the HTTP response headers
  * follow any redirects
  * change the User-Agent HTTP request field to "CS432/532"

Take a screenshot of the `curl` command and options you used and the result of your execution to include in your report.

c) Use a single `curl` command with the appropriate options to do the following:
  * request the URI
  * follow any redirects
  * change the User-Agent HTTP request field to "CS432/532"
  * save the HTML output to a file

Take a screenshot of the `curl` command and options you used and the result of your execution to include in your report.  

d) View the HTML output file that was produced by `curl` from part c in a web browser and take a screenshot to include in your report.

### Q3

For some of our later assignments, you will be analyzing large numbers of webpages. The goal of this question is to write a Python program to gather URIs of webpages that have enough text so they will be useful later.

Your program must do the following:
* take the URI of a seed webpage as a command-line argument
* extract all the links from the page's HTML
* for each link, request the URI and use the `Content-Type` HTTP response header to determine if the link references an HTML file (`text/html`)
    * if it does, use the `Content-Length` HTTP response header to determine if it contains more than 1000 bytes
       * if it does, then print the final URI (after any redirects) 

Use this program to collect at least 500 **unique** URIs of webpages that contain more than 1000 bytes.  Save the list of URIs to a file to use in later assignments.  The file must be uploaded to your GitHub repo.

Be aware of the need for a timeout.  If you use the Python requests library, make sure to include the [timeout](https://docs.python-requests.org/en/master/user/quickstart/#timeouts) parameter to your call to `get()`.  
* Example: `requests.get(url, timeout=5)   # 5 second timeout`

There are a couple ways you can use your program to gather the URIs:
* run the program multiple times with different seed webpages until you get to 500
* have your program randomly pick a URI that you've collected and use that as the new seed until you've collected 500 unique URIs

Here is a snippet of the expected operation:

```
% python3 collect-webpages.py https://weiglemc.github.io/
https://weiglemc.github.io/
https://weiglemc.github.io/publications/
https://weiglemc.github.io/teaching/
https://weiglemc.github.io/students/
https://weiglemc.github.io/talks/
https://weiglemc.github.io/schedule/
https://weiglemc.github.io/cv/
https://weiglemc.github.io/contact/
https://www.odu.edu/
https://www.odu.edu/facultydevelopment/women-in-stem#tab9=3&done1612907281342
https://www.odu.edu/computer-science/academics/graduate/masters
https://www.odu.edu/computer-science/academics/graduate/phd
https://oduwsdl.github.io/
https://weiglemc.github.io/publications/recent
https://minerva.defense.gov/Research/Funded-Projects/Article/2957187/innovating-interdisciplinary-methods-for-hard-to-reach-environments/
https://oducsreu.github.io
https://www.odu.edu/computer-science
https://www.clemson.edu/cecas/departments/computing/
https://cs.unc.edu/
https://www.unc.edu/
http://jekyllrb.com/
https://mademistakes.com/work/jekyll-themes/minimal-mistakes/
```

**Another Example**
```
% python3 collect-webpages.py https://weiglemc.github.io/ 200
Need to collect 178 more URIs...
 random seed: https://cs.unc.edu/
Need to collect 125 more URIs...
 random seed: https://cs.unc.edu/event/resume-workshop/
Need to collect 121 more URIs...
 random seed: https://give.unc.edu/donate?p=COMP
Need to collect 114 more URIs...
 random seed: https://cs.unc.edu/undergraduate/lecture-archive/
Need to collect 110 more URIs...
 random seed: https://weiglemc.github.io/talks/
Need to collect 89 more URIs...
 random seed: https://www.matchinggifts.com/unc/
Need to collect 77 more URIs...
 random seed: https://cs.unc.edu/undergraduate/ug-advising/
Need to collect 71 more URIs...
 random seed: https://cs.unc.edu/research/facilities/
Need to collect 69 more URIs...
 random seed: https://cs.unc.edu/person/john-majikes/
Need to collect 68 more URIs...
 random seed: https://weiglemc.github.io/students/
Need to collect 54 more URIs...
 random seed: https://weiglemc.github.io/talks/2020-11-09-course
Need to collect 54 more URIs...
 random seed: https://sigir.org/sigir2019/
Need to collect 41 more URIs...
 random seed: https://cs.unc.edu/undergraduate/courses-for-non-majors/
Need to collect 41 more URIs...
 random seed: https://www.loc.gov/programs/web-archiving/about-this-program/
Need to collect 30 more URIs...
 random seed: https://sciences.sorbonne-universite.fr/

Collected 200 unique URIs
https://weiglemc.github.io/
https://weiglemc.github.io/publications/
https://weiglemc.github.io/teaching/
https://weiglemc.github.io/students/
https://weiglemc.github.io/talks/
https://weiglemc.github.io/schedule/
https://weiglemc.github.io/cv/
https://weiglemc.github.io/contact/
...
```

In your report, describe which method you used to collect the 500 URIs and provide a list of the seed webpages that you used.

You will likely want to use the BeautifulSoup Python library for this question. On the ODU-CS Linux machines, you may need to run `pip3 install beautifulsoup4` before you can use BeautifulSoup, but you don't need root privileges to do this.

## Submission

You should be working in the private GitHub repo that I created for you in the [odu-cs432-websci organization](https://github.com/odu-cs432-websci/) (your repo URL should look something like https<nolink>://github.com/odu-cs432-websci/spr24-*username*/). 

If you are working locally, make sure that you have committed and pushed your local repo, including `HW1-report.md` or `HW1-report.pdf` (and `HW1-report.tex`) and any images you reference, to GitHub. 

Submit the URL of your report (*not the URL of your repo*) in Canvas under HW1. This should be something like  
https<nolink>://github.com/odu-cs432-websci/spr24-*username*/blob/main/HW1-report.{pdf,md}

*If you make changes to your report after submitting in Canvas, I will use the last commit time in your repo as your assignment submission time.*
