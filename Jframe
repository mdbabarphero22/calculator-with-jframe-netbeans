import javax.swing.*;

public class Calculator extends JFrame {
    
    double num1, num2, result;
    String operator;
    JTextField ti, tl; // Assuming ti and tl are JTextField components

    public Calculator() {
        initComponents();
    }
    
    private void initComponents() {
        // Initialize components (buttons, text fields, etc.)
        // Add action listeners to buttons
    }
    
    private void numButtonActionPerformed(java.awt.event.ActionEvent evt) {
        ti.setText(ti.getText() + ((JButton) evt.getSource()).getText());
    }

    private void operatorActionPerformed(java.awt.event.ActionEvent evt) {
        num1 = Double.parseDouble(ti.getText());
        ti.setText("");
        operator = ((JButton) evt.getSource()).getText();
    }

    private void bequalActionPerformed(java.awt.event.ActionEvent evt) {
        num2 = Double.parseDouble(ti.getText());
        switch (operator) {
            case "+": result = num1 + num2; break;
            case "-": result = num1 - num2; break;
            case "*": result = num1 * num2; break;
            case "/": result = (num2 != 0) ? num1 / num2 : 0; break;
        }
        tl.setText(String.valueOf(result));
    }

    public static void main(String args[]) {
        // Set Nimbus look and feel
        try {
            for (UIManager.LookAndFeelInfo info : UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ClassNotFoundException | InstantiationException | IllegalAccessException | UnsupportedLookAndFeelException ex) {
            java.util.logging.Logger.getLogger(Calculator.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        }

        // Create and display the form
        java.awt.EventQueue.invokeLater(() -> {
            new Calculator().setVisible(true);
        });
    }
}
