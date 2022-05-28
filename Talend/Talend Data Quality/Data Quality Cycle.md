# Data Quality Cycle
---
No definition for Data Quality
It is an iterative process; the whole cycle or parts of it might have to be repeated to achieve the desired result

---
##### 1. Define metrics and rules
- Define metrics to measure the quality of data
- Define rules to enforce compliance with the business requirements

---
##### 2. Profile
- Analyze data to assess their *Completeness, Timeliness, Validity, Uniqueness, Accuracy and Consistency* 
- Usually done with the person in charge of the data

---
##### 3. Standardise
- Correct your data according to the standardisation rules defined
- For example
	- Convert and correct emails, phone numbers, etc

---
##### 4. Validate
- Checking if your data is actually correct
- The three main data to check for validation is
	- Adresses  - Can be verified at different levels with APIs that check  adresses
	- Phones - 
	- Emails

---
##### 5. Cleanse
- Remove data that is not valid and not needed in the target source.
- Keep rejected data
- Always ask the customer or the one in charge of the data what to do with invalid data
- Review data that cannot be automatically verified

---
##### 6. Match
- Apply the match rules, bocking keys, confidence levels and amtching algorithms to your data to create groups of possible duplicate records
- Helps categorize your records into unique, suspects and duplicates
![[Matching.png]]

---
##### 7. Merge
- Merge duplicates by applying the surviviorship rules
- The customer will have the rules on what exactly they want the end product to be
- Data Stewards should Inspect suspect and decide if they should be merged
![[survivor.png]]
- For Data Stewardship, not your job to correct it
- Resolution - Update, remove, correct records
- Grouping campaigns are used to group records in a data set
- Merginging campaign - where records should be merged
- Arbitration campaign - 

---
##### 8. Document
- Create documentation for each stage of the data quality cycle. Remember, Data Quality is an iterative process and you need to keep track of all processes in didfferent cycles.