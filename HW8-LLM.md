# Homework 8 - Exploring LLMs
**Due:** Monday, December 2, 2024 by 11:59pm

Read through the entire assignment before starting.  

## Assignment

This assignment will have you explore different ways of using LLMs, such as ChatGPT.  

Write a report that answers and *explains how you arrived at the answers* to the following questions.  Include any interesting findings that you discover from your analysis.  Include the links to any conversations that you have with ChatGPT.
 
Before starting, review the [HW report guidelines](getting-started/reports.md).  Name your report for this assignment `HW8-report` with the proper file extension. 

### Q1. Word Vectors

In the LLM lecture, we saw examples from the WebVectors website at <http://vectors.nlpl.eu/explore/embeddings/en/> ([read more about the project](http://vectors.nlpl.eu/explore/embeddings/en/about/)). In this question, you'll explore some of the tasks that the website enables. Use the "English Wikipedia" model, and use the [Random Noun Generator](https://randomwordgenerator.com/noun.php) to generate words.  Include screenshots in your report to document your work.

1. Use <http://vectors.nlpl.eu/explore/embeddings/en/misc/> to calculate semantic similarity between pairs of words.  Generate two random words and calculate their similarity.  Then change one of the two words so that you get a higher similarity value.
2. Use <http://vectors.nlpl.eu/explore/embeddings/en/similar/> to find words semantically closest to the query word. Generate a random word and find its 10 nearest semantic associates.  Click on the top rated semantic associate. Was the original word the top related word for it?  (For instance, if you started with "girlfriend" and found that "boyfriend" was the top associate, is "girlfriend" the top associate for "boyfriend"?)
3. Use <http://vectors.nlpl.eu/explore/embeddings/en/similar/> to get the visualizations for a word in the chosen model.  Generate a random word (different than the previous one), find its 10 nearest semantic associates, and click on the generated link ("Semantic associates for [LINKED WORD]") to see the visualization.  Include a screenshot of the force-directed diagram that is generated.

### Q2. ChatGPT Prompts

Find 5 interesting ChatGPT prompts and demonstrate their use. Document where you found out about the prompt.

### Q3. Explain Topic Using ChatGPT

Ask ChatGPT to explain a concept from this course that you’ve found confusing. Did the explanation help? Try continuing the conversation and asking further questions or to have it explained in a different way. 

### Q4. Explore Academic References with ChatGPT

Pick 3 members of the ODU faculty and ask ChatGPT to describe their research and provide 2 of their best known papers. Do the papers exist? Describe how you checked. 

## Submission

You should be working in the private GitHub repo that I created for you in the [odu-cs432-websci organization](https://github.com/odu-cs432-websci/) (your repo URL should look something like https<nolink>://github.com/odu-cs432-websci/fall24-*username*/). 

If you are working locally, make sure that you have committed and pushed your local repo, including `HW8-report.md` and any images you reference, to GitHub. 

Submit the URL of your report (*not the URL of your repo*) in Canvas under HW8. This should be something like  
https<nolink>://github.com/odu-cs432-websci/fall24-*username*/blob/main/HW8-report.md

*If you make changes to your report after submitting in Canvas, I will use the last commit time in your repo as your assignment submission time.*
