# Suggestions to improve the code for the findNeedles() method

The following are some suggestions to improve the code for the `findNeedles()` method:
- The code can be updated with consistent indentation and formatting.
  
  The following is a sample of the modified code with consistent indentation and formatting.
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

- In the given code, the input text passed in the `haystack` parameter is repeatedly split inside a nested loop, which can result in memory usage issues. If the code is modified to split the haystack string once and then iterate through the `words`, then the memory usage issues are resolved.
- The code can be modified to handle the case-insensitive matching between words and needles.
- The code can be modified to handle the punctuation and non-alphanumeric characters effectively.

