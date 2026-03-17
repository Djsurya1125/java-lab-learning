# Ex.No.5 String Manipulation using Char Array

## Ex.No.5 String Manipulation using Char Array

```java
import java.util.*; // Imports Scanner class

class StringCal {
    public static void main(String[] args) { // main() is the starting method of the program
        // Easy analogy:
        // Think a word is a row of small letter boxes.
        // Each box has a position number (index), starting from 0.
        // We can count boxes, pick one box, and join one more word.

        Scanner s = new Scanner(System.in); // Reads input from keyboard

        String str = s.nextLine(); // Reads first string
        char[] arr = str.toCharArray(); // Converts string into character array

        System.out.println(arr.length); // Prints number of characters in first string

        int position = s.nextInt(); // Reads index position to pick one character
        char x = arr[position]; // Gets character at that index
        System.out.println(x); // Example: in "hello", index 1 gives 'e'

        s.nextLine(); // Consumes leftover newline after nextInt input
        String s2 = s.nextLine(); // Reads second string
        String concat = str + s2; // Joins first and second string
        System.out.println(concat); // Prints final joined string

        s.close(); // Good practice: close Scanner resource
    }
}
```

### Variables Used (Easy Meaning)
- `str`: Stores first string entered by user.
- `arr`: Stores all characters of `str` in array form.
- `position`: Stores index number entered by user.
- `x`: Stores one character taken from array at given index.
- `s2`: Stores second string entered by user.
- `concat`: Stores joined result of first and second string.
- `s`: Scanner object to read input.

### Simple understanding
- Program reads one string and changes it into character array.
- It prints total number of characters.
- It prints one character from the position you give.
- Then it joins first string with second string and prints result.

### Input Structure (How to Enter)
```text
Step 1: Enter first string

Step 2: Enter index position (starts from 0)

Step 3: Enter second string

Important:
- If first string is `hello`, valid index values are 0 to 4
- If you give invalid index (like 9), Java will show index error
```

### Sample Input / Output
```text
Sample Input (categorized):

First string:
hello

Index position:
1

Second string:
world

Sample Output:
5
e
helloworld
```

### Actual Input (Raw Console)
```text
hello
1
world
```

### Actual Output (Raw Console)
```text
5
e
helloworld
```

### Output Explanation (Easy)
- `5` means first string `hello` has 5 characters.
- `e` comes from index `1` in `hello` (h=0, e=1).
- `helloworld` is the joined result of `hello` + `world`.
- No extra space appears because we joined directly.

---
