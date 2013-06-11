Divide-Two-Integers
===================


public class Solution {
    public int divide(int dividend, int divisor) {
        // Start typing your Java solution below
        // DO NOT write main() function
        if(divisor == 0) return 0;
        if(divisor == 1) return dividend;
        if(divisor == dividend) return 1;
        if(divisor == 2) return dividend >> 1;
        
        boolean sign = false;
        
        if(dividend >0 && divisor < 0 || dividend <0 && divisor >0)
        {
            sign = true;
        }
        
        //int div = Math.abs(dividend);
        //int divis= Math.abs(divisor);
        
        dividend = dividend == Integer.MIN_VALUE ? Integer.MAX_VALUE : Math.abs(dividend);
        divisor = divisor == Integer.MIN_VALUE ? Integer.MAX_VALUE : Math.abs(divisor);
        
        int result = (int)Math.floor(Math.pow(Math.E, Math.log(dividend) - Math.log(divisor)));
        
        return sign? -result:result;
    }
}
