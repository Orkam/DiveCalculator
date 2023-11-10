package divingcalculations;


import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Scanner;

/**
 * Class core of Dive Formula Calculator. Creation of program logic, menu management and table creation
 *
 * @author Gustavo A Guevara Salazar
 * @version 23/04/2022
 */

public class DiveBroker {

    Scanner scanner = new Scanner(System.in);
    private int option;


    public void menu() {
        scanner = new Scanner(System.in);
        System.out.println("Welcome to the Dive Formula Calculator\n");
        System.out.println("Select which calculation you wish to perform");
        String[] calculationMenu = new String[]{"1. HELP",
                "2. MOD",
                "3. SMOD",
                "4. BM",
                "5. PP",
                "6. EAD",
                "7. PPT",
                "8. EADT",
                "9. Exit",
        };


        for (String option : calculationMenu) {
            System.out.println(option);
        }


        System.out.print("Enter 1 to 9: ");


        String opt = scanner.nextLine().replace(" ", ""); // Avoid errors if the user enters more than one number separated by spaces example 1 9 or 1 20

        while (!new DiveValidation().menuValidation(opt)) {

            System.out.print("Invalid Option. Please reenter: ");
            opt = scanner.nextLine().replace(" ", "");
        }


        option = Integer.parseInt(opt);


        switchCase();
    }


