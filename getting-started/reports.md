# Writing HW Reports

## General Guidelines

For each HW assignment, you are required to write a report. Reports are not just a list of questions and answers, but *must* include descriptions, screenshots, copy-paste of code output, references, as necessary.  For each question you address, you must provide a discussion of how you answered the question.  

You may use existing code, but you **must** document and reference where you adapted the code -- give credit where credit is due! *Use without attribution is plagiarism!*  **All reports must have a section labeled "References" for listing the outside resources you consulted.**

For an example of what I'm expecting, you can look at a [previous student's report](report-exemplar.pdf) (for an assignment that is no longer given).

## Submitting Reports

All students will have a GitHub repository created for their work in this class with the format:  
`https://github.com/odu-cs432-websci/fall24-username`, where `username` is your GitHub username.

Your HW submissions must have all of the files used to complete the assignment and generate the report, including code, images, LaTeX source, etc., in your class GitHub repository.  You are encouraged to use folders to separate files from each HW assignment ([example of creating a folder on GitHub.com via StackOverflow](https://stackoverflow.com/a/18791455)).

To submit your assignment, you'll submit the URL of your HW report.  

For instance, if my username is `ODUcoder`, I'm in CS 532 (so, generating a PDF report), and I've created a folder for HW1, then my HW1 report URL would be `https://github.com/odu-cs432-websci/fall24-ODUcoder/blob/main/HW1/HW1-report.pdf`

## Formatting Requirements

All reports must include your name, class (make sure to distinguish between CS 432 and CS 532), assignment number/title, and date.  You do not need a title page.

CS 432 students *may* complete their reports in Markdown or may choose to use LaTeX instead.

* I've provided a [Markdown report template](CS432-report-template.md) for CS 432 students.
* Your Markdown report and all images referenced in the report must be included in your GitHub repo.

CS 532 students *must* complete their reports using LaTeX generated to a PDF file.

* I've provided a [LaTeX report template in Overleaf](https://www.overleaf.com/read/tzvqcjvjtgdx).  You can view the PDF that's generated there as well.
  * You should sign up for a free [Overleaf](https://overleaf.com) account.
* When you include an image in your report, *do not change the [aspect ratio](https://en.wikipedia.org/wiki/Aspect_ratio_(image)) of the image*.
* You must include your .tex source file and any images used along with your .pdf report in your GitHub repo.  There are a couple different ways to do this.
  * Download the source files from Overleaf and upload to your GitHub repo.  See [Downloading a Project](https://www.overleaf.com/learn/how-to/Downloading_a_Project) for instructions on how to download a .zip file of your Overleaf project source files.  You should unzip this file locally and only upload the .tex, .pdf, and image files needed for your report to your GitHub repo.  Do not directly upload the .zip file to GitHub.
  * Connect your Overleaf project to your GitHub repo.  See ["How do I connect an Overleaf project with a repo on GitHub"](https://www.overleaf.com/learn/how-to/How_do_I_connect_an_Overleaf_project_with_a_repo_on_GitHub,_GitLab_or_BitBucket%3F) for instructions on how to do this.

When you are asked to include a graph/chart in your report, they must be generated in R or using a Python plotting library.  *Excel graphs are not acceptable.* Although scientific graphs can be created in Excel, I want you to become familiar with common data science tools.
