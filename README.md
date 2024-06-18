This is an analysis to process customer data for business by a company whose existing systems in-place can only export to a CSV file. It involves data cleaning, transformation, enrichment, filtering, creation of JSON files to facilitate extraction and storage. Additionally, new metrics was derived to support detailed and accurate analysis.
The CSV file being a flat file was converted into a rich nested structure showing; 
a. Vehicle - which consists of the make, model, year, and type
b. Credit Card - which consists of the start date, end date, number, security code, and IBAN.
c. Address - which consists of the main address, city, and postcode
The values read in was also appropriately casted to their respective types
The empty cells encountered in the dependant column was meaningfully changed to enable the nesting carried out above to be effective while also taking note(in terms of row numbers) of where those errors occurred
It is worthy of note that  all records were written to a processed.json file in the JSON data format which is a list of dictionaries, where each index of the list is a dictionary representing a singular person. 
Additional file outputs, retired.json and employed.json, were also created which contains all retired customers (as indicated by the retired field in the CSV), and all employed customers respectively (as indicated by the employer field in the CSV).
Additionally, the issues with the credit card entries was overcomed by writing a function which accepts a single row from the CSV data to flag all customers that have more than 10 years between their start and end date; these were written to a separate file, called remove_ccard.json, in the JSON data format.
Various metrics was calculated for ranking customers; example of such is the salary commute which represent the Salary that a customer earns, per mile of their commute
