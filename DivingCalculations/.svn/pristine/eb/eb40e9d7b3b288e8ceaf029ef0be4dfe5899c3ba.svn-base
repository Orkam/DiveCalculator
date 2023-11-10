
import divingcalculations.DiveFormulas;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;
import static org.junit.jupiter.api.Assertions.assertNotEquals;

/**
 * Test Formula methods
 *
 * @author Gustavo A Guevara Salazar
 * @version 23/04/2022
 */
class DiveFormulasTest {

    DiveFormulas diveFormulas = new DiveFormulas();

    @Test
    void mod() {

        assertEquals(33, new DiveFormulas().mod(32, 1.4));
        assertNotEquals(diveFormulas.mod(22, 1.5), 80);
    }

    @Test
    void bestMix() {

        assertEquals(22, new DiveFormulas().BestMix(56.0, 1.5));
        assertNotEquals(diveFormulas.BestMix(22, 1.5), 50);
    }

    @Test
    void partialPressure() {
        assertEquals(1.15, new DiveFormulas().partialPressure(40, 23));
        assertNotEquals(diveFormulas.partialPressure(33, 25), 50, 0.0);
    }

    @Test
    void equivalentAirDepth() {
        assertEquals(57, new DiveFormulas().equivalentAirDepth(58, 22));
        assertNotEquals(diveFormulas.equivalentAirDepth(33, 25), 50);
    }

    @Test
    void ataCalculation() {
        assertEquals(4, new DiveFormulas().ataCalculation(30.0));
        assertNotEquals(diveFormulas.ataCalculation(40.0), 0.23, 0.0);
    }

    @Test
    void calculationOxygenDecimal() {
        assertEquals(0.32, diveFormulas.calculationOxygenDecimal(32));
        assertNotEquals(diveFormulas.calculationOxygenDecimal(25), 0.23, 0.0);
    }
}