# LAB-3-COMPLETE

**LAB TASK 1**

**1.	Write a program which takes an integer value (k) as input and prints the sequence of numbers from k to 0 in descending order.**

package com.mycompany.lab3labtask1;

import java.util.*;
public class Lab3labtask1 {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter an integer (k): ");
        int k = scanner.nextInt();

        printDescending(k);
        
        scanner.close();
    }

    public static void printDescending(int k) {
        if (k < 0) {
            return; 
        }
        
        System.out.print(k + " ");
        
        printDescending(k - 1);
    }
}

**LAB TASK 2**

**2.	Write a program to reverse your full name using Recursion.**

package com.mycompany.lab3labtask2;

import java.util.*;
public class Lab3labtask2 {
    
    public static String reverse(String name) {
        if (name.isEmpty()) {
            return name;
        }
        return reverse(name.substring(1)) + name.charAt(0);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your full name: ");
        String fullName = scanner.nextLine();

        String reversedName = reverse(fullName);

        System.out.println("Reversed Name: " + reversedName);

    }
}

**LAB TASK 3**

**3.	Write a program to calculate the sum of numbers from 1 to N using recursion. N should be user input.**

package com.mycompany.lab3labtask3;
import java.util.*;
public class Lab3labtask3 {
 public static int calculateSum(int n) {

        if (n == 1) {
            return 1;
        }

        return n + calculateSum(n - 1);
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter a positive integer: ");
        int n = scanner.nextInt();
        
        if (n <= 0) {
            System.out.println("Please enter a positive integer.");
        } else {
            int sum = calculateSum(n);
            System.out.println("The sum of numbers from 1 to " + n + " is: " + sum);
        }
    }
}

**LAB TASK 4**

**4.	Write a recursive program to calculate the sum of elements in an array.**

package com.mycompany.lab3labtask4;


public class Lab3labtask4 {
public static int sumArray(int[] array, int n) {
    
        if (n <= 0) {
            return 0;
        }
  
        return array[n - 1] + sumArray(array, n - 1);
    }
    public static void main(String[] args) {
        int[] array = {2, 4, 6, 8, 10};
        int sum = sumArray(array, array.length);
        System.out.println("Sum of array elements: " + sum);
    }
}

**LAB TASK 5**

**5.	Write a recursive program to calculate the factorial of a given integer n.**

package com.mycompany.lab3labtask5;


public class Lab3labtask5 {

    public static void main(String[] args) {
        int n = 4; 
        int result = factorial(n);
        System.out.println("Factorial of " + n + " is: " + result);
    }

    public static int factorial(int n) {
      
        if (n == 0) {
            return 1;
        }
 
        return n * factorial(n - 1);
    }
}

**LAB TASK 6**

**6.	Write a program to count the digits of a given number using recursion.**

package com.mycompany.lab3labtask6;


public class Lab3labtask6 {

    public static void main(String[] args) {
       int number = 246810;
        int count = countDigits(number);
        System.out.println("Number of digits: " + count);
    }

    public static int countDigits(int num) {

        if (num == 0) {
            return 0;
        }

        return 1 + countDigits(num / 10);
    }
}

**HOME TASK 1**

**1.	Write a java program to find the N-th term in the Fibonacci series using Memoization.**

package com.mycompany.lab3hometask1;
import java.util.*;

public class Lab3hometask1 {

    private static long[] memo;

    public static long fibonacci(int n) {
    
        if (n <= 1) return n;


        if (memo[n] != -1) return memo[n];

        memo[n] = fibonacci(n - 1) + fibonacci(n - 2);
        return memo[n];
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the value of N: ");
        int n = scanner.nextInt();

        memo = new long[n + 1];
        for (int i = 0; i <= n; i++) {
            memo[i] = -1;
        }

        long nthFibonacci = fibonacci(n);
        System.out.println("The " + n + "-th Fibonacci number is: " + nthFibonacci);
    }
}

**HOME TASK 2**

**2.	Write a program to count the digits of a given number using recursion.**

package com.mycompany.lab3hometask2;

public class Lab3hometask2 {

    public static void main(String[] args) {
        int number = 246;
        int count = countDigits(number);
        System.out.println("Number of digits: " + count);
    }

    public static int countDigits(int num) {

        if (num == 0) {
            return 0;
        }

        return 1 + countDigits(num / 10);
    }
}

**HOME TASK 3**

**3.	Write a java program to check whether a given string is a palindrome or not. A palindrome is a string that reads the same forwards and backwards.Print "YES" if the string is a palindrome, otherwise print "NO".**

package com.mycompany.lab3hometask3;

public class Lab3hometask3 {
public static boolean isPalindrome(String str, int start, int end) {
        
        if (start >= end) {
            return true;
        }  
        if (str.charAt(start) != str.charAt(end)) {
            return false;
        }
        return isPalindrome(str, start + 1, end - 1);
    }
    public static void main(String[] args) {
        String input = "DaD";

        if (isPalindrome(input, 0, input.length() - 1)) {
            System.out.println("YES");
        } else {
            System.out.println("NO");
        }
    }
}

**HOME TASK 4**

**4.	Write a recursive program to find the greatest common divisor (GCD) of two numbers using Euclid's algorithm.**

package com.mycompany.lab3hometask4;

public class Lab3hometask4 {
    
public static int findGCD(int a, int b) {

        if (b == 0) {
            return a;
        }
        return findGCD(b, a % b);
    }

    public static void main(String[] args) {
        int num1 = 10;
        int num2 = 2;
        
        int gcd = findGCD(num1, num2);
        
        System.out.println("GCD of " + num1 + " and " + num2 + " is: " + gcd);
    }
}
