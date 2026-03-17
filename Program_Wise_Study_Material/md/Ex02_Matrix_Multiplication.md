# Ex.No.2 Matrix Multiplication

## Ex.No.2 Matrix Multiplication

```java
import java.util.*; // Imports Scanner and other utility classes

class MatrixMul {
    public static void main(String[] args) { // main() is the entry method
        // Easy analogy:
        // Think of Matrix A rows as questions and Matrix B columns as answer keys.
        // One result cell is made by multiplying matching pairs and adding them.

        // Why output looks like that:
        // Each output cell is a sum of products (called dot product).
        Scanner s = new Scanner(System.in); // Reads all inputs

        int row1 = s.nextInt(); // Number of rows in matrix A
        int col1 = s.nextInt(); // Number of columns in matrix A
        int row2 = s.nextInt(); // Number of rows in matrix B
        int col2 = s.nextInt(); // Number of columns in matrix B

        // Condition for valid matrix multiplication:
        // columns of A must be equal to rows of B
        if (col1 != row2) {
            System.out.println("Matrix multiplication is not possible for these sizes."); // Invalid case
            return; // Stop program here
        }

        int[][] a = new int[row1][col1]; // Matrix A
        int[][] b = new int[row2][col2]; // Matrix B
        int[][] c = new int[row1][col2]; // Result matrix

        for (int i = 0; i < row1; i++) { // Outer loop for A rows
            for (int j = 0; j < col1; j++) { // Inner loop for A columns
                a[i][j] = s.nextInt(); // Read one value of A
            }
        }

        for (int i = 0; i < row2; i++) { // Outer loop for B rows
            for (int j = 0; j < col2; j++) { // Inner loop for B columns
                b[i][j] = s.nextInt(); // Read one value of B
            }
        }

        for (int i = 0; i < row1; i++) { // Picks one row from A
            for (int j = 0; j < col2; j++) { // Picks one column from B
                c[i][j] = 0; // Reset sum for this output cell
                for (int k = 0; k < col1; k++) { // Walk through matching row/column values
                    c[i][j] += a[i][k] * b[k][j]; // Multiply and add
                    // Example for first cell:
                    // c[0][0] = (1*5) + (2*7) = 19
                }
            }
        }

        System.out.println("Result matrix:"); // Output title
        for (int i = 0; i < row1; i++) { // Print each row
            for (int j = 0; j < col2; j++) { // Print each column value
                System.out.print(c[i][j] + " "); // Show one result value
            }
            System.out.println();
        }

        s.close(); // Good practice: close scanner
    }
}
```

### Variables Used (Easy Meaning)
- `row1`: Number of rows in matrix A.
- `col1`: Number of columns in matrix A.
- `row2`: Number of rows in matrix B.
- `col2`: Number of columns in matrix B.
- `a`: First matrix values.
- `b`: Second matrix values.
- `c`: Final multiplied matrix.
- `i`: Row loop variable.
- `j`: Column loop variable.
- `k`: Matching position loop for multiplication and sum.
- `s`: Scanner object to read input.

Simple understanding:
- First we check matrix size rule (`col1 == row2`).
- Then we read values of both matrices.
- Next, 3 loops calculate each output cell.
- Finally, we print the result matrix.

### Input Structure (How to Enter)
```text
Step 1: Enter Matrix A size
row1 col1

Step 2: Enter Matrix B size
row2 col2

Step 3: Enter Matrix A values row-wise
(row1 rows, each row has col1 values)

Step 4: Enter Matrix B values row-wise
(row2 rows, each row has col2 values)
```

### Sample Input / Output
```text
Sample Input (categorized):

Matrix A size (row1 col1):
2 2

Matrix B size (row2 col2):
2 2

Matrix A values:
1 2
3 4

Matrix B values:
5 6
7 8

Sample Output:
Result matrix:
19 22
43 50
```

### Actual Input (Raw Console)
```text
2 2
2 2
1 2
3 4
5 6
7 8
```

### Actual Output (Raw Console)
```text
Result matrix:
19 22
43 50
```

### Output Explanation (Easy)
- Output has `2` rows and `2` columns because result size is `row1 x col2`.
- First value `19` comes from first row of A and first column of B:
    `(1*5) + (2*7) = 19`.
- Second value `22` is `(1*6) + (2*8) = 22`.
- Next row values are `43` and `50` using the same multiply-and-add rule.

---

