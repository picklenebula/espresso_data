# This file will catalogue and list the methodology and process of transforming the data from an unstructed text file into a comme delimited file for upload. 

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
