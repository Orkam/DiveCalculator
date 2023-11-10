package divingcalculations;

/**
 * In this class are the validations to perform the calculations  of the Dive Formula Calculator
 *
 * @author Gustavo A Guevara Salazar
 * @version 23/04/2022
 */
public class DiveValidation {

    /**
     * This method validate if the option number is in the range 1 to 9.
     *
     * @param str variable with option value
     * @return if is a number in the range 1 to 9 return true otherwise false
     */
    public boolean menuValidation(String str) {
        boolean flag = false;
        if (str.matches("[1-9]")) {
            flag = true;
        }
        return flag;

    }


    /**
     * This method validate if the oxygen number is in the range 18 to 100.
     *
     * @param str variable with oxygen value
     * @return if is a number in the range 18 to 100 return true otherwise false
     */
    public boolean oxyValidation(String str) {

        boolean flag = false;
        if (str.matches("^100|1[8-9]|[2-9][0-9]$")) {
            flag = true;
        }
        return flag;
    }

    /**
     * This method validate if the depth number is in the range 1 to 78 metres.
     *
     * @param str variable with depth value
     * @return if the number in the range 1 to 78 return true otherwise false
     */
    public boolean depthValidation(String str) {

        boolean flag = false;
        if (str.matches("^[1-9]|[1-7][0-8]$")) {
            flag = true;
        }
        return flag;
    }


    /**
     * @param str variable String from user input
     * @return if is a number between 1.1 and 1.6 return true otherwise false
     */
    public boolean validatePartialPressure(String str) {

        boolean flag = false;
        if (str.matches("[1](\\.[1-6])")) {
            flag = true;
        }
        return flag;
    }

    /**
     * This method validate if the oxygen range numbers are in the range 18 and 50 for the Complex calculations
     *
     * @param str range from the user
     * @return if the numbers are between 18 and 50 return true otherwise false
     */
    public boolean oxyComplexCalculations(String[] str) {

        boolean flag = false;

        if (str.length == 2) {

            if (str[0].matches("^1[8-9]|[2-4][0-9]|50$") && str[1].matches("^1[8-9]|[2-4][0-9]|50$")) {

                flag = true;
            }
        }
        return flag;
    }

    /**
     * This method validate if the depth range are in the range 3 to 70 metres
     *
     * @param str range from the user
     * @return if the numbers are between 3 and 70 return true otherwise false
     */
    public boolean depthComplexCalculations(String[] str) {

        boolean flag = false;

        if (str.length == 2) {

            if (str[0].matches("^[3-9]|[1-6][0-9]|70$") && str[1].matches("^[3-9]|[1-6][0-9]|70$")) {

                flag = true;
            }
        }
        return flag;
    }

}