    private void switchCase() {

        double partialPressure = 0.0;
        boolean isNumber = false;
        boolean validPP = false;
        int percentageOxygen = 0;
        double depth = 0.0;
        scanner = new Scanner(System.in);

        switch (option) {
            case 1 -> {

                System.out.println("You can select from the following choices:");
                String[] helpMenu = new String[]{"1. HELP prints this message.",
                        "2. MOD (Maximum Operating Depth) for a supplied percentage of Oxygen and partial pressure.",
                        "3. SMOD (Standard Maximum Operating Depth) for a supplied percentage of Oxygen and a standard 1.4 partial pressure.",
                        "4. BM (Best Mix) for a dive with a supplied partial pressure and depth (in metres).",
                        "5. PP (Partial Pressure) for a supplied percentage of Oxygen and depth (in metres).",
                        "6. EAD (Equivalent Air Depth) for a supplied percentage of Oxygen and depth (in metres).",
                        "7. PPT (Table of Partial Pressures) it will show a Partial Pressures Table for a start and end percentage of Oxygen and a start and end depth;" +
                                " any partial pressure above 1.6 is not displayed",
                        "8. EADT (Equivalent Air Depth Table) it will show the EAD's for a start and end percentage of Oxygen and a start and end depth",
                        "9. Exit the Dive Formula Calculator.",
                };

                for (String menu : helpMenu) {
                    System.out.println(menu);
                }
            }
            case 2 -> {
                System.out.println("Calculating the MOD");
                System.out.print("Enter the percentage of Oxygen: ");
                String pOxygenStr = scanner.nextLine().replace(" ", "");


                while (!isNumber) {
                    isNumber = new DiveValidation().oxyValidation(pOxygenStr);
                    if (isNumber) {
                        percentageOxygen = Integer.parseInt(pOxygenStr);

                    } else {
                        System.out.print("Invalid percentage of Oxygen, it must be between 18 and 100: ");
                        pOxygenStr = scanner.nextLine().replace(" ", "");
                    }
                }

                System.out.print("Enter the partial pressure of Oxygen (between 1.1 and 1.6 inclusive): ");
                String pPressureStr = scanner.nextLine().replace(" ", "");

                while (!validPP) {
                    validPP = new DiveValidation().validatePartialPressure(pPressureStr);
                    if (validPP) {
                        partialPressure = Double.parseDouble(pPressureStr);

                    } else {
                        System.out.print("Invalid partial pressure of Oxygen, it must be " +
                                "between 1.1 and 1.6 inclusive: ");
                        pPressureStr = scanner.nextLine().replace(" ", "");
                    }
                }


                int mod = new DiveFormulas().mod(percentageOxygen, partialPressure);

                System.out.println("Maximum operating depth (MOD) for a dive with " + percentageOxygen + "% " +
                        "O2 and a partial pressure of " + partialPressure + " is " + mod + " metres");

            }


            case 3 -> {

                System.out.println("Calculating the MOD for the standard 1.4 partial pressure");
                System.out.print("Enter the percentage of Oxygen: ");
                String pOxygenStr = scanner.nextLine().replace(" ", "");


                while (!isNumber) {
                    isNumber = new DiveValidation().oxyValidation(pOxygenStr);
                    if (isNumber) {
                        percentageOxygen = Integer.parseInt(pOxygenStr);
                    } else {
                        System.out.print("Invalid percentage of Oxygen, it must be between 18 and 100: ");
                        pOxygenStr = scanner.nextLine().replace(" ", "");
                    }
                }
                partialPressure = 1.4;

                int mod = new DiveFormulas().mod(percentageOxygen, partialPressure);

                System.out.println("Maximum operating depth (MOD) for a dive with " + percentageOxygen + "% " +
                        "O2 and a partial pressure of " + partialPressure + " is " + mod + " metres");
            }

            case 4 -> {

                System.out.println("Calculating the Best Mix");
                System.out.print("Enter the partial pressure of Oxygen (between 1.1 and 1.6 inclusive): ");

                String pPressureStr = scanner.nextLine().replace(" ", "");

                while (!validPP) {
                    validPP = new DiveValidation().validatePartialPressure(pPressureStr);
                    if (validPP) {
                        partialPressure = Double.parseDouble(pPressureStr);

                    } else {
                        System.out.print("Invalid partial pressure of Oxygen, it must be " +
                                "between 1.1 and 1.6 inclusive: ");
                        pPressureStr = scanner.nextLine().replace(" ", "");
                    }
                }

                System.out.print("Enter the depth of the dive (in metres): ");

                String depthStr = scanner.nextLine().replace(" ", "");

                while (!isNumber) {
                    isNumber = new DiveValidation().depthValidation(depthStr);
                    if (isNumber) {
                        depth = Integer.parseInt(depthStr);
                    } else {
                        System.out.print("Invalid depth, it must be between 1 and 78 metres: ");
                        depthStr = scanner.nextLine().replace(" ", "");
                    }
                }


                int bestMix = new DiveFormulas().BestMix(depth, partialPressure);
                System.out.println("Best mix for a dive to " + depth + " metres with a partial pressure of " +
                        partialPressure + " is " + bestMix + "% O2");

            }
            case 5 -> {

                System.out.println("Calculating the Partial Pressure");
                System.out.print("Enter the depth of the dive (in metres): ");
                String depthStr = scanner.nextLine().replace(" ", "");

                while (!isNumber) {
                    isNumber = new DiveValidation().depthValidation(depthStr);
                    if (isNumber) {
                        depth = Integer.parseInt(depthStr);
                    } else {
                        System.out.print("Invalid depth, it must be between 1 and 78 metres: ");
                        depthStr = scanner.nextLine().replace(" ", "");
                    }
                }

                System.out.print("Enter the percentage of Oxygen: ");

                String pOxygenStr = scanner.nextLine().replace(" ", "");

                isNumber = false;
                while (!isNumber) {
                    isNumber = new DiveValidation().oxyValidation(pOxygenStr);
                    if (isNumber) {
                        percentageOxygen = Integer.parseInt(pOxygenStr);
                    } else {
                        System.out.print("Invalid percentage of Oxygen, it must be between 18 and 100: ");
                        pOxygenStr = scanner.nextLine().replace(" ", "");
                    }
                }

                partialPressure = new DiveFormulas().partialPressure(depth, percentageOxygen);

                System.out.println("The partial pressure of Oxygen for a dive to " + depth + " metres with a percentage of Oxygen of " +
                        percentageOxygen + "% is " + partialPressure + " ata");

            }
            case 6 -> {

                System.out.println("Calculating the Equivalent Air Depth");
                System.out.print("Enter the depth of the dive (in metres): ");
                String depthStr = scanner.nextLine().replace(" ", "");

                while (!isNumber) {
                    isNumber = new DiveValidation().depthValidation(depthStr);
                    if (isNumber) {
                        depth = Integer.parseInt(depthStr);
                    } else {
                        System.out.print("Invalid depth, it must be between 1 and 78 metres: ");
                        depthStr = scanner.nextLine().replace(" ", "");
                    }
                }
                System.out.print("Enter the percentage of Oxygen: ");

                String pOxygenStr = scanner.nextLine().replace(" ", "");
                isNumber = false;
                while (!isNumber) {
                    isNumber = new DiveValidation().oxyValidation(pOxygenStr);
                    if (isNumber) {
                        percentageOxygen = Integer.parseInt(pOxygenStr);
                    } else {
                        System.out.print("Invalid percentage of Oxygen, it must be between 18 and 100: ");
                        pOxygenStr = scanner.nextLine().replace(" ", "");
                    }
                }

                int equAirDepth = new DiveFormulas().equivalentAirDepth(depth, percentageOxygen);

                System.out.println("Equivalent Air Depth for a dive with " + percentageOxygen + "% O2 to a depth of " +
                        depth + " metres is " + equAirDepth + " metres");


            }
            case 7, 8 -> tables(option);

            case 9 -> System.exit(0);

        }

        boolean flag = true;
        String anotherCalculation = "";
        while (flag) {

            System.out.print("Would you like to perform another calculation (y/n)? ");
            anotherCalculation = scanner.nextLine().replace(" ", "");
            if (!anotherCalculation.equalsIgnoreCase("y") &&
                    !anotherCalculation.equalsIgnoreCase("n")) {
                System.out.println("Invalid option");
            } else {
                flag = false;
            }
        }

        if (anotherCalculation.equalsIgnoreCase("y")) {
            menu();
        } else if (anotherCalculation.equalsIgnoreCase("n")) {
            System.exit(0);
        }

    }

