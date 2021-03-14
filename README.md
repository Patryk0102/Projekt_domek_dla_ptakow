package com.mycompany.obrazek;

/**
 *
 * @author Patryk
 */
import java.awt.Color;
import java.awt.EventQueue;
import java.awt.Graphics;
import java.awt.Graphics2D;
import java.awt.geom.Point2D;
import javax.swing.JFrame;
import javax.swing.JPanel;

class Surface extends JPanel {

    private void doDrawing(Graphics g) {

        Graphics2D g2d = (Graphics2D) g;
      
        
        
         g2d.setColor(Color.gray);
         g2d.fillRect(500, 500, 500, 500); //domek
         
         g2d.setColor(Color.DARK_GRAY);
         g2d.fillOval(625, 625, 250, 250); //dziupla
         
         g2d.setColor(Color.black);
         g2d.fillRect(700,800,700,50); // kijek zeby ptaki mogly siedziec
     
         g2d.setColor(Color.red);
         g2d.fillRect(1200,600,150,150);// korpus ptaka
         
         g2d.setColor(Color.LIGHT_GRAY);
         g2d.fillOval(1225,500,100,100);// glowa ptaka
         
         g2d.setColor(Color.black);
         g2d.drawLine(1275,750,1200,800); //lewa noga ptaka
         g2d.drawLine(1275,750,1350,800); // prawa noga ptaka
         
        g2d.drawLine(500, 500, 750, 250); //dach
        g2d.drawLine(750, 250, 1000, 500); //dach
         
         g2d.setColor(Color.blue);
         g2d.fillOval(1250,525,20,25); //lewe oko
         
         g2d.setColor(Color.blue);
         g2d.fillOval(1275,525,20,25); // prawe oko
        
       
        
      
       
    }

    @Override
    public void paintComponent(Graphics g) {

        super.paintComponent(g);
        doDrawing(g);
    }
}

public class LinesEx extends JFrame {

    public LinesEx() {

        initUI();
    }

    private void initUI() {

        add(new Surface());

        setTitle("Domek dla ptakow"); //ustawiam tytul
        setSize(2000, 2000); //ustawiam rozmiar okienka w ktorym wyswietla rysunek
        setLocationRelativeTo(null);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }

    public static void main(String[] args) {

        EventQueue.invokeLater(() -> {
            LinesEx ex = new LinesEx();
            ex.setVisible(true);
        });
    }
}
