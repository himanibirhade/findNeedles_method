# findNeedles() method

## Overview

The `findNeedles` method searches for occurrences of arguments within an input text. It counts the occurrences of each argument from the given array within the input text and provides a count for each argument.

This method uses a split function to separate the input string data using the following special characters:

| Special Character | Description |
|-------------------|-------------|
| `\"` | double quotes character |
| `\'` | single quotes character |
| `\t` | tab space character |
| `\n` | new line character |
| `\b` | backspace character |
| `\f` | form feed character |
| `\r` | carriage return character |

## Signature

**public static void findNeedles(String haystack, String[] needles)**

## Code

```
public static void findNeedles(String haystack, String[] needles) {
        if (needles.length > 5) {
                System.err.println("Too many words!");
        } else {
                int[] countArray = new int[needles.length];
                for (int i = 0; i < needles.length; i++) {
                        String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);
                        for (int j = 0; j < words.length; j++) {
                                if (words[j].compareTo(needles[i]) == 0) {
                                        countArray[i]++;
                                }
                        }
                }
                for (int j = 0; j < needles.length; j++) {
                        System.out.println(needles[j] + ": " + countArray[j]);
                }
        }
}

```

## Parameters

The following parameters are required to call the `findNeedles` method:

| Parameter | Type | Description |
|-----------|------|-------------|
| `haystack` | String | Input data in string format in which the argument(s) are to be searched |
| `needles` | String[] | Input data in the form of a string array to be searched in the `haystack` parameter |

## Returns

The `findNeedles` method does not return any value.

The following results are obtained after calling the `findNeedles` method:
- If the length of the needles array is less than five, then the `findNeedles` method prints the following output:
  - needles[0]: number of occurrences
  - needles[1]: number of occurrences
  - needles[2]: number of occurrences
  - needles[3]: number of occurrences
- If the length of the needles array is greater than or equal to five, then the `findNeedles` method prints the following output.

  `Too many words!`
  
## Calling the findNeedles method

The following is a sample for calling the `findNeedles` method using the `haystack` and the `needles` parameters.

```
String haystack = "Hello, my name is Himani! Nice to meet you.";
String[] needles = {"my", "meet", "you"};
findNeedles(haystack, needles);
```

## Test Cases

The following are the various test cases performed with the `findNeedles` method.

### Test Case 1

```
String haystack = "Hello, my name is Himani! Nice to meet you.";
String[] needles = {"my", "Jane", "you."};
findNeedles(haystack, needles);
```
  **Output**

  ```
  my: 1
  Jane: 0
  you.: 1
  ```

### Test Case 2

```
String haystack = "Hello, my name is Himani! Nice to meet you.";
String[] needles = {"Hello,", "meet", "you"};
findNeedles(haystack, needles);
```
 **Output**

  ```
  Hello,: 1
  meet: 1
  you: 0
  ```

### Test Case 3

```
String haystack = "Hello, my name is Himani! Nice to meet you.";
String[] needles = {"Hello,", "meet", "you", "please", "Jack", "Jane"};
findNeedles(haystack, needles);
```
 **Output**

  ```
  Too many words!
  ```

### Test Case 4

```
String haystack = "Hello, my name is Himani! Nice to meet you.";
String[] needles = {""};
findNeedles(haystack, needles);
```
 **Output**

No output is displayed

### Test Case 5

```
String haystack = "";
String[] needles = {""};
findNeedles(haystack, needles);
```
 **Output**

No output is displayed

## Limitations

The following are the various limitations of the `findNeedles` method:
- This method accepts less than or equal to four arguments for the `needles` parameter.
- Input arguments are case-sensitive.

  For example, "Hello" and "hello" are recognized as two different words.
- Punctuation in input arguments is recognized as a distinct word.

  For example, "Hello" and "Hello!" are recognized as two different words.
- No output is received when you pass an empty string or empty array while calling the method.
