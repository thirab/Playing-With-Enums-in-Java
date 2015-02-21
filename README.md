# Playing-With-Enums-in-Java
Playing with Enums in Java


public class dayEnum {

	public enum Day {
	    SUNDAY(1), MONDAY(2), TUESDAY(3), WEDNESDAY(4),
	    THURSDAY(5), FRIDAY(6), SATURDAY(7);
	    
	    int theDate;
	    
	    //set the date on instatiation
	    private Day(int i){
	    	this.theDate=i;
	    }
	    
	    //this returns the day number as set by the ordinal ( order in which the days were mentioned. It starts at 0 (sunday).)
	    public int dayNumber()
	    {
	    	return this.ordinal()+1;
	    }
	    
	    //this returns the date as set when the Day Enum is created
	    public int getTheDate(){
	    	return this.theDate;
	    }
	    
	}
	
	Day d;
	
	public Day getDayEnum(){
		return d;
	}

	//switch statement to handle each day
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
