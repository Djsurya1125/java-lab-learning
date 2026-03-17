# Ex.No.3 Count Lines, Words, Characters

## Ex.No.3 Count Lines, Words, Characters

```java
import java.util.*; // Imports Scanner and utility classes

class Count {
    public static void main(String[] args) { // main() is the starting method of the program
        // Easy analogy:
        // Think this like a notebook checker.
        // It counts how many lines you wrote, how many words are in those lines,
        // and how many characters are present (with and without spaces).

        // Why output looks like that:
        // Every line increases counters, until user types "exit".
        Scanner s = new Scanner(System.in); // Reads text input from keyboard

        int lines = 0;              // Counts total lines entered
        int wordsCount = 0;         // Counts total words
        int charsWithSpaces = 0;    // Counts all characters including spaces
        int charsWithoutSpaces = 0; // Counts characters after removing spaces

        System.out.println("Enter text line by line.");
        System.out.println("Type 'exit' to stop and see the result.");

        while (true) { // Loop keeps taking lines until stop word is entered
            String line = s.nextLine(); // Read one full line

            if (line.equalsIgnoreCase("exit")) { // Condition: stop when user types exit
                break; // exit word is not included in count
            }

            lines++; // One valid line processed
            charsWithSpaces += line.length(); // Add full line length
            charsWithoutSpaces += line.replace(" ", "").length(); // Remove spaces and count

            // Explanation: trim() removes spaces at start/end; split("\\s+") cuts string at spaces
            // Example: "Java is easy" becomes ["Java", "is", "easy"] (3 separate words in array)
            String[] words = line.trim().isEmpty() ? new String[0] : line.trim().split("\\s+");
            wordsCount += words.length; // Add count of words from current line
        }

        System.out.println("Lines: " + lines); // Final line count
        System.out.println("Words: " + wordsCount); // Final word count
        System.out.println("Chars (with spaces): " + charsWithSpaces); // Total chars with spaces
        System.out.println("Chars (without spaces): " + charsWithoutSpaces); // Total chars without spaces

        s.close(); // Good practice: close Scanner resource
    }
}
```

### Variables Used (Easy Meaning)
- `lines`: Stores how many lines user entered.
- `wordsCount`: Stores total words from all lines.
- `charsWithSpaces`: Stores character count including spaces.
- `charsWithoutSpaces`: Stores character count after removing spaces.
- `line`: Stores one line typed by user.
- `words`: Stores words of one line in array form.
- `s`: Scanner object to read user input.

Simple understanding:
- Program reads one line at a time.
- If line is `exit`, reading stops.
- Otherwise, all counters are updated.
- At the end, all totals are printed.

### Input Structure (How to Enter)
```text
Step 1: Type text lines (one line at a time)
Step 2: Type more lines if needed
Step 3: Type exit

Important:
- "exit" is only a stop word.
- "exit" line is NOT counted in output.
```

### Sample Input / Output
```text
Sample Input (categorized):

Line 1:
Java is easy

Line 2:
I am learning loops

Stop word:
exit

Sample Output:
Lines: 2
Words: 7
Chars (with spaces): 31
Chars (without spaces): 25
```

### Actual Input (Raw Console)
```text
Java is easy
I am learning loops
exit
```

### Actual Output (Raw Console)
```text
Lines: 2
Words: 7
Chars (with spaces): 31
Chars (without spaces): 25
```

### Output Explanation (Easy)
- `Lines: 2` because two normal lines were entered before `exit`.
- `Words: 7` because line 1 has 3 words and line 2 has 4 words.
- `Chars (with spaces): 31` includes letters and spaces in both lines.
- `Chars (without spaces): 25` removes spaces before counting.

---

