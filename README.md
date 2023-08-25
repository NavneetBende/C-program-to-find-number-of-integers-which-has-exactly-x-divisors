# C-program-to-find-number-of-integers-which-has-exactly-x-divisors

Number of integers which has exactly X divisors using C
In this page we will learn how to find number of integers which has exactly x divisors using  C . Divisors are numbers which  perfectly divides a number.

Method Discussed :
Method 1 : Naive approach
Method 2 : Efficient approach
Method 1 :
Declare a variable count =0, to count the required numbers with x factors.
Run a loop for range 1 to n.
Inside that take a variable count_factors = 0, that will count the factors of ith.
Now, run a inner loop.
And increase the count_factors if it’s is factor of ith number.
Check if count_factors == X, then increment the count by 1.
At last print the count value.
Method 1 : Code in C
Run
//Write a program to count Number of integers which has exactly X divisors using C
#include <stdio.h>
#include <math.h>

int main(){
    
    int n=7, x=2;
    
    //Variable of count required numbers
    int count = 0;
    
    for(int i=1; i<=n; i++){
        
        //variable to count the factors of i-th number
        int count_factors = 0;
        for(int j = 1; j<= i; j++){
            if(i%j==0){
                    count_factors++;
            }
        }
        
        if(count_factors == x)
            count++;
    }
    
    printf("%d ", count);
}
Output :
4
Related Pages
Counting number of days in a given month of a year
 
Finding Number of times x digit occurs in a given input
 
Finding Roots of a quadratic equation

Power of a Number 

Prime Number

Method 2 :
In this method we will use the efficient way for counting the factors that used in method 1.

Method 2 : Code in C
Run
//Write a program to count Number of integers which has exactly X divisors using C
#include <stdio.h>
#include <math.h>


int main(){
    
    int n=7, x=2;
    
    //Variable of count required numbers
    int count = 0;
    
    for(int i=1; i<=n; i++){
        
        //variable to count the factors of i-th number
        int count_factors = 0;
        for(int j = 1; j<=sqrt(i); j++){
            if(i%j==0){
                if(i/j != j)
                    count_factors += 2;
                else
                    count_factors++;
            }
        }
        
        if(count_factors == x)
            count++;
    }
    
    printf("%d ", count);
}
Output :
4
