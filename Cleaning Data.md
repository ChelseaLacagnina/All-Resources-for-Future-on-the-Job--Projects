Identifying and cleaning data example - https://www.coursera.org/learn/process-data/quiz/YzKhK/hands-on-activity-clean-data-with-spreadsheet-functions/attempt

Motto - Take your time and be thourough!

Data-Cleaning Tools and Techniques
	1. Before cleaning the data, make a copy of the data set.
	2. Get rid of duplicates.
		1. data -> data cleanup -> remove duplicates
		2. Choose 'data has header row'
		3. select all
		4. Remove duplicates
	3. Remove irrelevant data (data you will not be using for your analysis).
	4. Remove extra spaces and blanks. 
		1. Remove Blanks
			1. Highlight all cells in the spreadsheet.
			2. Click on the **Data** tab and pick the **Create a filter** option.
			3. Click the green triangle in a Column to access a new menu.
			4. On that new menu, click **Filter by condition** and open the dropdown menu to select **Is empty.** Click **OK**
			5. Select all these cells and delete the rows except the row of column headers.
			6. Return to the **Filter by condition** and return it to **None**. In Excel, click **Clear Filter from ‘Column’**.
			7. Repeat this for all other Columns.
		2. Remove Extra spaces
			1. Highlight the data in the spreadsheet.
			2. Click on the **Data** tab, then hover over **Data cleanup** and select **Trim whitespace**.
	5. Fix misspellings, inconsistent capitalizations, and incorrect punctuation and other typos.
		1. Change Text Lower/Uppercase/Propercase
			1. Microsoft Excel - [this documentation](https://support.microsoft.com/en-us/office/change-the-case-of-text-in-excel-adc65f5b-958f-46a2-4d23-ab4d5faf48a8)
			2. Google Sheets
				1. Click on the **Add-Ons** option at the top of Google Sheets.
				2. Click on **Get add-ons**.
				3. Search for **ChangeCase**.
				4. Click on **Install** to install the add-on.
				5. Access it by clicking on the Extensions -> **Add-ons** menu again.
				6. Click on **Column C**. Be sure to deselect the column header.
				7. Click on the **Add-Ons** tab and select **ChangeCase**. Select the option **All uppercase*.
	6.  Formatting
		1. Delete all formatting
			1. Find the command in the **Format** tab.
			2. Select the data for which you want to delete the formatting.
			3. Select the data for which you want to delete the formatting.
				1. In Excel, go to the **Home** tab, then hover over **Clear** and select **Clear Formats**.
		2. Convert data from long format to wide format (transposing)
			1. Highlight and copy the data that you want to transpose including the column labels. You can do this by highlighting **Columns A-H**. In Excel, highlight only the relevant cells (**A1-H45**) instead of the headers.
			2. Right-click on **cell I1**. This is where you want the transposed data to start.
			3. Hover over **Paste Special** from the right-click menu. Select the **Transposed** option. In Excel, select the **Transpose** icon under the paste options.
			4. Delete the previous long data. The easiest way to do this is to click on **Column A**, so the entire column is highlighted. Then, hold down the **Shift** key and click on **Column H**. You should find these columns highlighted. Right-click on the highlighted area and select **Delete Columns A - H**.
		3. Conditional formatting - A spreadsheet tool that changes how cells appear when values meet specific conditions.
			1. Highlight columns you want to use
			2. Go to format, then conditional formatting
			3. See the apply range to make sure it is correct
			4. Add in format rules, such as "is empty"
			5. Create a formatting style, such as a bright pink highlight
			6. This highlights the blank cells in those columns
		4. Making formats consistent
			1. Select the column
			2. format
			3. what format you have, such as 'Date'
	https://www.coursera.org/learn/process-data/quiz/ucqPE/hands-on-activity-cleaning-data-with-spreadsheets/attempt

Split
	1. Highlight data column
	2. Data -> Split text to columns
	Helpful for splitting values stored as text -> makes it a number for easy calculating

Sort Range
	Also find them by Sorting
	Data -> sort range -> Advanced range sorting options


Plotting Data - Visual aid to see if there are any errors
	Select a column
	Insert -> Chart
	See if anything looks off

Cleaning Data from Multiple Sources
	1. Combine data through data merging
		1. Data merging - The process of combining two or more datasets into a single dataset.
	2. Asking key questions about compatibility
		Compatibility - How well two or more datasets are able to work together.
		1. Do I have all the data I need?
		2. Does the data I need exist within these datasets?
		3. Does the data need to be cleaned, or are they ready for me to use?
		4. Are the datasets cleaned to the same standards?
	3. Transforming data to a consistent format
		1. Use CONCATENATE to combine columns in one sheet to make it the same format as the other data sheet
		2. Select a sample piece of data from each sheet to make sure it is ready to merge
		To evaluate how well two or more data sources work together, data analysts use data mapping

## Common mistakes to avoid
-   **Not checking for spelling errors**: Misspellings can be as simple as typing or input errors.
-   **Forgetting to document errors**: Documenting your errors can be a big time saver, as it helps you avoid those errors in the future by showing you how you resolved them. Documenting your errors also helps you keep track of changes in your work, so that you can backtrack if a fix didn’t work. 
-   **Not checking for misfielded values**: A misfielded value happens when the values are entered into the wrong field. These values might still be formatted correctly, which makes them harder to catch if you aren’t careful. Making sure your data has been entered correctly is key to accurate, complete analysis. 
-   **Overlooking missing values**: Missing values in your dataset can create errors and give you inaccurate conclusions.
-   **Only looking at a subset of the data**: It is important to think about all of the relevant data when you are cleaning. This helps make sure you understand the whole story the data is telling, and that you are paying attention to all possible errors.
-   **Losing track of business objectives**: When you are cleaning data, you might make new and interesting discoveries about your dataset-- but you don’t want those discoveries to distract you from the task at hand. 
-   **Not fixing the source of the error:** Fixing the error itself is important. But if that error is actually part of a bigger problem, you need to find the source of the issue. Otherwise, you will have to keep fixing that same error over and over again. 
-   **Not analyzing the system prior to data cleaning:** If we want to clean our data and avoid future errors, we need to understand the root cause of your dirty data. 
-   **Not backing up your data prior to data cleaning**: It is always good to be proactive and create your data backup before you start your data clean-up. If your program crashes, or if your changes cause a problem in your dataset, you can always go back to the saved version and restore it. 
-   **Not accounting for data cleaning in your deadlines/process**: All good things take time, and that includes data cleaning. 

## Additional resources
-   [Top ten ways to clean your data](https://support.microsoft.com/en-us/office/top-ten-ways-to-clean-your-data-2844b620-677c-47a7-ac3e-c2e157d1db19 "Top ten ways to clean your data"): Review an orderly guide to data cleaning in Microsoft Excel.
-   [10 Google Workspace tips to clean up data](https://support.google.com/a/users/answer/9604139?hl=en#zippy= "Ten Google Workspace tips to clean up data"): Learn best practices for data cleaning in Google Sheets.

# Data-cleaning verification
Checklist
	**Sources of errors**: Did you use the right tools and functions to find the source of the errors in your dataset?
	**Null data**: Did you search for NULLs using conditional formatting and filters?
    **Misspelled words**: Did you locate all misspellings?
    **Mistyped numbers**: Did you double-check that your numeric data has been entered correctly?
    **Extra spaces and characters**: Did you remove any extra spaces or characters using the **TRIM** function? 
    **Duplicates**: Did you remove duplicates in spreadsheets using the **Remove Duplicates** function or **DISTINCT** in SQL?
    **Mismatched data types**: Did you check that numeric, date, and string data are typecast correctly?
    **Messy (inconsistent) strings**: Did you make sure that all of your strings are consistent and meaningful?
    **Messy (inconsistent) date formats**: Did you format the dates consistently throughout your dataset?
    **Misleading variable labels (columns)**: Did you name your columns meaningfully?
    **Truncated data:** Did you check for truncated or missing data that needs correction?
	**Business Logic**: Did you check that the data makes sense given your knowledge of the business?
Review the Project Goal
	Confirm the business problem 
    Confirm the goal of the project
	Verify that data can solve the problem and is aligned to the goal

# Formatting
### **String to date**
-   [**How to convert text to date in Excel**](https://www.ablebits.com/office-addins-blog/2015/03/26/excel-convert-text-date/#:~:text=Excel%20DATEVALUE%20function%20%2D%20change%20text,Excel%20recognizes%20as%20a%20date.&text=So%2C%20the%20formula%20to%20convert,stored%20as%20a%20text%20string. "This link takes you to a blog on how to convert text to a date in Microsoft Excel."):
-   [**Google Sheets: Change date format:**](https://www.ablebits.com/office-addins-blog/2019/08/13/google-sheets-change-date-format/ "This link takes you to a blog on how to change to a date format in Google Sheets.") 

### **String to numbers**
-   [**How to convert text to number in Excel:**](https://www.ablebits.com/office-addins-blog/2018/07/18/excel-convert-text-to-number/ "This link takes you to a blog on how to convert text to a number in Excel.") 
-   [**How to convert text to numbers in Google Sheets:**](https://productivityspot.com/convert-text-to-numbers-google-sheets/ "This link takes you to instructions to convert text to a number in Google Sheets.") 

### **Combining columns**
-   [**Convert text from two or more cells:**](https://support.microsoft.com/en-us/office/combine-text-from-two-or-more-cells-into-one-cell-81ba0946-ce78-42ed-b3c3-21340eb164a6 "This link takes you to a Microsoft Support page to merge text in multiple cells in Excel.")
-   [**How to split or combine cells in Google Sheets:**](https://www.techrepublic.com/article/how-to-split-or-combine-text-cells-with-google-sheets/ "This link takes you to an article with instructions to split or combine text in cells in Google Sheets.")

### **Number to percentage**
-   [**Format numbers as percentages:**](https://support.microsoft.com/en-us/office/format-numbers-as-percentages-de49167b-d603-4450-bcaa-31fba6c7b6b4 "This link takes you to a Microsoft Support page for formatting numbers as percentages.") 
-   [**TO_PERCENT:**](https://support.google.com/docs/answer/3094284?hl=en "This link takes you to the help page for the TO_PERCENT function in Google Sheets.") 
