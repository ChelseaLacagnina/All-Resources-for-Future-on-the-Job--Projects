
### **Google Sheets**
In Google Sheets, you can use the IMPORTRANGE function. It enables you to specify a range of cells in the other spreadsheet to duplicate in the spreadsheet you are working in. You must allow access to the spreadsheet containing the data the first time you import the data.
Refer to the Google Help Center's [IMPORTRANGE](https://support.google.com/docs/answer/3093340?hl=en&ref_topic=9199554 "IMPORTRANGE") page for more information about the syntax. There is also an example of its use later in the program in [Advanced functions for speedy data cleaning](https://www.coursera.org/learn/process-data/supplement/PLnRS/advanced-functions-for-speedy-data-cleaning).

### **Microsoft Excel**
To import data from another spreadsheet, do the following:
**Step 1:** Select **Data** from the main menu.
**Step 2:** Click **Get Data**, select **From File**, and then select **From Workbook**.
**Step 3:** Browse for and select the spreadsheet file and then click **Import**.
**Step 4:** In the Navigator, select which worksheet to import.
**Step 5:** Click **Load** to import all the data in the worksheet; or click **Transform Data** to open the Power Query Editor to adjust the columns and rows of data you want to import.
**Step 6:** If you clicked Transform Data, click **Close & Load** and then select one of the two options:
-   **Close & Load** - import the data to a new worksheet
-   **Close & Load to...** - import the data to an existing worksheet
If these directions do not work for the version of Excel that you have. Visit this free online training center, [Microsoft Excel for Windows Training](https://support.microsoft.com/en-us/office/excel-video-training-9bc05390-e94c-46af-a5b3-d7c22f6990bb "Microsoft Excel for Windows Training"), you will find everything you need to know, all in one place.
If you are using Numbers, search the [Numbers User Guide](https://support.apple.com/guide/numbers/welcome/mac "Numbers Uswer Guide") for directions.

## Importing data from CSV files

### **Google Sheets**
**Step 1:** Open the **File** menu in your spreadsheet and select **Import** to open the Import file window.
**Step 2:** Select **Upload** and then select the CSV file you want to import.
**Step 3:** From here, you will have a few options. For **Import location**, you can choose to replace the current spreadsheet, create a new spreadsheet, insert the CSV data as a new sheet, add the data to the current spreadsheet, or replace the data in a specific cell. The data will be inserted as plain text only if you _uncheck_ the Convert text to numbers, dates, and formulas checkbox, which is the default setting. Sometimes a CSV file uses a separator like a semi-colon or even a blank space instead of a comma. For **Separator type**, you can select Tab or Comma, or select Custom to enter another character that is being used as the separator.
**Step 4:** Select **Import data**. The data in the CSV file will be loaded into your sheet, and you can begin using it!
**Note:** You can also use the **IMPORTDATA** function in a spreadsheet cell to import data using the URL to a CSV file. Refer to Google Help Center's [IMPORTDATA](https://support.google.com/docs/answer/3093335?hl=en "IMPORTDATA") page for more information and the syntax.

### **Microsoft Excel**
**Step 1:** Open a new or existing spreadsheet
**Step 2:** Click **Data** in the main menu and select the **From Text/CSV** option.
**Step 3:** Browse for and select the CSV file and then click **Import**.
**Step 4:** From here, you will have a few options. You can change the delimiter from a comma to another character such as a semicolon. You can also turn automatic data type detection on or off. And, finally, you can transform your data by clicking **Transform Data** to open the Power Query Editor.
**Step 5:** In most cases, accept the default settings in the previous step and click **Load** to load the data in the CSV file to the spreadsheet. The data in the CSV file will be loaded into the spreadsheet, and you can begin working with the data.
If these directions do not work for the version of Excel that you have. Visit this free online training center, [Microsoft Excel for Windows Training](https://support.microsoft.com/en-us/office/excel-video-training-9bc05390-e94c-46af-a5b3-d7c22f6990bb "Microsoft Excel for Windows Training"), you will find everything you need to know, all in one place.
If you are using Numbers, search the [Numbers User Guide](https://support.apple.com/guide/numbers/welcome/mac "Numbers Uswer Guide") for directions.

## Importing HTML tables from web pages
Importing HTML tables is a very basic method to extract or "scrape" data from public web pages. [Web scraping made easy](https://www.thedataschool.co.uk/anna-prosvetova/web-scraping-made-easy-import-html-tables-or-lists-using-google-sheets-and-excel "Web scraping made easy") introduces how to do this with Google Sheets or Microsoft Excel.

### **Google Sheets**
In Google Sheets, you can use the **IMPORTHTML** function. It enables you to import the data from an HTML table (or list) on a web page.
Refer to the Google Help Center's [IMPORTHTML](https://support.google.com/docs/answer/3093339?hl=en "IMPORTHTML") page for more information about the syntax. If you are importing a list, replace "table" with "list" in the above example. The number 4 is the index that refers to the order of the tables on a web page. It is like a pointer indicating which table on the page you want to import the data from.

### **Microsoft Excel**
You can import data from web pages using the **From Web** option:
**Step 1:** Open a new or existing spreadsheet.
**Step 2:** Click Data in the main menu and select the **From Web** option.
**Step 3:** Enter the URL and click OK.
**Step 4:** In the Navigator, select which table to import.
**Step 5:** Click **Load** to load the data from the table into your spreadsheet.
If these directions do not work for the version of Excel that you have. Visit this free online training center, [Microsoft Excel for Windows Training](https://support.microsoft.com/en-us/office/excel-video-training-9bc05390-e94c-46af-a5b3-d7c22f6990bb "Microsoft Excel for Windows Training"), you will find everything you need to know, all in one place.
If you are using Numbers, search the [Numbers User Guide](https://support.apple.com/guide/numbers/welcome/mac "Numbers Uswer Guide") for directions.