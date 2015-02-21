# Playing-With-Enums-in-Java
Playing with Enums in Java

public class dayEnum {

	public enum Day {
	    SUNDAY, MONDAY, TUESDAY, WEDNESDAY,
	    THURSDAY, FRIDAY, SATURDAY;
	    
	    public int dayNumber()
	    {
	    	return this.ordinal();
	    }
	}
	
	Day d;
	
	public Day getDayEnum(){
		return d;
	}

	
	public int numberDay(Day day) {
        switch (day) {
            case MONDAY:
                return 1;
                    
            case TUESDAY:
                return 2;
            case WEDNESDAY:
                return 3;
            case THURSDAY:
                return 4;
            case FRIDAY:
                return 5;
                         
            case SATURDAY:
            	return 6;
            case SUNDAY:
                return 7;
                        
            default:
            	//error
                return 0;
        }
    }
}


import static org.junit.Assert.*;

import org.junit.Test;



public class dayEnumTest {

	dayEnum dayE = new dayEnum();
	
	@Test
	public void test() {
		assertEquals(dayE.numberDay(dayE.getDayEnum().MONDAY),1);
		assertEquals(dayE.numberDay(dayE.getDayEnum().WEDNESDAY),3);
		
		//due to order they were entered they are in the correct order 1-7 to be the date 
		assertEquals(dayE.getDayEnum().MONDAY.dayNumber(),1);
	}

}
