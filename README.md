# Module3_Challenge
# Election_Analysis

## Project Overview
Tom is looking to do audit recent US congressional election data for Colorado. He is looking to find key outcomes like, winner of the election, vote share of the election and turnouts from different counties. Tom’s manager is looking to automate the audit process to make it more efficient and faster. 

## Purpose
The purpose of this project is to automate the process of audit for US congressional election which can be replicated to other electoral levels.

# Results
  
  •	Total number of vote casted in this congressional election
  
    o	As per the audit, total number of votes casted for this election were 369,711
 
 •	Breakdown of number of votes and percentage of total votes for each county
 
    o	Jefferson county casted 38855 votes, 10.51% of total votes casted
    
    o	Denver county casted 306055 votes, 82.78% of total votes casted
    
    o	Arapahoe county casted 24801 votes, 06.71% of total votes casted
  
  •	County with largest number of votes
  
    o	Denver county had largest number of votes with 306055 votes
  
  •	Breakdown of number of votes and percentage of total votes received by a candidate

    o	Charles Casper Stockham received 23.05% of vote and 85213 number of votes

    o	Diana DeGette received 73.81% of vote and 272892 number of votes

    o	Raymon Anthony Doane received 03.14% of vote and 11606 number of votes

•	Winner of the election

    o	Diana DeGette who received 73.81% of vote and 272892 number of votes


# Summary

Audit process for each congressional election is a tedious process as it requires accuracy and have to be efficient enough to get finished in stipulated timeline. Manual processing always takes more time and subject to high chance of error due to human interventions. Also, manual process requires multiple checkpoints to avoid quality issues, biasness and human error. This makes it more time consuming.

As a python expert, we have developed a python code for the automation of auditing the electoral data to provide best possible insights like votes counting, votes percentage distribution, election turnout ratios and elected candidate details. The code is efficient enough to be replicated for all future elections after implementing few changes and can be utilized to get instant results as soon as the electoral data is collated. The code is very well tested on the available electoral data for district of Colorado and is quick, robust and successful to provide accurate results.

However, there are few modifications can be implemented as below to use it for other elections:

1.	We can use header of the data to make the output more relevant. If in case we are using the code to run at state level data and sub-hierarchy is district than the current output will not make any sense. Hence, we can make following changes in the code for the output section. 

   
     …
   
     …
   
     with open(file_to_load) as election_data:
     
        file_reader = csv.reader(election_data)
      
        header = next(file_reader)
        
        # Creating variable for storing level of hierarchy for election
        
        
         resultAt = header[1]
    
      …
      
      …
      
        election_results = (
            f"\nElection Results\n"
            f"-------------------------\n"
            f"Total Votes: {total_votes:,}\n"
            f"-------------------------\n\n"
            f"{resultAt} Votes:\n")
    
       …
    
      …
      
        largest_county_summary = (
            f"\n-------------------------\n"
            f"Largest {resultAt} Turnout: {winning_county}\n"
            f"-------------------------\n")
    
      …
    
      …
2.	If we have to run multiple audits for different districts/states than we can take input from user for the filename (input and output) to make it easier for the user to run the program one by one successively without wasting time in renaming the files. We can simply put input & output of filename in 2 different variables and pass on the open command in the code, instead of hard coded filename. 
        
        …
        
        …
        
        # Creating variable for input file
        
        dataInFile = input("Please provide filename for electoral data:")
        
        # Creating variable for output file
        
        dataOutFile = input("please provide output filename:")
    
        # Add a variable to load a file from a path
    
        file_to_load = os.path.join("Resources", dataInFile + ".csv")
    
        # Add a variable to save the file to a path
    
        file_to_save = os.path.join("analysis", dataOutFile + ".txt")	
    
        …
    
        …

In conclusion, the python code written for the analysis of electoral data will provide you multi-fold benefits such as increased processing rate, reduction in error and quick processing of the data. 
