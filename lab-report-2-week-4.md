# Lab Report Week 4

## First Correction: Allowing Parenthesis when parsing Links

![Image](https://github.com/astoriama/cse15l-lab-reports/raw/main/CorrectionLink1.png)

Test that results in an unexpected output : [link](https://github.com/astoriama/markdown-parser/commit/d0a6a357b7a569e9424167a06e03bda0c65eb455)

The symptom that the failure inducing input results in is 

``` 
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
        at java.base/java.util.Arrays.copyOfRange(Arrays.java:3822)
        at java.base/java.lang.StringLatin1.newString(StringLatin1.java:769)
        at java.base/java.lang.String.substring(String.java:2709)
        at MarkdownParse.getLinks(MarkdownParse.java:19)
        at MarkdownParse.main(MarkdownParse.java:30)
```
When parsing through the code that contains the link, the parsing program causes an error because it counts the parenthesis within the link thinking that it is actually the parenthesis from the code. The reason for this is because there are two parenthesis within the test input, and the code thinks that after the two parenthesis from the link, that open brackets are next, since this is not the case with the test input the program breaks. 

## Second Correction: Parsing through other code elements 

![Image](https://github.com/astoriama/cse15l-lab-reports/raw/main/CorrectionLink2.1.png)

Test that results in an unexpected output : [link](https://github.com/astoriama/markdown-parser/commit/faa8431f04f6e5f6b86c51881fa1e35b2cb7ac09)

The symptom that the failure inducing input results in is 

```
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
        at java.base/java.util.Arrays.copyOf(Arrays.java:3512)
        at java.base/java.util.Arrays.copyOf(Arrays.java:3481)
        at java.base/java.util.ArrayList.grow(ArrayList.java:237)
        at java.base/java.util.ArrayList.grow(ArrayList.java:244)
        at java.base/java.util.ArrayList.add(ArrayList.java:454)
        at java.base/java.util.ArrayList.add(ArrayList.java:467)
        at MarkdownParse.getLinks(MarkdownParse.java:43)
        at MarkdownParse.main(MarkdownParse.java:58)
```

Within the 8 test files we are given, some of them have other markdown code before or after the code for the links. For example: with the old code, the parser would continue parsing through code that contained partial code for links, and this would cause an infinite loop therefore causing an out of memory error.

## Third Correction: Allowing Parenthesis in Link Titles

![Image](https://github.com/astoriama/cse15l-lab-reports/raw/main/CorrectionLink3.png)

Test that results in an unexpected output : [link](https://github.com/astoriama/markdown-parser/commit/6e9b08eba085109f2ffdbadc5075d8ded5b3a2c5)

Symptom of the failure inducing input is:   
```(base) astoria@Astorias-MacBook-Pro markdown-parser % javac MarkdownParse.java
(base) astoria@Astorias-MacBook-Pro markdown-parser % java MarkdownParse test-file3.md
[hi, hi.com]
```
The correct output should be:   
`[hi.com, hi.com]`  

When there are parenthesis within the brackets for the link title, the parsing algorithm does not work as expected. The program breaks and ends up using the parenthesis from the link title for the parsing algorithm which causes a different output than the expected one since it ended the search for a link early and moved on to the next link prematurely.  




