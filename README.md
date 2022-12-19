package fees;
// Java program to write a student
// information in JFrame and
// storing it in a file

import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.io.*;

public class GFG {

	// Function to write a student
	// information in JFrame and
	// storing it in a file
	public static void StudentInfo()
	{

		// Creating a new frame using JFrame
		JFrame f
			= new JFrame(
				"Student Details Form");

		// Creating the labels
		JLabel l1, l2, l3,  l5;

		// Creating three text fields.
		// One for student name, one for
		// college mail ID and one
		// for Mobile No
		JTextField t1, t2, t3, t5;

                
		

		// Creating a  button
		JButton b1 ;

		// Naming the labels and setting
		// the bounds for the labels
		l1 = new JLabel("Student Name:");
		l1.setBounds(50, 50, 100, 30);
		l2 = new JLabel("College Email ID:");
		l2.setBounds(50, 120, 120, 30);
		l3 = new JLabel("RegNo");
		l3.setBounds(50, 190, 50, 30);
		
		l5 = new JLabel("Mobile No:");
		l5.setBounds(50, 270, 90, 30);

		// Creating the textfields and
		// setting the bounds for textfields
		t1 = new JTextField();
		t1.setBounds(170, 50, 130, 30);
		t2 = new JTextField();
		t2.setBounds(170, 120, 130, 30);
		t3 = new JTextField();
		t3.setBounds(170, 190, 130, 30);
                t5 = new JTextField();
		t5.setBounds(170, 270, 130, 30);
                
		
		

		

		// Creating one button for Saving
		
		// and setting the bounds
		b1 = new JButton("Save");
		b1.setBounds(200, 350, 70, 30);
		

		// Adding action listener
		b1.addActionListener((ActionEvent e) -> {
                    // Getting the text from text fields
                    
                    // and copying it to a strings
                    
                    String s1 = t1.getText();
                    String s2 = t2.getText();
                    String s3 = t3.getText();
                    String s5 = t5.getText();
                    
                    
                    
                    if (e.getSource() == b1) {
                        try {
                            
                            // Creating a file and
                            // writing the data
                            // into a Textfile.
                            FileWriter w
                                    = new FileWriter(
                                            "GFG.txt", true);
                            
                            w.write(s1 + "\n");
                            w.write(s2 + "\n");
                            w.write(s3 + "\n");
                            w.write(s5 + "\n");
                            
                            
                            w.close();
                        }
                        catch (IOException ae) {
                            System.out.println(ae);
                        }
                    }
                    
                    // Shows a Pop up Message when
                    // save button is clicked
                    JOptionPane
                            .showMessageDialog(
                                    f,
                                    "Successfully Saved"
                                            + " The Details");
                });


		
		// Default method for closing the frame
		f.addWindowListener(new WindowAdapter() {
                        @Override
			public void windowClosing(WindowEvent e)
			{
				System.exit(0);
			}
		});

		// Adding the created objects
		// to the frame
		f.add(l1);
		f.add(t1);
		f.add(l2);
		f.add(t2);
		f.add(l3);
               		
		
		f.add(t5);
		f.add(l5);
		f.add(t3);
		f.add(b1);
		
		f.setLayout(null);
		f.setSize(700, 600);
		f.setVisible(true);
	}
	// Driver code
	public static void main(String args[])
	{
		StudentInfo();
	}
}
