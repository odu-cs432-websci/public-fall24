# HW# - Title
### Your Name
### CS 432, Fall 2024
### Due Date

### Q1. Get TimeMaps for Each URI.

## Answer


*If you want to include code in your report, you can insert a screenshot (if it's legible), or you can copy/paste the code into a fenced code block.*

```python
import argparse
import subprocess
import time

x = 0

def process_uri(uri, x):
    memgator_path = 'C:\\Users\\ethan\\OneDrive\\Desktop\\CS\\memgator-windows-amd64'
    
    stringnumber = str(x)
    outputfile = "timemap"
    outputfile += stringnumber
    outputfile += ".json"
    
    print(outputfile)

    
    try:
        subprocess.run([memgator_path, "-c",
                        "'ODU CS432/532 ebarn023@odu.edu'", "-a", "https://raw.githubusercontent.com/odu-cs432-websci/public/main/archives.json",
                        "-F", "2", "-f", "JSON", uri, ">>", outputfile], shell = True)
        time.sleep(10)
    except subprocess.CalledProcessError as e:
        return f"Error fetching {uri}: {e}"

def process_uris(input_file):

    try:
        with open(input_file, 'r') as infile:
            for uris in infile:
                uri = uris.strip()
                global x
                x += 1
                process_uri(uri, x)           
                
                
                
    except Exception as e:
        print(f"An error occurred: {e}")

if __name__ == "__main__":
    parser = argparse.ArgumentParser()
    parser.add_argument('input_file', type=str)

    args = parser.parse_args()
    process_uris(args.input_file)

```



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

##Answer

# References

*Every report must list the references that you consulted while completing the assignment. If you consulted a webpage, you must include the URL.  These are just a couple examples.*

https://stackoverflow.com/questions/4856583/how-do-i-pipe-a-subprocess-call-to-a-text-file
