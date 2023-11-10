package divingcalculations;

import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

/**
 * @author Gustavo
 */
public class DiveCalculatorPanel extends JPanel {
    // private JLabel title;
    private final JPanel panelRadio;
    private final JPanel panelOptionsStandard;
    private final JPanel panelAnswer;
    private final JRadioButton radioMaximumOperatingDepth;
    private final JRadioButton radioStandardMaximumOperatingDepth;
    private final JRadioButton radioBestMix;
    private final JRadioButton radioPartialPressure;
    private final JRadioButton radioEquivalentAirDepth;
    private final JSpinner spinnerPercentageOxygen;
    private final JSpinner spinnerPartialPressure;
    private final JSpinner spinnerDepth;
    private JTextArea jTextAreaResult;

    private String percentageOxygen;
    private String partialPressure;
    private String depth;

    private String selectionRadio;


    public DiveCalculatorPanel(String string) {
        setPreferredSize(new Dimension(350, 225));
        //  title = new JLabel("Standard Calculations", SwingConstants.CENTER);


        radioMaximumOperatingDepth = new JRadioButton("Maximum Operating Depth", false);
        radioMaximumOperatingDepth.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {


            }
        });


        radioStandardMaximumOperatingDepth = new JRadioButton("Standard Maximum Operating Depth", false);
        radioStandardMaximumOperatingDepth.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                selectionRadio = e.getActionCommand();


            }
        });
        System.out.println(selectionRadio);

        radioBestMix = new JRadioButton("Best Mix", false);
        radioBestMix.addActionListener(e -> selectionRadio = e.getActionCommand());

        radioPartialPressure = new JRadioButton("Partial Pressure", false);
        radioPartialPressure.addActionListener(e -> selectionRadio = e.getActionCommand());

        radioEquivalentAirDepth = new JRadioButton("Equivalent Air Depth", false);
        radioEquivalentAirDepth.addActionListener(e -> selectionRadio = e.getActionCommand());

        SpinnerModel value =
                new SpinnerNumberModel(20, //initial value
                        18, //minimum value
                        100, //maximum value
                        1); //step

        SpinnerModel value2 = new SpinnerNumberModel(1.1, 1.1, 1.6, 0.1);

        SpinnerModel value3 =
                new SpinnerNumberModel(20, //initial value
                        18, //minimum value
                        100, //maximum value
                        1); //step

        spinnerPercentageOxygen = new JSpinner(value);

        spinnerPartialPressure = new JSpinner(value2);

        spinnerDepth = new JSpinner(value3);

        panelOptionsStandard = new JPanel();
        panelRadio = new JPanel();
        panelAnswer = new JPanel();

        if (string.equals("left")) {


            panelRadio.setBorder(BorderFactory.createTitledBorder("Calculation"));
            BoxLayout layout = new BoxLayout(panelRadio, BoxLayout.Y_AXIS);
            panelRadio.setLayout(layout);


            panelRadio.add(radioMaximumOperatingDepth);
            panelRadio.add(radioStandardMaximumOperatingDepth);
            panelRadio.add(radioBestMix);
            panelRadio.add(radioPartialPressure);
            panelRadio.add(radioEquivalentAirDepth);

            add(panelRadio);

        }

        if (string.equals("center")) {

            //   panelOptionsStandard.setPreferredSize(new Dimension(800,50));
            panelOptionsStandard.setBorder(BorderFactory.createTitledBorder("Variables"));
            BoxLayout layoutOptionStandard = new BoxLayout(panelOptionsStandard, BoxLayout.Y_AXIS);

            panelOptionsStandard.setLayout(layoutOptionStandard);
            JLabel lab1 = new JLabel("Percentage Oxygen:", SwingConstants.LEFT);
            panelOptionsStandard.add(lab1);
            panelOptionsStandard.add(spinnerPercentageOxygen);
            JLabel lab2 = new JLabel("Partial pressure:", SwingConstants.LEFT);
            panelOptionsStandard.add(lab2);
            panelOptionsStandard.add(spinnerPartialPressure);

            JLabel lab3 = new JLabel("Depth:");
            panelOptionsStandard.add(lab3);
            panelOptionsStandard.add(spinnerDepth);


            add(panelOptionsStandard);
        }

        if (string.equals("right")) {


            BoxLayout dsf = new BoxLayout(panelAnswer, BoxLayout.Y_AXIS);
            panelAnswer.setLayout(dsf);

            jTextAreaResult = new JTextArea(10, 20);
            Button doCalculation = new Button();
            doCalculation.setLabel("Do Calculation");

            doCalculation.addActionListener(new ActionListener() {
                @Override
                public void actionPerformed(ActionEvent e) {


                    jTextAreaResult.setText(selectionRadio);

                }
            });
            jTextAreaResult.setEditable(false);
            panelAnswer.add(jTextAreaResult);
            panelAnswer.add(doCalculation);
            add(panelAnswer);


        }

    }

    public String getSelectionRadio() {
        return selectionRadio;
    }

    public void setSelectionRadio(String selectionRadio) {
        this.selectionRadio = selectionRadio;
    }


}



