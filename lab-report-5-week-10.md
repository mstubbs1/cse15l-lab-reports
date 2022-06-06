# Lab Report 5 Week 10

## Finding tests with different results

To compare tests from my version of markdown parse and the implementation provided I used the bash script and vimdiff.
The script I used :
```
for file in test-files/*.md;
do
  echo $file
  java MarkdownParse $file
done
```
Ran command : `bash script.sh > results.txt` in both repositories, and used the command `vimdiff /Users/migue/Documents/GitHub/markdown-parser/results.txt /Users/migue/Documents/GitHub/markdown-parser2/results.txt`

## Test 488

[Link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/488.md) to the test file
![image](https://github.com/astoriama/cse15l-lab-reports/raw/main/preview488.png) 
The preview only shows "link", therefore the parser should return `[</my uri>]`.  
![image](https://github.com/astoriama/cse15l-lab-reports/raw/main/compare488.png)  
The implementation given to us in class was wrong while my groups was correct. The reasons why the parser given to us in class is wrong is because it doesnt take into account spaces and basically resets the search at blank spaces. The code that should be modified is in line 75-78.
![image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/488fix.jpg?raw=true)

# Test 489

[Link](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/489.md) to the test file.
![image](https://github.com/astoriama/cse15l-lab-reports/raw/main/preview489.png)  
The preview basically prints out the code because there is a space in between lines, therfore the parser should return `[]`.  
![image](https://github.com/astoriama/cse15l-lab-reports/raw/main/compare489.png)
The implemenation given to us in class was right while the implementation my group and I created was incorrect. The main issue with our implementation was that it does not take into account line breaks. Therefore, a fix that can be added to the code is to take into account `\n` which is a line break ; if the parsers sees a new line it should then go to the next index and not take the new line into account when parsing links. 