    /**
     * Manage user input to create the Tables either PPT or EADT
     *
     * @param commandOption user input value caught from switch case
     */
    private void tables(int commandOption) {

        BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
        if (commandOption == 8) {
            System.out.println("Generating Equivalent Air Depths Table");
        } else if (commandOption == 7) {
            System.out.println("Generating Partial Pressures Table");
        }


        System.out.print("Enter a start and end percentage of Oxygen: ");


        try {

            String[] oxygenNumberValidated = in.readLine().split(" ");
            int startOxy = 0;
            int endOxy = 0;
            boolean validNumbers = false;
            while (!validNumbers) {
                if (new DiveValidation().oxyComplexCalculations(oxygenNumberValidated)) {
                    startOxy = Integer.parseInt(oxygenNumberValidated[0]);
                    endOxy = Integer.parseInt(oxygenNumberValidated[1]);

                    if (endOxy > startOxy) {
                        validNumbers = true;
                    } else {

                        System.out.println("The end value must be larger than the start value");
                        System.out.print("Enter a start and end percentage of Oxygen: ");
                        oxygenNumberValidated = in.readLine().split(" ");
                    }
                } else {

                    System.out.println("Invalid input. The percentages of Oxygen must be from 18% to 50% ");
                    System.out.print("Enter a start and end percentage of Oxygen: ");
                    oxygenNumberValidated = in.readLine().split(" ");

                }
            }


            System.out.print("Enter a start and end depth (in metres): ");
            String[] depthNumberValidated = in.readLine().split(" ");
            int startDepth = 0;
            int endDepth = 0;

            validNumbers = false;
            while (!validNumbers) {
                if (new DiveValidation().depthComplexCalculations(depthNumberValidated)) {
                    startDepth = Integer.parseInt(depthNumberValidated[0]);
                    endDepth = Integer.parseInt(depthNumberValidated[1]);

                    if (endDepth > startDepth) {
                        validNumbers = true;
                    } else {

                        System.out.println("The end value must be larger than the start value");
                        System.out.print("Enter a start and end depth (in metres): ");
                        depthNumberValidated = in.readLine().split(" ");
                    }
                } else {

                    System.out.println("Invalid input. The depth must be from 3 to 70 metres. ");
                    System.out.print("Enter a start and end depth (in metres): ");
                    depthNumberValidated = in.readLine().split(" ");

                }
            }


            if (commandOption == 8) {

                System.out.println("Equivalent Air Depth Table for " + startOxy + " to " + endOxy + " percent Oxygen and depths of " + startDepth + " to " + endDepth + " metres");
            } else if (commandOption == 7) {
                System.out.println("Partial Pressures Table for " + startOxy + " to " + endOxy + " percent Oxygen and depths of " + startDepth + " to " + endDepth + " metres");
            }


            System.out.print("======================================================================================");

            System.out.println();
            System.out.println();
            if (commandOption == 8) {
                System.out.format("            ");
            } else if (commandOption == 7) {
                System.out.format("          ");

            }

            for (int j = startOxy; j <= endOxy; j++) {
                System.out.format("%10d", j);
            }
            System.out.println();

            System.out.format("------------");
            int diff = endOxy - startOxy;
            for (int j = 0; j <= diff; j++) {
                System.out.print("----------");
            }


            System.out.println();

            for (int i = startDepth; i <= endDepth; i += 3) {

                System.out.format("%10d |", i);
                for (int j = startOxy; j <= endOxy; j++) {

                    if (commandOption == 8) {

                        int equAirDepth = new DiveFormulas().equivalentAirDepth(i, j);

                        System.out.format("%10d", equAirDepth);
                    } else if (commandOption == 7) {

                        double partialPressure = new DiveFormulas().partialPressure(i, j);

                        if (partialPressure <= 1.6) {

                            System.out.format("%10.2f", partialPressure);
                        }
                    }

                }
                System.out.println();
            }
            System.out.println();

        } catch (IOException e) {
            e.printStackTrace();
        }


    }


}
