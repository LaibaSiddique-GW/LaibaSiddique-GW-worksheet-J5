# Laiba Siddique
# Worksheet J5 - GUIs

## 1.) How does object-oriented programming pair so closely with GUIs?

In the 1990's, as others were starting to use computers at home and using programmigns, JAVA and GUIs were on the rise, and GUIs allow people to use programs without knowing the insides. This relates to information hiding and abstracting things away, which OOP does. 
(JAVA swing library provides and API to seamlessley use GUIs.)

## 2.) What is the relationship between `WindowListener` and `WindowAdapter`?

WindowListener is an interface, and WindowAdapter is an extendable class that implements WindowListener allowing you to only write code for the methods you want implemented. 

## 3.) What does the program below produce for a GUI? (You can sketch and upload an image or describe it – do this without running the program to make sure you understand what each line below is doing).

_Attached in the Zip File Submission._

## 4.) Modify the `HelloGoodbyeEx2` code to update the number of times the button has been clicked on the button’s label itself.

```
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class HelloGoodbyeEx2 {

    public static void main(String args[]) {
        JFrame f = new JFrame();
        f.setTitle("Hello/Goodbye Ex1");
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        
        JLabel label = new JLabel("Hello");
        JButton button = new JButton("Click me!");

        // num times clicked
        int count = 0;

        //using an anonymous (static) class
        //avoids having to make ButtonClickListenerEx1 class above
        button.addActionListener(new ActionListener() {
                //implement the one method here
                //shares the name space with the whole class
                //has access to the label field above
                public void actionPerformed(ActionEvent e) {
                    if (label.getText().equals("Hello")) {
                        label.setText("Goodbye");
                    }else {
                        label.setText("Hello");
                    }
                    count++;
                    button.setText("Click Me!" + count);
                }
            });
        
        f.add(button, BorderLayout.SOUTH);
        f.add(label, BorderLayout.NORTH);

        f.pack();
        f.setVisible(true);
        
    }
}
```

## 5.) Consider the following Java swing GUI. Convert the `ActionListeners` to Lambda Functions.

```
red.addActionListener(e) -> {
    label.setText("RED");
}
```

```
blue.addActionListener(e) -> {
    label.setText("BLUE");
}
```

## 6.) Explain why for `ActionListener` you can use a Lambda function but for `WindowListener` you cannot?

ActionListener only requires 1 (i.e. a single) method to be realized: actionPerformed. So, Lambda knows what method to call. Whereas, WindowListener has multiple methods that need to be realized; so, Lambda does not know which method to call. 

## 7.) Write a program that allows you to enter a 6-digit PIN, like you would on your smartphone to unlock it. It should have the following layout: Where `[ < ]` is a “backspace” button. The display should show the PIN as it is typed, and when the user enters the PIN 202113, the display changes to “YOU MAY ENTER!”

_Code Attached in Zip File Submission._

