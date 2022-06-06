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
![image](https://github.com/astoriama/cse15l-lab-reports/blob/main/compare488.png)
The implementation given to us in class was wrong while my groups was correct. The reasons why the parser given to us in class is wrong is because it doesnt take into account spaces and basically resets the search at blank spaces. The code that should be modified is in line 75-78.
![image](https://github.com/mstubbs1/cse15l-lab-reports/blob/main/488fix.jpg?raw=true)