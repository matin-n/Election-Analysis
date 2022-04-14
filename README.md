# Election Analysis

## Project Overview
### Purpose
A Colorado Board of Elections employee has been given the following tasks to complete the election audit of a recent local congressional election. The purpose of this audit is to analyze the candidates and counties:

#### Candidate
- Calculate the total votes in the election
- Calculate each candidate's total vote and percentage of votes
- Determine the winner of the election, winning vote count, and winning percentage of votes

#### County
- Determine each county and its total vote county
- Calculate each county's percentage of total votes
- Determine the county with the most substantial number of voters

## Election Audit Results
The analysis shows that:
- There was a total of 369,711 votes cast in the election
#### Candidate
The candidate's results:
| **Canidate**            | **Acquired Votes** | **Acquired Votes (Percentage)** |
|:------------------------|:------------------:|:-------------------------------:|
| Charles Casper Stockham | 85,213             | 23.0%                           |
| Diana DeGette           | 272,892            | 73.8%                           |
| Raymon Anthony Doane    | 11,606             | 3.1%                            |
- Diana DeGette was the winner of the election
  - Acquired 73.8% of the votes and accumulated 272,892 votes
  
 #### County 
The counties results:
| **County** | **Acquired Votes** | **Acquired Votes (Percentage)** |
|:-----------|:------------------:|:-------------------------------:|
| Jefferson  | 38,885             | 10.5%                           |
| Denver     | 306,055            | 82.8%                           |
| Arapahoe   | 24,801             | 6.7%                            |

- Denver had the most significant country turnout rate of votes
    - Acquired 82.8% of the votes and accumulated 306,055 votes

#### Election Analysis 
```
Election Results
-------------------------
Total Votes: 369,711
-------------------------

County Votes:
Jefferson: 10.5% (38,855)
Denver: 82.8% (306,055)
Arapahoe: 6.7% (24,801)

-------------------------
Largest County Turnout: Denver
-------------------------
Charles Casper Stockham: 23.0% (85,213)
Diana DeGette: 73.8% (272,892)
Raymon Anthony Doane: 3.1% (11,606)
-------------------------
Winner: Diana DeGette
Winning Vote Count: 272,892
Winning Percentage: 73.8%
-------------------------
```


## Summary

I propose that this script gets modified for the election commission to be used for any election. One solution is to remove the hardcoded variable of `file_to_load = os.path.join("Resources", "election_results.csv")` to a dynamic input given by the user. A snippet of code that used for removing the hardcoded filename is:

```Python
# Add a variable to load a file from a path.
election_file = input("What is the file name of file that contains the election results? (ex. election_results.csv)\n")
file_to_load = os.path.join("Resources", election_file)

# Ask user for input again if file does not exist
while not os.path.isfile(os.path.join("Resources", election_file)):
    print("ERROR!", "File not found. Check to see if the file exists.")
    election_file = input("What is the file name of file that contains the election results? (ex. election_results.csv) \n")
```


The second proposal is to conduct further analysis by analyzing supplemental data, such as the election results of each year. For example, we could modify the `election_results.csv` to include the election results of each year as a new column and have the script read the new columns. The yearly data can be achieved by making the script read multiple CSV files and then merge the dataset into a single CSV file or conduct the analysis in memory without writing to a new column. We could then conduct additional analysis for each year and compare the results. Resources to achieve this task can be found with [Pandas library](https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html) or [files.write()](https://www.kite.com/python/answers/how-to-concatenate-two-csv-files-in-python).

## Resources
- Source Code: [`PyPoll_Challenge.py`](PyPoll_Challenge.py)
- Data Source: [`election_results.csv`](Resources/election_results.csv)
- Analysis Results: [`election_analysis.txt`](Analysis/election_analysis.txt)
- Software: [Python 3.9.12](https://www.python.org/downloads/release/python-3912/), [JetBrains PyCharm 2021](https://www.jetbrains.com/pycharm/)
