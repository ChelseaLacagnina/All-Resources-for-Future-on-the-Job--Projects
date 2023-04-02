Data Validation process - Checking and rechecking the quality of your data so that it is complete, accurate, secure and consistent.

## Spreadsheets
Data Validation - Allows you to control what can and can't be entered in your worksheet.
	Adds a dropdown list with predetermined options - Column Options
		Choose column -> Data-> data valudation-> cell range and criteria (list from a range) to make a dropdown
	Create custom checkboxes
		Choose column -> Data-> data valudation-> cell range and criteria (Checkbox) and click "Use custom cell values"
	Protect Structured Data and Formulas
		Choose column -> Data-> data valudation-> cell range and criteria and click "Reject input"

## SQL Queries
Data Validation
	Recaluculating totals and checking to see if they are correct in the column that is already there.
		Ex: Small_Bags + Large_Bags + XLarge_Bags AS Total_Bags_Calc
			Check that the Total_Bags column and Total_Bags_Calc column are the same.
	This can also be done by:
		SELECT *
		FROM (dataset)
		WHERE (column) != (column)
Types of Data Validation
	1. Data Type
		1. Purpose: Check that the data matches the data type defined for a field.
		2. Example: Data values for school grades 1-12 must be a numeric data type.
		3. Limitations: The data value 13 would pass the data type validation but would be an unacceptable value. For this case, data range validation is also needed.
	2. Data Range
		1. Purpose: Check that the data falls within an acceptable range of values defined for the field.
		2. Example: Data values for school grades should be values between 1 and 12.
		3. Limitations: The data value 11.5 would be in the data range and would also pass as a numeric data type. But, it would be unacceptable because there aren't half grades. For this case, data constraint validation is also needed.
	3. Data Constraint
		1. Purpose: Check that the data meets certain conditions or criteria for a field. This includes the type of data entered as well as other attributes of the field, such as number of characters.
		2. Example: Content constraint: Data values for school grades 1-12 must be whole numbers.
		3. Limitations: The data value 13 is a whole number and would pass the content constraint validation. But, it would be unacceptable since 13 isn’t a recognized school grade. For this case, data range validation is also needed.
	4. Data Consistency
		1. Purpose: Check that the data makes sense in the context of other related data.
		2. Example: Data values for product shipping dates can’t be earlier than product production dates.
		3. Limitations: Data might be consistent but still incorrect or inaccurate. A shipping date could be later than a production date and still be wrong.
	5. Data Structure
		1. Purpose: Check that the data follows or conforms to a set structure.
		2. Example: Web pages must follow a prescribed structure to be displayed properly.
		3. Limitations: A data structure might be correct with the data still incorrect or inaccurate. Content on a web page could be displayed properly and still contain the wrong information.
	6. Code Validation
		1. Purpose: Check that the application code systematically performs any of the previously mentioned validations during user data input.
		2. Example: Common problems discovered during code validation include: more than one data type allowed, data range checking not done, or ending of text strings not well defined.
		3. Limitations: Code validation might not validate all possible variations with data input.