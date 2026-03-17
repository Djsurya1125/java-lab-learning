# Ex.No.13 Mouse Events with Adapter

## Ex.No.13 Mouse Events with Adapter

```java
import javax.swing.*; // Imports Swing classes
import java.awt.*; // Imports layout classes
import java.awt.event.*; // Imports mouse event classes

public class MouseAdapterDemo extends JFrame {
    private JLabel status; // Label to show current mouse event message

    public MouseAdapterDemo() { // Constructor creates UI
        // Easy analogy:
        // Think this window like a touch board.
        // When mouse enters, clicks, exits, or moves, message changes.

        setTitle("Mouse Event Demo"); // Window title
        setSize(420, 250); // Window size
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); // Close app on window close
        setLayout(new BorderLayout());

        status = new JLabel("Move or click mouse inside window", SwingConstants.CENTER); // Default message
        add(status, BorderLayout.CENTER);

        addMouseListener(new MouseAdapter() { // Adapter lets us override only needed methods
            public void mouseEntered(MouseEvent e) {
                status.setText("Mouse entered window"); // Shows enter message
            }

            public void mouseExited(MouseEvent e) {
                status.setText("Mouse exited window"); // Shows exit message
            }

            public void mouseClicked(MouseEvent e) {
                status.setText("Mouse clicked at (" + e.getX() + ", " + e.getY() + ")"); // Shows click coordinates
            }
        });

        addMouseMotionListener(new MouseMotionAdapter() {
            public void mouseMoved(MouseEvent e) {
                status.setText("Mouse moved at (" + e.getX() + ", " + e.getY() + ")"); // Shows move coordinates
            }
        });

        setVisible(true); // Displays window
    }

    public static void main(String[] args) { // Starts Swing app
        SwingUtilities.invokeLater(MouseAdapterDemo::new);
    }
}
```

### Variables Used (Easy Meaning)
- `status`: Label used to show mouse event text.
- `e`: MouseEvent object holding mouse details.
- `e.getX()`: Mouse x-coordinate.
- `e.getY()`: Mouse y-coordinate.

### Simple understanding
- Program opens a window.
- Mouse listener checks enter, exit, and click.
- Mouse motion listener checks movement.
- Label updates continuously with event message.

### Input Structure (How to Enter)
```text
Step 1: Run program to open window
Step 2: Move mouse inside window
Step 3: Click mouse inside window
Step 4: Move mouse out of window

Important:
- Input is mouse action (GUI), not keyboard input
```

### Sample Input / Output
```text
Sample Input (categorized):

Action 1:
Mouse entered window

Action 2:
Mouse clicked near center

Action 3:
Mouse moved

Sample Output (on label):
Mouse entered window
Mouse clicked at (210, 120)
Mouse moved at (215, 118)
```

### Actual Input (Raw Console)
```text
No console input
```

### Actual Output (Raw Console)
```text
No console output (messages appear inside GUI label)
```

### Output Explanation (Easy)
- Adapter classes capture mouse actions.
- Each action triggers its own method.
- Method updates the label text.
- Coordinates show exact mouse position in window.

---
