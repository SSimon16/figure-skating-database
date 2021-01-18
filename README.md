# figure-skating-database
Structured Database built from ISU competition protocols

## Summary
This repository builds a structured database of figure skating scores from ISU competitions. Data sources include published competition protocol PDFs from the ISU ([example](http://www.isuresults.com/results/season1819/wc2019/wc2019_protocol.pdf) for the 2019 World Championships) and other ISU communications. 


## Background
The [International Skating Union] publishes competition result protocols for all major competitions ([example](http://www.isuresults.com/results/season1819/wc2019/wc2019_protocol.pdf). Each protocol includes all scores from a competition, and is available as a PDF online. Protocols are available from their inception in 2006 with the International Judging System (IJS) through present.  

## Data
Data is structured in the tables with the attributes below.  
The first attribute of each table (ending in "ID") is the table's primary key.

- **Skaters**: One entry for each skater
  - skID: A unique skater ID
  - Name: The skater's name
  - Nation: The nation the skater represents
  - Race: The skater's race
  - DOB: The skater's date of birth
- **Competitions**: One entry for each competition
  - competitionID: A unique competition ID
  - Competition: The competition name
  - Country: The country where the competition took place
  - City: The city where the competition took place
- **Events**: One entry for each event at a competition
  - eventID: A unique event ID
  - Event_Name: The name of the event
  - Number_of_Skaters: The number of skaters competing in the event
  - Start_Time: The start time of the event
  - Date: The date of the event
  - competitionID: Foreign key linking each event to the competition it was a part of
- **Protocols**: One entry for each protocol (and therefore each program performed) at an event
  - pID: A unique protocol ID
  - Event_Rank: The ranking (1, 2, 3) of the program in the event
  - Event_StartNum: The start number of the program in the event
  - Event_Total_Score: The total score of the program
  - Element_Score: The total element score of the program
  - Total_Element_Base_Value: The total element base value of the program
  - Total_GOE_Points: The total score from GOE for the program
  - Component_Score: The total program component score of the program
  - Deductions: The total deductions received for the program
  - J1ID: A unique ID for judge 1
  - J2ID: A unique ID for judge 2
  - J3ID: A unique ID for judge 3
  - J4ID: A unique ID for judge 4
  - J5ID: A unique ID for judge 5
  - J6ID: A unique ID for judge 6
  - J7ID: A unique ID for judge 7
  - J8ID: A unique ID for judge 8
  - J9ID: A unique ID for judge 9
  - REFID: A unique ID for the referee
  - TCID: A unique ID for the technical controller
  - TSID: A unique ID for the technical specialist
  - ATSID: A unique ID for the assistant technical specialist
  - skID: A foreign key linking each program to the skater who performed it
  - eventID: A foreign key linking each program to the event it was performed at
- **Elements**
  - 
- **Element_Details**
- **Program_Components**
- **Officials**
- **Event_Officials**
- **Coaches**
- **Skater_Coaches**

## Current Status and Planned Next Steps
Currently, this project downloads and structures data from the first event (the pairs SP) at 2019 Worlds into structured dataframes in python. 

- Expand code to include additional events
- Expand code to include additional competitions
- Create entity-relationship (ER) diagram of database
- Move csv files and dataframes of data to a database, for further analysis
- Expand project to include additional skater, coach, and official information
- Add a glossary of terms for this project

## Questions and Feedback
Please contact Spencer Simon at spencersimon16@gmail.com with questions or feedback.
