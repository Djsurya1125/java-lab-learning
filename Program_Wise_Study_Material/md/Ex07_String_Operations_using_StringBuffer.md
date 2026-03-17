# Ex.No.7 String Operations using StringBuffer

## Ex.No.7 String Operations using StringBuffer

```java
import java.util.*; // Imports Scanner class

public class StringBufferOps {
    public static void main(String[] args) { // main() is the starting method of the program
        // Easy analogy:
        // Think StringBuffer like soft clay text.
        // We can add, insert, replace, delete, and reverse letters directly.

        Scanner s = new Scanner(System.in); // Reads input from keyboard

        StringBuffer sb1 = new StringBuffer(s.nextLine()); // Reads first editable string
        StringBuffer sb2 = new StringBuffer(s.nextLine()); // Reads second string (used in append)

        int choice; // Stores menu choice
        do {
            choice = s.nextInt(); // Reads operation choice
            s.nextLine(); // Consumes newline after number input

            switch (choice) { // Performs action based on choice
                case 1:
                    sb1.append(sb2); // Adds second string at end of first
                    System.out.println(sb1); // Prints updated string
                    break;
                case 2:
                    String text = s.nextLine(); // Reads text to insert
                    int pos = s.nextInt(); // Reads position for insertion
                    s.nextLine();
                    sb1.insert(pos, text); // Inserts text at given index
                    System.out.println(sb1); // Prints updated string
                    break;
                case 3:
                    String rep = s.nextLine(); // Reads replacement text
                    int a = s.nextInt(); // Start index of replace
                    int b = s.nextInt(); // End index of replace (exclusive)
                    s.nextLine();
                    sb1.replace(a, b, rep); // Replaces selected range with new text
                    System.out.println(sb1); // Prints updated string
                    break;
                case 4:
                    int d1 = s.nextInt(); // Start index of delete
                    int d2 = s.nextInt(); // End index of delete (exclusive)
                    s.nextLine();
                    sb1.delete(d1, d2); // Deletes selected range
                    System.out.println(sb1); // Prints updated shorter string
                    break;
                case 5:
                    sb1.reverse(); // Reverses complete string
                    System.out.println(sb1); // Prints reversed string
                    break;
                case 6:
                    System.out.println("Exit"); // Exit option
                    break;
                default:
                    System.out.println("Invalid choice"); // Handles wrong menu input
            }
        } while (choice != 6);

        s.close(); // Good practice: close Scanner resource
    }
}
```

### Variables Used (Easy Meaning)
- `sb1`: Main editable string.
- `sb2`: Second string used for append operation.
- `choice`: Stores menu choice.
- `text`: Stores text for insert operation.
- `pos`: Stores insert position.
- `rep`: Stores replacement text.
- `a`, `b`: Start and end index for replace.
- `d1`, `d2`: Start and end index for delete.
- `s`: Scanner object to read input.

### Simple understanding
- Program reads two strings first.
- User chooses operation from menu (1 to 6).
- Chosen operation changes `sb1` and prints result.
- Program repeats until user enters `6`.

### Input Structure (How to Enter)
```text
Step 1: Enter first string (sb1)

Step 2: Enter second string (sb2)

Step 3: Enter menu choice
- 1: Append sb2 to sb1
- 2: Insert text (then enter text and position)
- 3: Replace text (then enter replacement text, start, end)
- 4: Delete text (then enter start, end)
- 5: Reverse string
- 6: Exit

Important:
- For choices 2, 3, and 4, extra inputs are required
- Index positions start from 0
```

### Sample Input / Output
```text
Sample Input (categorized):

First string (sb1):
hello

Second string (sb2):
java

Choice 1 (Append):
1

Choice 6 (Exit):
6

Sample Output:
hellojava
Exit
```

### Actual Input (Raw Console)
```text
hello
java
1
6
```

### Actual Output (Raw Console)
```text
hellojava
Exit
```

### Output Explanation (Easy)
- Choice `1` appends `java` to `hello`.
- So output becomes `hellojava`.
- Choice `6` prints `Exit` and loop stops.
- Other operations are not shown because we did not select them in this sample.

---
