# Ex.No.14 Simple Calculator

## Ex.No.14 Simple Calculator

```java
import javax.swing.*; // Imports Swing classes
import java.awt.*; // Imports layout classes
import java.awt.event.*; // Imports action event classes

public class SimpleCalculator extends JFrame implements ActionListener {
    private JTextField t1; // First number input box
    private JTextField t2; // Second number input box
    private JLabel result; // Label to show answer

    public SimpleCalculator() { // Constructor creates calculator UI
        // Easy analogy:
        // Think this like a small pocket calculator.
        // Enter two numbers and press operation button.

        setTitle("Simple Calculator"); // Window title
        setSize(400, 220); // Window size
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); // Close app on window close
        setLayout(new GridLayout(5, 2, 5, 5)); // Grid layout for neat arrangement

        add(new JLabel("First Number:"));
        t1 = new JTextField();
        add(t1);

        add(new JLabel("Second Number:"));
        t2 = new JTextField();
        add(t2);

        JButton addBtn = new JButton("Add");
        JButton subBtn = new JButton("Subtract");
        JButton mulBtn = new JButton("Multiply");
        JButton divBtn = new JButton("Divide");

        add(addBtn);
        add(subBtn);
        add(mulBtn);
        add(divBtn);

        result = new JLabel("Result: "); // Default output label
        add(result);

        // Listener means actionPerformed() runs when button is clicked
        addBtn.addActionListener(this);
        subBtn.addActionListener(this);
        mulBtn.addActionListener(this);
        divBtn.addActionListener(this);

        setVisible(true); // Shows window
    }

    public void actionPerformed(ActionEvent e) { // Runs on button click
        try {
            double a = Double.parseDouble(t1.getText()); // Reads first number
            double b = Double.parseDouble(t2.getText()); // Reads second number
            double ans = 0; // Stores result

            String op = e.getActionCommand(); // Gets clicked button text
            if (op.equals("Add")) {
                ans = a + b;
            } else if (op.equals("Subtract")) {
                ans = a - b;
            } else if (op.equals("Multiply")) {
                ans = a * b;
            } else if (op.equals("Divide")) {
                if (b == 0) { // Checks divide by zero
                    result.setText("Result: Cannot divide by zero");
                    return;
                }
                ans = a / b;
            }

            result.setText("Result: " + ans); // Displays final answer
        } catch (NumberFormatException ex) {
            result.setText("Result: Enter valid numbers"); // Handles wrong input
        }
    }

    public static void main(String[] args) { // Starts Swing app
        SwingUtilities.invokeLater(SimpleCalculator::new);
    }
}
```

### Variables Used (Easy Meaning)
- `t1`: Text field for first number.
- `t2`: Text field for second number.
- `result`: Label that shows output.
- `a`: Parsed first number.
- `b`: Parsed second number.
- `ans`: Calculated answer.
- `op`: Selected operation button name.

### Simple understanding
- Program opens calculator window.
- User enters two numbers.
- User clicks operation button.
- Program calculates and shows result.

### Input Structure (How to Enter)
```text
Step 1: Run program to open calculator window
Step 2: Enter first number
Step 3: Enter second number
Step 4: Click Add / Subtract / Multiply / Divide

Important:
- For division, second number must not be 0
- Input is GUI-based, not console-based
```

### Sample Input / Output
```text
Sample Input (categorized):

First Number:
20

Second Number:
5

Operation:
Divide

Sample Output:
Result: 4.0
```

### Actual Input (Raw Console)
```text
No console input
```

### Actual Output (Raw Console)
```text
No console output (result appears in GUI label)
```

### Output Explanation (Easy)
- Button decides which arithmetic operation runs.
- Program converts text into numbers first.
- Valid input shows answer in result label.
- Wrong input or divide-by-zero shows clear message.

---
