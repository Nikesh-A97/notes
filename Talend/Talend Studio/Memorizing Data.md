# Memorizing Data
---
##### Memorizing data Scenario
- Need a way to sort data and store non-standard columns such as history
- For example, the gross revenue for previous years
- A standard model has this stored in its own "history" line
- A process is needed to join the appropriate data

----
##### Problems with using an Auto-Join design
- Lets say you have  a table with years and revenue and asked to add a previous year
- This would not be a good idea for a large data set

---
##### `tMemorizeRows` component
- This component **retains** one or more previous rows of data in memory
- **Sort** your data first befire using it so that it is presented in groups and in order
- When the **current** row of data is processed, the component makes the *n* previous rows of data accessible in a table
- So use to access the previous rows, and current rows and process data as necessary
