Text string - A group of characters within a cell, commonly composed of letters, numbers, or both.
-When using functions to create a new column make sure to copy and "paste values only" so the column has the static values and not the function.

Locking a spreadsheet
	data -> protected sheets and ranges -> choose what you want to protect
MATCH - A function used to locate the position of a specific lookup value.

Sort sheet - All of the data in a spreadsheet is sorted by the ranking of a specific sorted column - data across rows is kept together.
	Menu
		1. Highlight the column
		2. Data -> Sort sheet

Sort range - Does not keep the rows together! Nothing else on the spreadsheet is rearranged besides the specified cells in a column.
	Menu
		1. Highlight the column
		2. Data -> Sort range
	Function
		=SORT(range, column we are sorting by, TRUE)
			TRUE = Ascending
			False = Decending

[[Pivot Table]]
	Select data to be used
	Data -> Pivot table
		New sheet and create
		Add in the main of what you want to a row
			Then add in values

$ is used to lock a colunm ($A2) or row (A$2) or both at the same time $A$2

IFS
	SUMIF - A function that adds numeric data based on one condition.
		=SUMIF(range, criteria/condition, [sum_range])
		=SUMIF(B2:B50, "=1", C3:C50)
		Multiple conditions
			=SUMIFS(sum_range, criteria_range1, criterion1, [criteria_range2, criterion2, ...])
				-The square brackets let you know that this is optional.
	COUNTIF - A function that returns the number of cells that match a specified value.
		=COUNTIF(rance, "value")
		=COUNTIF(H2:H72, "<100")
		Multiple conditions
			=COUNTIFS(criteria_range1, criterion1, [criteria_range2, criterion2, ...])
	AVERAGEIF
		=AVERAGEIF(range, criteria, [sum_range])
		=AVERAGEIF(B2:B21, "NY", D2:D21)
	MAXIF
		=MAXIFS(max_range, range1, criteria1, [range2], [criteria2], ...)
		=MAXIFS(D2:D21, B2:B21, "NY")

IF with AND, OR, and NOT
	AND
		=IF(AND(Something is True, Something else is True), Value if True, Value if False)
	OR 
		=IF(OR(Something is True, Something else is True), Value if True, Value if False)
	NOT 
		=IF(NOT(Something is True), Value if True, Value if False)
	https://support.microsoft.com/en-us/office/using-if-with-and-or-and-not-functions-d895f58c-b36c-419e-b1f2-5c193a236d97

SIMPLE Math Calculations
	Multiply
		=product(value, value)
	COUNT - Can be used to count the total number of numerical values within a specific range in spreadsheets.
	SUMPRODUCT - A function that multiplies arrays and returns the sum of those products.xf

LEN - A function that tells you the length of a text string by counting the number of characters it contains.
	=LEN(range)
	=LEN(A2)
	You can create a new colunm and use this to count the number of characters in a different column.
	Then use conditional formatting for if they are not equal to what the len should be.

Extracting Sub-Strings
LEFT - A function that gives you a set number of characters from the left side of a text string.
	=LEFT(range, number of characters)
	=LEFT(A2, 5)
RIGHT - A function that gives you a set number of characters from the right side of a text string.
	=RIGHT(range, number of characters)
	=RIGHT(A2, 4)
MID - A function that gives you a segment from the middle of a text string.
	=MID(range, reference starting point, number of middle characters)
	=MID(A2, 4, 2) - the 4 means it will start at the 4th character

Combining Text Strings
CONCATENATE - A function that joins together two or more text strings.
	=CONCATENATE(item 1, item 2)
	=CONCATENATE(H2, I2)

TRIM - A function that removes leading, trailing, and repeated spaces in data.
	=TRIM(range)
	=TRIM(C2)

VLOOKUP (Vertical Lookup) - A function that searches for a certain value in a column to return a corresponding piece of information. VLOOKUP only returns the first match it finds! Can only look to the right of the column that the function is in after a match is found.
	=VLOOKUP(data to look up/search for, 'where to look'!Range, column(within the range given), false)
	=VLOOKUP(A2, 'Sheet 2'!A1:B31, 2, false)
		False - tells VLOOKUP to find an exact match.
		True - tells VLOOKUP to find a close match.
	Preparing data for VLOOKUP
		Convert the data to be in a consistent format.
			Value, Trim, Remove Duplicates
		If you get #N/A 
			There isn't a matching vlaue that  can be returned.
			Replace the error with something descriptive
				IFNA(#N/A, "Does not exist")
				Syntax: IFNA(value, value_if_na)

Value - A function that converts a text string that represents a number to a numerical value.
	=VALUE(cell)
	=VALUE(A2)

COUNTA - A function that counts the total number of values within a specified range.
	Can be used in a pivot table editor

## Advanced Functions
IMPORTRANGE - Imports (pastes) data from one sheet to another and keeps it automatically updated.
	[Google support page for IMPORTRANGE](https://support.google.com/docs/answer/3093340?hl=en# "Google support page for IMPORTRANGE")
	Google Sheets
		=IMPORTRANGE(spreadsheet_url, range_string)
		Ex: =IMPORTRANGE("https://docs.google.com/spreadsheets", "sheet1!A1:C10")
	Excel
		Paste Link
QUERY - Enables pseudo SQL statements or a wizard to import the data.
	[Google support page for the QUERY function](https://support.google.com/docs/answer/3093343?hl=en "Google Support page for the QUERY function")
	Google Sheets
		=QUERY(Sheet and Range, "Select*")
	Excel
		Data -> From Other Sources -> From Microsoft Query
FILTER - Displays onlu the data that meets the specified conditions.
	[Google support page for the FILTER function](https://support.google.com/docs/answer/3093197?hl=en "Google Support page for the FILTER function")
	Google Sheets
		=FILTER(range, condition1, [condition2, ...])
	Excel
		Filter (conditions per column)
CONVERT
	From Celsius(-22) to Fahrenheit
	=CONVERT(-22, "C", "F")





