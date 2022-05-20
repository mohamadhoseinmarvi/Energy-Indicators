# Energy-Indicators
#Created By Hosein Marvi

Assignment proposed by the Applied Data Science with Python course  in Coursera.
Data cleaning with Pandas, merging three files and answering some questions.

*Excel file Energy Indicators.xls, which contain a list of indicators of energy supply and renewable electricity production from the United Nations for the year 2013.

##### Data Cleaning Tasks - Energy:

1. Load the data. Keep in mind that this is an Excel file, and not a comma separated values file. Also, make sure to exclude the footer and header information from the datafile. The first two columns are unneccessary, so you should get rid of them, and you should change the column labels so that the columns are:
['Country', 'Energy Supply', 'Energy Supply per Capita', '% Renewable']

2. Convert Energy Supply to gigajoules (there are 1,000,000 gigajoules in a petajoule). 

3. For all countries which have missing data (e.g. data with "...") make sure this is reflected as np.NaN values.

4. There are also several countries with numbers and/or parenthesis in their name. Be sure to remove these, 

   e.g. Bolivia (Plurinational State of) should be 'Bolivia' 
       'Switzerland17' should be 'Switzerland'
       
5. Rename the following list of countries (for use in later questions):

   "United States of America": "United States",
   "United Kingdom of Great Britain and Northern Ireland": "United Kingdom",
   "China, Hong Kong Special Administrative Region": "Hong Kong"   

*World_bank.csv is a csv containing countries GDP from 1960 to 2015 from [World Bank](http://data.worldbank.org/indicator/NY.GDP.MKTP.CD).

##### Data Cleaning Tasks - GDP:
1. Load the GDP data. Make sure to skip the header.
2. Rename the following list of countries:
   "Korea, Rep.": "South Korea", 
   "Iran, Islamic Rep.": "Iran",
   "Hong Kong SAR, China": "Hong Kong"

*[Sciamgo Journal and Country Rank data for Energy Engineering and Power Technology](http://www.scimagojr.com/countryrank.php?category=2102) from the file `scimagojr-3.xlsx`,  ranks countries based on their journal contributions in the aforementioned area. 

##### Data Cleaning Tasks - ScimEn:
1. Load de data. Call this DataFrame **ScimEn**.
2. Join the three datasets: GDP, Energy, and ScimEn into a new dataset (using the intersection of country names). Use only the last 10 years (2006-2015) of GDP data and only the    top 15 countries by Scimagojr 'Rank' (Rank 1 through 15). 

   The index of this DataFrame should be the name of the country, and the columns should be ['Rank', 'Documents', 'Citable documents', 'Citations', 'Self-citations',
       'Citations per document', 'H index', 'Energy Supply',
       'Energy Supply per Capita', '% Renewable', '2006', '2007', '2008',
       '2009', '2010', '2011', '2012', '2013', '2014', '2015'].
       
       
### Questions

1. The previous step joined three datasets then reduced this to just the top 15 entries. When you joined the datasets, but before you reduced this to the top 15 items, how many 
   entries did you lose?
2. What is the average GDP over the last 10 years for each country? (exclude missing values from this calculation.)
3. By how much had the GDP changed over the 10 year span for the country with the 6th largest average GDP?
4. What is the mean Energy Supply per Capita?
5. What country has the maximum % Renewable and what is the percentage?
6. Create a new column that is the ratio of Self-Citations to Total Citations. What is the maximum value for this new column, and what country has the highest ratio?
7. Create a column that estimates the population using Energy Supply and Energy Supply per capita. What is the third most populous country according to this estimate?
8. Create a column that estimates the number of citable documents per person. What is the correlation between the number of citable documents per capita and the energy supply 
   per capita? Use the .corr() method, (Pearson's correlation).
9. Use the built-in function plot() to visualize the relationship between Energy Supply per Capita vs. Citable docs per Capita
10. Create a new column with a 1 if the country's % Renewable value is at or above the median for all countries in the top 15, and a 0 if the country's % Renewable value is 
    below the median.
11. Use the following dictionary to group the Countries by Continent, then create a dateframe that displays the sample size (the number of countries in each continent bin), and 
    the sum, mean, and std deviation for the estimated population of each country.

    ContinentDict  = {'China':'Asia', 
                  'United States':'North America', 
                  'Japan':'Asia', 
                  'United Kingdom':'Europe', 
                  'Russian Federation':'Europe', 
                  'Canada':'North America', 
                  'Germany':'Europe', 
                  'India':'Asia',
                  'France':'Europe', 
                  'South Korea':'Asia', 
                  'Italy':'Europe', 
                  'Spain':'Europe', 
                  'Iran':'Asia',
                  'Australia':'Australia', 
                  'Brazil':'South America'}
12. Cut % Renewable into 5 bins. Group Top15 by the Continent, as well as these new % Renewable bins. How many countries are in each of these groups?
13. Convert the Population Estimate series to a string with thousands separator (using commas). Do not round the results.
    e.g. 317615384.61538464 -> 317,615,384.61538464
14. Use the built in function plot to make an example visualization.
