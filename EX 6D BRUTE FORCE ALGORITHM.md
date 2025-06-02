# EX 6D BRUTE FORCE ALGORITHM
## DATE:
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.




## Algorithm
1. Compile the regular expression pattern from the input string str2.
2. Search for the first occurrence of the pattern in str1.
3. While a match is found, print the starting index of the match.
4. Continue searching from the next index after the last found match.
5. Stop when no further matches are found.
## Program:
```
/*
To implement the program using brute force method of searching for the given substring in the main string.


Developed by: D Vergin Jenifer
Register Number: 212223240174
import re #Import this package
def match(str1,str2):
    pattern = re.compile(str2)
    r = pattern.search(str1)
    while r:
        print("Found at index {}".format(r.start()))
        r = pattern.search(str1,r.start() + 1)
str1=input()
str2=input()

*/
```

## Output:

![image](https://github.com/user-attachments/assets/27541d5d-1cbe-459e-a045-95b29b0dde75)


## Result:
Thus the above program was executed successfully for searching the substring at respective index.
