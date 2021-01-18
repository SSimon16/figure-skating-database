# figure-skating-database
Structured Database built from ISU competition protocols

## Summary
This repository builds a structured database of figure skating scores from ISU competitions. Data sources include published competition protocol PDFs from the ISU ([example](http://www.isuresults.com/results/season1819/wc2019/wc2019_protocol.pdf)) for the 2019 World Championships) and other ISU communications. 


## Background
The [International Skating Union](https://www.isu.org) publishes competition result protocols for all major competitions ([example](http://www.isuresults.com/results/season1819/wc2019/wc2019_protocol.pdf)). Each protocol includes all scores from a competition, and is available as a PDF online. Protocols are available from their inception in 2006 with the International Judging System (IJS) through present.  

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
- **Elements**: One entry for each element performed
  - elemID: A unique element ID
  - Element_Number: The element number for the element within the program
  - Elem_Code: The shorthand code for the element
  - Info: "X" marker for jumps performed in the bonus
  - Base_Value: The base value score of the element
  - GOE_Points: The additional score awarded to the element from GOE
  - J1_score: The GOE given to the element by judge 1
  - J2_score: The GOE given to the element by judge 2
  - J3_score: The GOE given to the element by judge 3
  - J4_score: The GOE given to the element by judge 4
  - J5_score: The GOE given to the element by judge 5
  - J6_score: The GOE given to the element by judge 6
  - J7_score: The GOE given to the element by judge 7
  - J8_score: The GOE given to the element by judge 8
  - J9_score: The GOE given to the element by judge 9
  - Element_Points: The total number of points scored by the element
  -pID: A foreign key linking each element to the program it was performed in
- **Element_Details**: One entry for every possible element 
  - Elem_Code: A shorthand code for each element. Used as the primary key since it is unique to each element.
  - Name: The name of the element
  - Type: The type of the element (e.g. Jump)
  - lvl: The level of the element
- **Program_Components**: One entry for each program component of the program
  - pcID: A unique ID for each program component
  - Component: The name of the program component
  - Factor: The factor used in scoring for the program component
  - J1_score: The component score given by judge 1
  - J2_score: The component score given by judge 2
  - J3_score: The component score given by judge 3
  - J4_score: The component score given by judge 4
  - J5_score: The component score given by judge 5
  - J6_score: The component score given by judge 6
  - J7_score: The component score given by judge 7
  - J8_score: The component score given by judge 8
  - J9_score: The component score given by judge 9
  - Component_Score: The overall score awarded for that component
  - pID: A foreign key linking each program component to the program it was performed in
- **Officials**: One entry for each ISU official
- **Event_Officials**: A table linking officials to the events they officiated at One entry for each link. 
- **Coaches**: One entry for coach
- **Skater_Coaches**: A table linking coaches to the skaters they train

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
