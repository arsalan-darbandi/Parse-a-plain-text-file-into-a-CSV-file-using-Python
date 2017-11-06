# Parse-a-plain-text-file-into-a-CSV-file-using-Python
I wrote a code that is selecting data from paragraphs in text file and extract them and save them as CSV file. 
I used jupyter because of that it doesn't have function. 

You could find either my python file or jupyter file with the text file. 

open and read the txt file.
```
text_file = open("Name_of_File.txt", "r") # Multi is name of my file and Name_of_File.txt must be in the same folder otherwise you have to write the direction of specific file. 
```
Read each line of text file and save it in lines. 
```
lines = text_file.readlines()
```
Print lines.
```
print len(lines)
text_file.close()
```
To read CSV and write CSV file you have to import csv library.  
```
import csv
```
Make a csv file.
```
mycsv = csv.writer(open('OutPut.csv', 'wb'))
```
Write header for csv file.
```
mycsv.writerow(['year', 'month', 'date', 'hour', 'minute', 'second'])
```
This is a function that works in this way that:
Text file is reading each line and find where it has "2016"
Then it is finding other parameters for that date. 
Spliting Date as year, month, day and other parameteres. 
```
n = 0
for line in lines: 
    n = n + 1
    if "2016" in line:
        if "[" in line:
            date_time = line.split("[")[0]
            year = date_time.split(" ")[0]
            month = date_time.split(" ")[1]
            day = date_time.split("  ")[1]
            time = date_time.split("  ")[2]
            hour = time.split(":")[0]
            minute = time.split(":")[1]
            second = time.split(":")[2]
```
At the end we save all information for that specific date and then going for other date.             
```
mycsv.writerow([year, month, day, hour, minute, second])
```

Recently, I've faced with another example that I used this method. This example, I wanted to change the format of all files from jpeg to jpg.
```
import os
path = '/Users/asikhalaban/Downloads/phone/New' # Define the directery that all files are in. 
files = os.listdir(path)
i = 1

for file in files:
    filename = file.split(".")[0] # Split name of a file based on "." and select first part.
    os.rename(os.path.join(path, file), os.path.join(path, filename +'.jpg')) # Here rename it the selected name.
```
