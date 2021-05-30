# Factorial-of-Large-Number

Factorial of a non-negative integer, is the multiplication of all integers smaller than or equal to n. For example factorial of 6 is 6*5*4*3*2*1 which is 720.

![image](https://user-images.githubusercontent.com/22562694/120111111-3f830500-c18e-11eb-8f87-0bb3200db30d.png)

Factorial of 100 has 158 digits. It is not possible to store these many digits even if we use long long int. 
Examples : 

Input : 100
Output : 933262154439441526816992388562667004-
         907159682643816214685929638952175999-
         932299156089414639761565182862536979-
         208272237582511852109168640000000000-
         00000000000000

Input :50
Output : 3041409320171337804361260816606476884-
         4377641568960512000000000000
         
         
The following is a detailed algorithm for finding factorial.

factorial(n) 

1) Create an array ‘res[]’ of MAX size where MAX is number of maximum digits in output. 
2) Initialize value stored in ‘res[]’ as 1 and initialize ‘res_size’ (size of ‘res[]’) as 1. 
3) Do following for all numbers from x = 2 to n. 
……a) Multiply x with res[] and update res[] and res_size to store the multiplication result.

How to multiply a number ‘x’ with the number stored in res[]? 
The idea is to use simple school mathematics. We one by one multiply x with every digit of res[]. The important point to note here is digits are multiplied from rightmost digit to leftmost digit. If we store digits in same order in res[], then it becomes difficult to update res[] without extra space. That is why res[] is maintained in reverse way, i.e., digits from right to left are stored.

multiply(res[], x) 

1) Initialize carry as 0. 
2) Do following for i = 0 to res_size – 1 
….a) Find value of res[i] * x + carry. Let this value be prod. 
….b) Update res[i] by storing last digit of prod in it. 
….c) Update carry by storing remaining digits in carry. 
3) Put all digits of carry in res[] and increase res_size by number of digits in carry.         
