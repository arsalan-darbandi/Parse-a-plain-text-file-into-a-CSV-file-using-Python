# Parse-a-plain-text-file-into-a-CSV-file-using-Python
I wrote a code that is selecting data from paragraphs in text file and extract them and save them as CSV file. 
I used jupyter because of that it doesn't have function. 

## You could find either my python file or jupyter file with the text file. 

open and read the txt file.
```
text_file = open("Multi.txt", "r") # Multi is name of my file and Multi.txt must be in the same folder otherwise you have to write the direction of specific file. 
```

Read each line of text file and save it in lines. 
```
lines = text_file.readlines()
```

Print lines
```
print len(lines)
text_file.close()
```

To read CSV and write CSV file you have to import csv library.  
```
import csv
```
