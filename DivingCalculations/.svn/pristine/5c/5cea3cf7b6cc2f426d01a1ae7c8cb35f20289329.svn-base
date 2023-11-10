package divingcalculations;

/**
 * In this class are the formulas to perform the calculations  of the Dive Formula Calculator
 *
 * @author Gustavo A Guevara Salazar
 * @version 23/04/2022
 */
public class DiveFormulas {

    private double ata;
    private double perOxyDecimal;

    /**
     * This method calculates the Maximum Operating Depth using the percentage of oxygen and the partial pressure
     *
     * @param percentageOxygen variable for percentage of oxygen
     * @param partialPressure  variable for partial pressure
     * @return Maximum Operating Depth in metres
     */
    public int mod(int percentageOxygen, double partialPressure) {

        perOxyDecimal = (double) percentageOxygen / 100;

        double modATA = partialPressure / perOxyDecimal;

        double modMetres = ((modATA - 1) * 10);

        return (int) Math.floor(modMetres);

    }

    /**
     * This method calculates the best Mix
     *
     * @param depth     variable for depth
     * @param pPressure variable for partial pressure
     * @return Best mix rounded down to keep within safe limits
     */
    public int BestMix(double depth, double pPressure) {

        ata = ataCalculation(depth);
        double bestMix = (pPressure / ata) * 100;
        return (int) Math.floor(bestMix);

    }

    /**
     * Calculates the partial pressure
     *
     * @param depth            variable for depth
     * @param percentageOxygen variable for percentage of oxygen
     * @return double partial pressure
     */
    public double partialPressure(double depth, int percentageOxygen) {

        ata = ataCalculation(depth);
        perOxyDecimal = calculationOxygenDecimal(percentageOxygen);

        double partialP = ata * perOxyDecimal;

        return Math.round(partialP * 100.0) / 100.0;
    }

    /**
     * This method Calculates the Equivalent Air Depth
     *
     * @param depth            variable for depth
     * @param percentageOxygen variable for percentage of oxygen
     * @return EAD in metres
     */
    public int equivalentAirDepth(double depth, int percentageOxygen) {

        ata = ataCalculation(depth);

        perOxyDecimal = calculationOxygenDecimal(percentageOxygen);

        double equivADepth = ((1 - perOxyDecimal) * ata) / 0.79;
        double ataToMetres = ((equivADepth - 1) * 10);


        return (int) Math.round(ataToMetres);
    }

    /**
     * ATA calculation
     *
     * @param depth variable for depth
     * @return ATA
     */
    public double ataCalculation(double depth) {
        return (depth / 10) + 1;

    }

    /**
     * This method express the percentage of oxygen in a decimal
     *
     * @param percentageOxygen variable for
     * @return decimal oxygen
     */
    public double calculationOxygenDecimal(int percentageOxygen) {
        return (double) percentageOxygen / 100;

    }

}
