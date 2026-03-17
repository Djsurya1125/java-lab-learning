# Ex.No.9 Thread Number Printer

## Ex.No.9 Thread Number Printer

```java
public class ThreadNumberPrinter {
    public static void main(String[] args) { // main() is the starting method
        // Easy analogy:
        // Think two students reading two different number ranges.
        // Both read at the same time, so output lines can mix.

        NumPrint n1 = new NumPrint(1, 10); // First thread prints 1 to 10
        NumPrint n2 = new NumPrint(40, 50); // Second thread prints 40 to 50

        n1.start(); // Starts first thread
        n2.start(); // Starts second thread
    }
}

class NumPrint extends Thread {
    int start; // Starting number of range
    int end; // Ending number of range

    NumPrint(int x, int y) { // Constructor receives range
        start = x;
        end = y;
    }

    public void run() { // run() executes when thread starts
        // Loop prints all numbers from start to end
        for (int i = start; i <= end; i++) {
            System.out.println(i); // Prints current number
            try {
                Thread.sleep(1000); // Waits 1 second between numbers
            } catch (Exception e) {
                System.out.println(e); // Prints exception if any
            }
        }
    }
}
```

### Variables Used (Easy Meaning)
- `n1`: Thread object for range 1 to 10.
- `n2`: Thread object for range 40 to 50.
- `start`: Starting value for one thread.
- `end`: Ending value for one thread.
- `i`: Loop counter used for printing values.

### Simple understanding
- Program creates two threads with two ranges.
- Both threads start together.
- Each thread prints numbers in its own range.
- Because of threading, lines may appear in mixed order.

### Input Structure (How to Enter)
```text
No keyboard input is required.
Ranges are already given in the program.
```

### Sample Input / Output
```text
Sample Input (categorized):

Input:
No manual input

Sample Output (interleaved example):
1
40
2
41
3
42
... up to 10 and 50
```

### Actual Input (Raw Console)
```text
No console input
```

### Actual Output (Raw Console)
```text
1
40
2
41
3
42
```

### Output Explanation (Easy)
- One thread prints small range (1 to 10).
- Another thread prints large range (40 to 50).
- Since both run together, order can interleave.
- Final output still contains all numbers from both ranges.

---
