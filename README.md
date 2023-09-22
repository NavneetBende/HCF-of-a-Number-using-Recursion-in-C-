# HCF-of-a-Number-using-Recursion-in-C-

HCF of Two Numbers using Recursion in C++
 

Here, in this page we will discuss the program to find the HCF of Two numbers using recursion in C++. We are given with two numbers and need to find the HCF of the given two numbers.The HCF or the Highest Common Factor of two numbers is the largest common factor of two or more values.

Example :

Input : a = 96, b = 56
Output : HCF of 96 and 56 is 8.
HCF of two Numbers using Recursion in C++
Different Methods Discussed in this page :
We have discussed the following methods using recursion to find the HCF of given two numbers.

Method 1 :Recursive Euclidean Algorithm: Repeated Subtraction
Method 2: Modulo Recursive Euclidean Algorithm: Repeated Subtraction.
 
Method 1 :
This method is based on  Euclidean Algorithm.

Create a function say getHCF(int num1, int num2)
Check if (num1==0) then return num2,
Check if (num2==0) then return num1.
If(num1==num2) then return num1.//Base condition
Else check if (num1 > num2) return getHCF(num1 – num2, num2); Otherwise, return getHCF(num1, num2 – num1);

Euclidean Algorithm
HCF of two numbers doesn’t change if smaller number is subtracted from a bigger number
Code to find HCF of a Number using Recursion in C++
Run
#include<bits/stdc++.h>
using namespace std;

// Recursive function for repeated subtraction HCF calculation
int getHCF(int num1, int num2)
{
   if (num1 == 0)
      return num2;

   if (num2 == 0)
      return num1;

   // base case
   if (num1 == num2)
      return num1;

   if (num1 > num2)
      return getHCF(num1 - num2, num2);

   return getHCF(num1, num2 - num1);
}

int main()
{
   int num1 = 96, num2 = 56, HCF = 1;

   HCF = getHCF(num1, num2);

   cout<<"HCF of "<<num1<<" and "<<num2<<" is "<<HCF;

   return 0;
}
Output

HCF of 96 and 56 is 8
Method 2 :
It is similar to what we have seen in method 1. In Addition, we are using modulo operation to reduce the number of subtractions required and improve time complexity.

Create a function say getHCF(int num1, int num2) and simply
return b == 0? a :getHCF(b, a %b);

Code to find HCF of a Number using Recursion in C++
Run
#include<bits/stdc++.h>
using namespace std;

int getHCF(int a, int b)
{
  return b == 0 ? a : getHCF(b, a % b);
}

int main()
{
  int num1 = 96, num2 = 56, HCF;

  HCF = getHCF(num1, num2);

  cout<<"HCF of "<<num1<<" and "<<num2<<" is "<<HCF;

  return 0;
}
Output

HCF of 96 and 56 is 8
