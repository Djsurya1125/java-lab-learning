# Ex.No.10 Exception Handling

## Ex.No.10 Exception Handling

```java
import java.util.*; // Imports Scanner and utility classes

class EXNO10 {
    public static void main(String[] args) { // main() is the starting method
        // Easy analogy:
        // Think try-catch like a safety helmet.
        // If an error happens, catch block protects program and shows clear message.

        Scanner s = new Scanner(System.in); // Reads input from keyboard
        int[] arr1 = {25, 30, 15}; // Small array for index exception demo
        boolean running = true; // Controls menu loop

        while (running) { // Repeats until user chooses exit
            System.out.println("1.Arithmetic 2.NumberFormat 3.ArrayIndex 4.NegativeArray 5.Exit");
            int ch = s.nextInt(); // Reads menu choice

            try { // Risky code goes inside try
                switch (ch) {
                    case 1:
                        int n3 = 4 / 0; // ArithmeticException: divide by zero
                        System.out.println(n3);
                        break;
                    case 2:
                        int d = Integer.parseInt("12x"); // NumberFormatException
                        System.out.println(d);
                        break;
                    case 3:
                        for (int i = 1; i <= 3; i++) { // i=3 causes ArrayIndexOutOfBounds
                            System.out.println(arr1[i]);
                        }
                        break;
                    case 4:
                        int size = s.nextInt(); // Reads requested array size
                        int[] arr2 = new int[size]; // Negative value causes NegativeArraySizeException
                        System.out.println(arr2.length);
                        break;
                    case 5:
                        running = false; // Exit loop
                        break;
                    default:
                        System.out.println("Invalid choice"); // Handles wrong menu choice
                }
            } catch (ArithmeticException e) {
                System.out.println("Cannot divide by zero"); // Message for case 1
            } catch (NumberFormatException e) {
                System.out.println("Invalid number format"); // Message for case 2
            } catch (ArrayIndexOutOfBoundsException e) {
                System.out.println("Invalid array index"); // Message for case 3
            } catch (NegativeArraySizeException e) {
                System.out.println("Negative array size not allowed"); // Message for case 4
            }
        }

        s.close(); // Good practice: close Scanner resource
    }
}
```

### Variables Used (Easy Meaning)
- `s`: Scanner object to read user input.
- `arr1`: Fixed array used for index exception example.
- `running`: Controls whether menu keeps running.
- `ch`: Stores user menu choice.
- `n3`: Variable for divide-by-zero demo.
- `d`: Variable for number-format demo.
- `size`: User input for new array size.
- `arr2`: Array used for negative-size demo.
- `i`: Loop counter in array-index demo.

### Simple understanding
- Program shows menu for 4 exception demos and exit.
- User picks one option.
- Risky code runs inside try block.
- If error occurs, matching catch block prints simple message.

### Input Structure (How to Enter)
```text
Step 1: Enter menu choice
- 1: ArithmeticException
- 2: NumberFormatException
- 3: ArrayIndexOutOfBoundsException
- 4: NegativeArraySizeException (then enter array size)
- 5: Exit

Important:
- Only choice 4 needs one extra number input
- Program continues until choice 5
```

### Sample Input / Output
```text
Sample Input (categorized):

Choice:
1

Choice:
5

Sample Output:
Cannot divide by zero
```

### Actual Input (Raw Console)
```text
1
5
```

### Actual Output (Raw Console)
```text
Cannot divide by zero
```

### Output Explanation (Easy)
- Choice `1` tries `4/0`, so arithmetic error happens.
- Catch block handles it and prints `Cannot divide by zero`.
- Choice `5` exits the menu loop.

---
