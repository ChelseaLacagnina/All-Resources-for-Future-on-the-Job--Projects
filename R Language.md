Importing Data
	[Data Import chapter](https://r4ds.had.co.nz/data-import.html "This link takes you to the Data Import chapter of the R for Data Science book.")
	[The R Datasets Package](https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/00Index.html "This link takes you to a list of the datasets in the R datasets pacakge.") 
	http://statseducation.com/Introduction-to-R/modules/getting%20data/import_data/

R Studio
	R Studio Cloud
		https://posit.cloud/content/5568667
	Open Source Editor Pane (top left)
		File->New File -> R Script
	Keyboard Shortcuts
		Tools->Keyboard Shortcuts Help
	Console
		Where you give commands to R
	--You can import data from Spreadsheets
	--Save your Script in the Editor
	--You only need to install a package once, but you need to reload it every time you start a new session.
	R Textbook
		https://lgatto.github.io/2017_11_09_Rcourse_Jena/before-we-start.html

[Dates and times with lubridate: Cheat Sheet](https://rawgit.com/rstudio/cheatsheets/master/lubridate.pdf "This link takes you to an online cheat sheet for using lubridate to work with dates and times."): This “cheat sheet” gives you a detailed map of all the different things you can do with the lubridate package.

**data.frame()** function - To manually create a data frame in R.
	In the parentheses, enter the name of the column, followed by an equals sign, and then the vector you want to input for that column.
		Example: data.frame(x = c(1, 2, 3) , y = c(1.5, 5.5, 7.5))
		Create a data frame
			https://www.coursera.org/learn/data-analysis-r/quiz/h4kqH/hands-on-activity-create-your-own-data-frame

Loading Data from preloaded datasets
	data()
		You can also display the dataset by clicking directly on the name of the dataset in the Environment pane.
Viewing Data
	head() function - Use this to preview the data in a dataset
	str() and glimpse() functions - Both return summaries of each column in your data arranged horizontally.
		Str() - highlights the structure of the data frame. 
			Column names and the type of data in those columns
	colnames() function - Returns a list of column names from a dataset.
	mutate() function - makes changes to the data frame. Comes from the dplyr package.
		library(tidyverse) -> mutate(data frame we want to change, new column name=what goes into the new column)
	seperate() - seperate information from multiple columns
	unite() - combine information from multiple columns
Cleaning Data
	rename() function - to rename columns.
	summarize() function - To generate a wide range of summary statistics.
Visualizing Data
	ggplot2 - A common visualization package.
		To build a visualization with `ggplot2` you layer plot elements together with a `+` symbol.
			Example: ggplot(data = diamonds, aes(x = carat, y = price)) +
  geom_point()
	  facet_wrap() function - create a different plot for each type of one variable
			  Example: ggplot(data = diamonds, aes(x = carat, y = price, color = cut)) + geom_point() + facet_wrap(~cut)
Documentation
	R markdown - Allows you to put code and writing in the same place.
	Knit - When you have written, executed, and documented your code in an `R markdown` document, you can use the `knit` button in the menu bar at the top of the editing pane to export your work to a readable document. 

**R documentation** is a tool that helps you easily find and browse the documentation of almost all R packages on CRAN.
	--Check out [R documentation: files](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/files)
	**dir.create** function - to create a new folder, or directory, to hold your files.
			Example: dir.create ("destination_folder")
	**file.create()** function - to create a blank file.
		Place the name and the type of the file in the parentheses of the function.
			Example: file.create (“new_text_file.txt”)
		--If the file is successfully created when you run the function, R will return a value of TRUE (if not, R will return FALSE)
	**file.copy()** function - Copying a file.
		In the parentheses, add the name of the file to be copied. Then, type a comma, and add the name of the destination folder that you want to copy the file to.
			Example: file.copy (“new_text_file.txt” , “destination_folder”)
	**unlink()** function - Delete R files
		Enter the file’s name in the parentheses of the function.
			Example: 
			unlink (“some_.file.csv”)
	Matrices - two-dimensional collection of data elements
		**matrix()** function - To create a matrix in R.
		In the parentheses, add a vector and add at least one matrix dimension.
			You can choose to specify the number of rows or the number of columns by using the code nrow = or ncol =.

R Packages
	[**Tidyverse**](https://www.tidyverse.org/ "This link takes you to the Tidyverse home page.") - A standard library for most data analysts.
		8 Core Tidyverse packages:
			1. ggplot2 - Used for data visualization (plots). 
				Create a variaty of data viz by applying different visual properties to the data variables in R
			2. tidyr - A package used for data cleaning to make tidy data.
				Wide to long format.
				[**Pivoting**](https://tidyr.tidyverse.org/articles/pivot.html "This link takes you to the tidyr documentation for the pivot_longer and pivot_wider functions.") 
			1. readr - Used for importing data.
				The readr package in R is a great tool for reading rectangular data.
					.csv, .tsv, .fwf, .log, etc.
						-   read_csv(): comma-separated values (.csv) files
						-   read_tsv(): tab-separated values files
						-   read_delim(): general delimited files
						-   read_fwf(): fixed-width files
						-   read_table(): tabular files where columns are separated by white-space
						-   read_log(): web log files
				To import spreadsheet data into R, you can use the readxl package.
			4. dplyr - Offers a consistent set of functions that help you complete some common data manipulation tasks.
				Select and Filtering.
			5. tibble - Streamlined data frames that automatically set to pull up only the first 10 rows of a dataset, and only as many columns as can fit on the screen.
					 Never change the data types of the inputs.
					 Never change the names of your variables.
					 Never create row names.
					 Make printing easier.
				 as_tibble() function - create a tibble from existing data
					 [Tibble](https://tibble.tidyverse.org/ "This link takes you to the Tibble section of the Tidyverse documentation.") and [Tidy chapter](https://rstudio-education.github.io/tidyverse-cookbook/tidy.html# "This link takes you to the Tidy chapter in "A Tidyverse Cookbook."") 
			6. purrr - Works with functions and vectors to make code easier to write.
			7. stringr - Functions that make it easier to work with strings.
			8. forcats - Provides tools that solve common problems with factors.
				Factors store categorical data in R where the data values are limited.
	[**Quick list of useful R packages**](https://support.rstudio.com/hc/en-us/articles/201057987-Quick-list-of-useful-R-packages "This link takes you to a list of R packages recommended by RStudio Support.") - RStudio Support’s list of useful packages with installation instructions and functionality descriptions. 
     [**CRAN Task Views**](https://cran.r-project.org/web/views/ "This link takes you to a list of packages on CRAN by topic or task in alphabetical order.") - An index of CRAN packages sorted by task.

browseVignettes("packagename") function
	To read through vignettes of a loaded package.

Pipes (R) - A tool in R for expressing a sequence of multiple operations, represented with "%>%"
		Add the pipe operator at the end of each line of the piped operation except the last one.
		Check your code after you've programmed your pipe.
		Revisit piped operations to check for parts of your code to fix.

Operators
	[R Operators](https://r-coder.com/operators-r/#Assignment_operators_in_R "This link takes you to the Assignment Operators in R section of the R Operators guide from R Coder.")

Packages
	here - makes referencing files easier.
		load before saving csv. files
	skimr - makes summarizing data easy and lets you skim through it.
	janitor - functions for cleaning data.

Addressing Biases
	sample() function - allows you to take a random sample of elements from a data set.
	[**Bias function****:**](https://www.rdocumentation.org/packages/SimDesign/versions/2.2/topics/bias "This link takes you to RDocumentation's description and examples of using the bias function.")

Create a plot in ggplot2
	Visualizing
		https://www.coursera.org/learn/data-analysis-r/quiz/fmyHH/hands-on-activity-visualizing-data-with-ggplot2/attempt
		ggplot2 [Cheat Sheet](https://ggplot2.tidyverse.org/)
	Aesthetic attributes
		https://www.coursera.org/learn/data-analysis-r/supplement/jvaYe/aesthetic-attributes
		[**Data visualization with ggplot2 cheat sheet**](https://ggplot2.tidyverse.org/)
	

See [[Common Problems Visualizing in R.pdf]]

Adding Annotations
	[**Create an annotation layer**](https://ggplot2.tidyverse.org/reference/annotate.html "This link takes you to the tidyverse ggplot2 documentation on creating an annotation layer.")
	[**How to annotate a plot in ggplot2**](https://www.r-graph-gallery.com/233-add-annotations-on-ggplot2-chart.html "This link takes you to the R Graph Gallery's instructions to annotate a plot in ggplot2.")**:**
	[**Annotations**](https://ggplot2-book.org/annotations.html "This link takes you to Chapter 8: Annotations in a ggplot2 book.")**:**
	[**How to annotate a plot**](https://www.r-bloggers.com/2017/02/how-to-annotate-a-plot-in-ggplot2/ "This link takes you to an R-Bloggers post on how to annotate a plot.")**:**
	[**Text Annotations**](https://viz-ggplot2.rsquaredacademy.com/textann.html "This link takes you to Chapter 5: Text Annotations in the Data Visualization with ggplot2 book.")**:**


Saving images without ggsave()
	**png()** or **pdf()**
		[**Saving images without ggsave()**](https://ggplot2.tidyverse.org/reference/ggsave.html#saving-images-without-ggsave- "This link takes you to tidyverse's ggplot2 documentation on saving images without ggsave().")
		[**How to save a ggplot**](https://www.datanovia.com/en/blog/how-to-save-a-ggplot/ "This link takes you to Data Novia's blog on how to save a ggplot.")
		[**Saving a plot in R:**](https://www.datamentor.io/r-programming/saving-plot/ "This link takes you to Data Mentor's article on how to save a plot as a bitmap, vector image, PDF, or PostScript file.")






