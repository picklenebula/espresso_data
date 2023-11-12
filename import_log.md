# This file will catalogue and list the methodology and process of transforming the data from an unstructed text file into a comma delimited file for upload. 

### Initial spreadsheet formatting and manual importing of uncleaned data.
>[!NOTE]
>The unstructered data set can be found here: [coffee.txt](https://github.com/picklenebula/espresso_data/blob/main/coffee.txt).

1. Setup of initial column headers.
   ```
   - coffee_company   (name of the producer or distributor name.)
   - coffee_name      (name of the coffee flavour itself.)
   - country_origin   (country of origin where coffee beans were grown.)
   - simone_rating    (personal rating of the barista on a 10 point scale.)
   - column_separate  (place holder column for separating grind setting and extraction once imported from text file.)
   - grind_setting    (grind setting used on REPLACEWITHGRINDERMODEL.)
   - extraction_time  (total extraction time of espresso in seconds integers.)
   - device_used      (espresso machine used to extract espresso.)
   - new_basket       (was the espresso made with the old basket or new basket, boolean, 1 for new, 0 for old.)
   ```
2. Importing data manually because I don't know how to use regular expression whoops.
     - Fill *coffee_company, coffee_name and simone_rating* with values from [coffee.txt](https://github.com/picklenebula/espresso_data/blob/main/coffee.txt).
     - Leave *country_origin, grind_setting, extraction_time, device_used and new_basket* blank.
     - Copy and paste text lines from [coffee.txt](https://github.com/picklenebula/espresso_data/blob/main/coffee.txt) for that coffee flavour into *column_separate*.
     - Autofill *coffee_company, coffee_name and simone_rating* to match the number of rows filled by *column_separate*.
     - Autofill *device_used and new_basket* for all rows except the first which uses the new basket.
>[!IMPORTANT]
>This spreadsheet does not have a primary key as no date/time info or unique identifier is present to differentiate data observations.
---
### Cleaning the data !
1. Prepare the column headers for final version.
   - Remove *column_separate* after copy/paste as values in *column_separate_limit*.
   - Add formula to column *grind_setting* to split text. *=SPLIT(E2," - ")*
   - Copy/paste as values in columns *grind_setting* and *extraction_time* to preserve values.
   - Delete column *column_separate_limit*.
   - Correcting certain invalid *coffee_name* entries for accuracy.  
   - Correcting double decimal points in *grind_setting* because it produces null value in tableau.
>[!NOTE]
> I don't know how to effectively state that a coffee is from multiple countries, ask someone smarter than me.

2. Adding countries of origin to column *country_origin*.
3. Adding new column *country_origin2* for secondary origin countries, tertriery countries not listed.
4. 
