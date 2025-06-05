

## 1)  Given two integers M and N, calculate the sum of the factorials of all the integers from M and N inclusive* .if M is greater than N , return 0 or display an appropriate message. 
## Test Case 01 : M = 3, N = 5 
## Test Case 02 : M = 0, N = 4 
## Test Case 03 : M = 5, N = 5 
## Test Case 04 : M = 6, N =4

````java[]
package ex;
import java.util.*;
public class main2 {
   
public static int fact(int n) {
     if(n==0 || n==1) {
        return 1;
  }
return n*fact(n-1);
}
public static void main(String[] args) {
	 
  Scanner s=new Scanner(System.in);
  int m=s.nextInt();
  int n=s.nextInt();
  if(m>n) {
	  System.out.println("Invalid input");
  }
  int sum=0;
  for(int i=m;i<=n;i++) {
	  sum+=fact(i);
  }
  System.out.println("sum of the factorial: "+ sum);
    
	}
	

}


output:

3
6
sum of the factorial: 870


````
 ## 2)  You are working for a Survey Analysis company, and your team has been given the task of analyzing survey responses. The survey asks participants to select their favorite color from a list of options, and you are provided with an array of integers where each integer represents the choice of a color. The goal is to find the majority color — the color that has been selected by more than half of the participants. A majority element in the array is defined as an element that appears more than n/2 times, where n is the length of the array. 

## Requirements: 
## You need to write a function findMajorityColor that takes in an array of integers representing survey results and returns the majority element (if it exists), or -1 if there is no majority element. 

## Input: 
## An array of integers, colors[], where each integer represents a survey response corresponding to a particular color. If the length of the array is n, then the function should find the element that occurs more than n/2 times. 
## Output: 
## The majority element (integer) if it exists. 
## If no majority element exists, return -1. 
## Constraints: 
## The array can have at most 10^5 elements. 
## Array elements are non-negative integers.


```java[]


import java.util.*;
public class Main {

	public static void main(String[] args) {
	    Scanner s=new Scanner(System.in);
	    int n=s.nextInt();
	    int[] a=new int[n];
	    for(int i=0;i<n;i++) {
	    	a[i]=s.nextInt();
	    }
	    int candidate=a[0];
	    int count=1;
	    for(int i=1;i<n;i++) {
	    	if(a[i]==candidate) {
	    		count++;
	    	}
	    	else {
	    		count--;
	    	}
	    	
	    	if(count==0) {
	    		candidate=a[i];
	    		count=1;
	    	}
	    }
	    count=0;
	    for(int num:a) {
	    	if(num==candidate) {
	    		count++;
	    	}
	    }
	    
	    int result=(count>n/2) ? candidate:-1;
	    System.out.println("Majority Element: "+ result);

	}

}

OUTPUT:
5
1
3
3
2
3
Majority Element: 3

`````
## 3) Find the kth largest and smallest number in an array 
## Task 1: Find the kth smallest score (You need to find the 3rd smallest score in this list.)
## Task 2: Find the kth largest score (You also need to find the 2nd largest score in this list.) 
## You have the following scores recorded for 10 participants:  (scores = [65, 89, 45, 72, 54, 91, 32, 77, 60, 82])

````java[]

package day;
import java.util.*;
public class Main1 {
  public static void main(String args[]) {
	  Scanner s=new Scanner(System.in);
	  int n=s.nextInt();
	  int[] a=new int[n];
	  for(int i=0;i<n;i++) {
		  a[i]=s.nextInt();
		  
	  }
	  System.out.println("Enter k value");
	  int k=s.nextInt();
	  for(int i=0;i<n;i++) {
		  for(int j=0;j<n;j++) {
			  if(a[i]<a[j]) {
				  int temp=a[i];
				  a[i]=a[j];
				  a[j]=temp;
			  }
		  }
	  }
	  System.out.println(k+"th largest Element:" + a[n-k]);
	  System.out.println(k+"th Smallest Element:" + a[k-1]);
  }
}


OUTPUT:

10
65
89
45
72
54
91
32
77
60
82
Enter k value
3
3th largest Element:82
3th Smallest Element:54

`````

## 4) FIND THE THIRD MAXIMUM ELEMENT
````JAVA[]

class Solution {
    public int thirdMax(int[] nums) {
        long max1=Long.MIN_VALUE;
        long max2=Long.MIN_VALUE;
        long max3=Long.MIN_VALUE;
        for(int num : nums){
            if(num>max1){
                max3 = max2;
                max2 = max1;
                max1 = num;
            }else if(max1>num && num>max2){
                max3 = max2;
                max2 = num;
            }else if(max2>num && num>max3){
                max3=num;
            }
        }
        return max3 != Long.MIN_VALUE ? (int) max3 : (int) max1;
    }
}

````

## 5) Find Original Array From Doubled Array 

## Problem Statement: A doubled array changed is formed from the original array after appending twice the value of each element in the original array and randomly shuffling elements in the updated original array. Given an array changed, return the original array if changed is a valid doubled array. Otherwise, return empty array. 
## Example:  Input: changed = [2,4,1,8] 

````java[]


package day;
import java.util.*;
public class Main2 {
  public static int[] findOriginalArray(int[] changed) {
 if (changed.length % 2 != 0) return new int[0];

Arrays.sort(changed); 

 Map<Integer, Integer> freqMap = new HashMap<>();
 for (int num : changed) {
    freqMap.put(num, freqMap.getOrDefault(num, 0) + 1);
 }

 int[] original = new int[changed.length / 2]; 
int index = 0;

for (int num : changed) {
    if (freqMap.get(num) == 0) continue; 
		            
   if (freqMap.getOrDefault(num * 2, 0) == 0) return new int[0]; 

   original[index++] = num; 
   freqMap.put(num, freqMap.get(num) - 1);
  freqMap.put(num * 2, freqMap.get(num * 2) - 1);
 }

return original;
 }

 public static void main(String[] args) {
 Scanner s=new Scanner(System.in);
 int n=s.nextInt();
 int a[]=new int[n];
  for(int i=0;i<n;i++) {
     a[i]=s.nextInt();
}
System.out.println(Arrays.toString(findOriginalArray(a))); // Output: [1, 4]
 }
}

OUTPUT:

4
6
3
9
18
[3, 9]

````

## 6)  The function accepts two positive integers ‘r’ and ‘unit’ and a positive integer array ‘arr’ of size ‘n’ as its argument ‘r’ represents the number of rats present in an area, ‘unit’ is the amount of food each rat consumes and each ith element of array ‘arr’ represents the amount of food present in ‘i+1’ house number, where 0 <= i. 
## Note: 
## Return -1 if the array is null. 
## Return 0 if the total amount of food from all houses is not sufficient for all the rats. 
## Computed values lie within the integer range. 
## Example: 
## Input: 
## r: 7 
## unit: 2 
## n: 8 
## arr: 2 8 3 5 7 4 1 2


````java[]

package day;
import java.util.*;
public class Main3 {
  
	
	public static int findHouse(int r,int unit,int n,int[] a) {
		if(n==0) {
			return -1;
		}
		int totalfoodrequire=r*unit;
		int totalfoodavailable=0;
		for(int num:a) {
			totalfoodavailable+=num;
		}
		if(totalfoodavailable<totalfoodrequire) {
			return -1;
		}
		int count=0;
		int sum=0;
		for(int num:a) {
			sum+=num;
			count++;
			if(sum>=totalfoodrequire) {
				return count;
			}
		}
		return 0;
	}
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int r=s.nextInt();
		int unit=s.nextInt();
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++) {
			a[i]=s.nextInt();
		}
		
		int result=findHouse(r,unit,n,a);
		System.out.println("Require House: " +result);
		

	}

}


OUTPUT:

7
2
8

2
8
3
5
7
4
1
2
Require House: 4

````

## 7)  Given  two integers M and N, calculate the  sum of the squares of all the prime numbers between from M and N inclusive.if M is greater than N , return 0 or display an appropriate message  
## Test Case 01 : M = 2, N = 10 
## Test Case 02 : M = 11, N = 20 
## Test Case 03 : M = 4, N = 4 
## Test Case 04 : M = 12, N = 8

````java[]

package day;
import java.util.*;
public class primeNumber {
  public static boolean isprime(int num) {
     if(num==0 || num==1) {
          return false;
   }
 for(int i=2;i<=num/2;i++) {
       if(num%i==0) {
          return false;
     }
  }
   return true;
  }
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int m=s.nextInt();
		int n=s.nextInt();
		if(m>n) {
		    System.out.println("Invalid input");
		    return;
		}
		int sum=0;
		for(int i=m;i<=n;i++) {
			if(isprime(i)) {
				sum +=i*i;
			}
			
		}
		System.out.println("Sum of Square of prime number between "+ m +" and "+ n +": "+ sum);

	}

}

OUTPUT:

11
20
Sum of Square of prime number between 11 and 20: 940


````

##  8) You are developing a system for an online bookstore. The system has different types of customers: regular customers, premium members, and admin users. The bookstore has the following rules for applying discounts: 
## Regular customers: 
If they have bought more than 5 books in the last 6 months, they get a 10% discount. 
Otherwise, they get no discount. 
## Premium members: 
If they have bought more than 10 books in the last 6 months, they get a 20% discount. 
If they have bought 5 to 10 books, they get a 15% discount. 
Otherwise, they get a 5% discount. 
## Admin users: 
Admins get a 30% discount regardless of their purchase history. 
## Your task is to create a Java program that calculates the discount for a customer based on their membership type and the number of books they've bought in the last 6 months. If the user is an admin, they should receive the admin discount immediately. Write a Java program using nested if statements to calculate and print the discount for each customer.


````java[]

package day;
import java.util.*;
public class Discount {

	public static void main(String[] args) {
	Scanner s=new Scanner(System.in);
	System.out.println("Enter the customer type(Admin/premium/regular)");
	String customer=s.nextLine().trim().toLowerCase();
	System.out.println("Enter how many books are purchased last 6 month ");
	int n=s.nextInt();
	double discount=0.0;
	if(customer.equals("admin")) {
		discount=30.0;
		
	}
	else if(customer.equals("premium")) {
		if(n>10) {
			discount=20.0;
		}
		else if(n>=5 && n<= 10) {
			discount=15.0;
		}
		else {
			discount=5.0;
		}
	}
	else if(customer.equals("regular")) {
		 if(n>5) {
			 discount=10.0;
			 
		 }
		 else {
			 discount=0.0;
		 }
	}
	else {
		System.out.println("Invalid customer");
		return;
	}
	System.out.println("Discount percentage "+ discount +"%");

	}

}


OUTPUT:

Enter the customer type(Admin/premium/regular)
premium 
Enter how many books are purchased last 6 month 
8
Discount percentage 15.0%


````

## 9)  Given  two integers M and N, calculate the product  of all odd integers from M and N inclusive.if M is greater than N , return 1 or display an appropriate message. 
## Test Case 1: M = 3, N =7  
## Test Case 02 : M = 2, N = 5 
## Test Case 03 : M = 6, N = 6


````java[]

package day;
import java.util.*;
public class Product {

	public static void main(String[] args) {
    Scanner s=new Scanner(System.in);
    int m=s.nextInt();
    int n=s.nextInt();
    int prod=1;
    if(m>n) {
    	System.out.println("Invalid input");
    	return;
    }
    for(int i=m;i<=n;i++) {
    	if(i%2!=0)
    	{
    		prod*=i;
    	}
    }
    System.out.println("Product of odd Integer range between "+ m+ " and "+n +": " + prod);

	}

}


OUTPUT:

3
7
Product of odd Integer range between 3 and 7: 105

````

## 10) Find Maximum Number of Meetings in a Room 
## Given a set of meetings with start and end times, determine the maximum number of meetings that can be scheduled in a single room. 
## input :  
## intervals[] =  ([(1, 4),(2, 5), (3, 6), (5, 8), (7, 9])

````JAVA[]

package day;
import java.util.*;
public class Comparing {

	public static int maximumNumber(int[][] interval) {
		Arrays.sort(interval,Comparator.comparingInt(a -> a[1]));
		int count = 0; 
        int lastEndTime = Integer.MIN_VALUE;;

        for (int[] meeting : interval) {
            if (meeting[0] >= lastEndTime) {
                count++;
                lastEndTime = meeting[1]; 
            }
        }
        return count;
	}
	public static void main(String[] args) {
	   Scanner s=new Scanner(System.in);
	   int m=s.nextInt();
	   int arr[][]=new int[m][2];
	   for (int i = 0; i < m; i++) {
           arr[i][0] = s.nextInt();  
           arr[i][1] = s.nextInt();  
       }
	   int result=maximumNumber(arr);
	   System.out.println("Maximum number of overlapping: "+ result);
	}

}

OUTPUT:
Enter number of meetings:
5
Enter start and end times:
 1 4
2 5
3 6
5 8
7 9

Maximum number of non-overlapping meetings: 2

````

## 11)  Count frequency of each element in the array 
## Problem statement: Given an array, we have found the number of occurrences of each element in the array. 
## Example 1: 
## Input: arr[] = {10,5,10,15,10,5}; 
## Example2:  
## Input: arr[] = {2,2,3,4,4,2};

````java[]


package day;
import java.util.*;
public class Main5 {

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++) {
			a[i]=s.nextInt();
			
		}
		boolean[] visited=new boolean[n];

	
		for(int i=0;i<n;i++) {
			if(visited[i]==true) {
				continue;
			}
			int count=1;
			for(int j=i+1;j<n;j++) {
				if(a[i]==a[j]) {
					visited[j]=true;
					count++;
				}
			}
			System.out.println(a[i] +": "+ count);
		}

	}

}

OUTPUT:

6
7
3
7
4
3
8
7: 2
3: 2
4: 1
8: 1

````

## 12)  Find Smallest integer made up of factors 
## Find the smallest integer value 'b'for the given value of 'a'.  If we multiply the digits of 'b', we should get the exact value of 'a'. Result 'b' must contain more than one digit. 
## If it is not possible Print Invalid as output. 
## Examples: 
## 1.Input: 10
   Output: 25
  Explanation: 2*5 = 10. Hence 25 is the smallest value for 10.
## 2.Input: 13
     Output: Invalid

````java[]

package day;
import java.util.*;
public class Factor {
    public static String fact(int a) {
    	if(a<10) {
			return String.valueOf(a + 10);
		}
    	ArrayList<Integer> factor=new ArrayList<>();
    	for(int i=9;i>=2;i--) {
    		while(a%i==0) {
    			factor.add(i);
    			a/=i;
    		}
    	}
    	if(a>1) {
    		System.out.println("Invalid");
    	}
    	Collections.sort(factor);
    	StringBuilder result=new StringBuilder();
    	for(int num: factor) {
    		result.append(num);
    	}
    	return result.toString();
    	
    }
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int a=s.nextInt();
	  String b=fact(a);
	  
		System.out.println(b);

	}

}


OUTPUT:

10
25
`````

##  13)   You are working as a software engineer for a popular online shopping platform. The company wants to optimize its recommendation system by providing the top-selling products to its users based on their sales data. The company has a list of sales data for various products, where each product has a total number of units sold. The company needs to know the Kth largest-selling product so that it can prioritize inventory and recommend these top products to the users. You are tasked with writing a program that finds the Kth largest-selling product based on the number of units sold. 
## Input: 
An array of integers, where each integer represents the number of units sold for 
each product. 
An integer K which represents the rank of the product you want to find (for example, 
if K=3, you want to find the 3rd largest-selling product). 
## Example: 
## Given the array of sales data salesData = [100, 200, 50, 400, 300] and K = 2, the 
## second-largest-selling product has sold 300 units. 
## Constraints: 
The array length can range from 1 to 10^5 elements. 
The sales data is guaranteed to be non-negative integers.

````java[]

package day;
import java.util.*;
public class Main8 {
  public static void main(String args[]) {
	  Scanner s=new Scanner(System.in);
	  int n=s.nextInt();
	  int[] a=new int[n];
	  for(int i=0;i<n;i++) {
		  a[i]=s.nextInt();
		  
	  }
	  System.out.println("Enter k value");
	  int k=s.nextInt();
	  for(int i=0;i<n;i++) {
		  for(int j=0;j<n;j++) {
			  if(a[i]<a[j]) {
				  int temp=a[i];
				  a[i]=a[j];
				  a[j]=temp;
			  }
		  }
	  }
	  System.out.println(k+"th largest Element:" + a[n-k]);
	 
  }
}

OUTPUT:
5
100
200
50
400
300
Enter k value
2
2th largest Element:300

````

## 14)  You have been hired by a software development company to help with a function that finds all pairs of integers in an array whose sum equals a specified target value. The company needs to ensure that the program handles duplicate pairs correctly, meaning that each unique pair should only be returned once, regardless of the order in which the numbers appear in the array. You are required to write a program that: Takes an array of integers and a target sum as input. Returns all unique pairs of integers in the array whose sum equals the target value. 
## Sample Input  : 
## arr = [10, 15, 3, 7, 5, -1, 1, 11] 
## target = 10

````java[]


package day;
import java.util.*;
public class Main9 {
	public static Set<List<Integer>> findPairs(int[] a, int target) {
		Arrays.sort(a);
		int n=a.length;
	      Set<List<Integer>> res=new HashSet<>();
	      int left=0;
	      int right=n-1;
	      while(left<=right) {
	    	  int sum=a[left]+a[right];
	    	  if(sum==target) {
	    		  res.add(Arrays.asList(a[left],a[right]));
	    		  left++;
	    		  right--;
	    	  }
	    	  else if(sum<target) {
	    		  left++;
	    	  }
	    	  else {
	    		  right--;
	    	  }
	      }
	      return res;
		
	}

	public static void main(String[] args) {
	Scanner s=new Scanner(System.in);
	int n=s.nextInt();
	int[] a=new int[n];
	for(int i=0;i<n;i++) {
		a[i]=s.nextInt();
	}
	int target=s.nextInt();
	Set<List<Integer>> pairs = findPairs(a, target);
    System.out.println("Unique pairs with sum " + target + ": " + pairs);
      

	}

}


OUTPUT:

8
10
15
3
7
5
-1
1
11
10
Unique pairs with sum 10: [[5, 5], [3, 7], [-1, 11]]

`````

## 14) write a java program to move all the zeros to the end in given array . 
## Input :  int[] arr = {0, -1, 0, 3, 0, -2, 0, -12, -1};

````java[]

package day;
import java.util.*;
public class Moveallzeros {

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++) {
			a[i]=s.nextInt();
		}
		
		int j=0;
		for(int i=0;i<n;i++) {
			if(a[i]!=0) {
				a[j++]=a[i];
			}
		}
			while(j<n) {
				a[j++]=0;
			}
		
		for(int i=0;i<n;i++) {
			System.out.print(a[i]+" ");
		}

	}

}


OUTPUT:

9
0
-1
0
3
0
-2
0
-12
-1
-1 3 -2 -12 -1 0 0 0 0

`````

## Day 18 - Develop  booking system for a hotel. The system calculates the final booking price for a guest based on several factors including the type of room, the length of stay, seasonality (peak or off-peak season), and whether the guest has any special discounts. The rules for pricing are as follows:

## Room Types:

Standard: $100 per night

Deluxe: $200 per night

Suite: $300 per night


## Stay Length:

Stay of 1-3 nights: No discount
Stay of 4-7 nights: 5% discount on the total room cost
Stay of 8+ nights: 10% discount on the total room cost


## Season:

Peak season: From December to February (higher prices)
Apply a 20% surcharge on the base room price.
Off-peak season: All other months (normal pricing)


## Discounts:

VIP Guests: If the guest is a VIP, they get an additional 15% discount on the final amount.
Special Discount Code: If the guest enters a valid discount code, they receive a 10% discount on the total room cost (this can be combined with other discounts)
## other Rules:

Cancellation Policy: If the guest cancels the booking within 48 hours of the check-in date, they will incur a 50% cancellation fee based on the total booking cost.
Taxes: A 12% tax is applied to the final price after any discounts but before the cancellation fee.

## Requirements:

Write an if-else block to calculate the total cost for the guest based on the inputs. Consider the room type, stay length, seasonality, VIP status, discount codes, and cancellation policy. Ensure that taxes are applied last, after all discounts but before cancellation fees.
````java[]

````

## Day 25 - Problem Solving for the day - 22.03.2025 
## Write a java program to convert string to Integer (without using Integer.parseInt) 
## Sample Inputs and Expected Outputs: 
## Positive integer: 
## Input: "12345" 
## Expected Output: 12345 
## Negative integer: 
## Input: "-6789" 
## Expected Output: -6789 
## Single digit positive number: 
## Input: "7" 
## Expected Output: 7 
##  digit negative number: 
## Input: "-3" 
## Expected Output: -3

````java[]


import java.util.*;
public class StringintoInt
{
	public static void main(String[] args) {
	  Scanner s=new Scanner(System.in);
	  String str=s.next();
	  int num=0;
	  int n=str.length();
	  for(int i=0;i<n;i++){
	      num=(num*10)+((int)str.charAt(i)-48);
	  }
	  System.out.println(num);
	
	}
}

OUTPUT:

123
123

````

##  Day 24 - Problem Solving for the day - 21.03.2025  
## Find the Missing Number in an Array Given an array containing n-1 integers where the integers are in the range 1 to n, find the missing number 
## Sample Input : 
## Arr = {1,2,3,5,6,7,8}

````java[]

import java.util.*;
public class Missingnumber
{
	public static void main(String[] args) {
	  Scanner s=new Scanner(System.in);
	  int n=s.nextInt();
	  int[] a=new int[n];
	  for(int i=0;i<n;i++){
	     a[i]=s.nextInt();
	 }
	 int res=(n*(n+1))/2;
	 int sum=0;
	 for(int i=0;i<n-1;i++){
	     sum+=a[i];
	 }
	  int missingnumber=res-sum;
	  System.out.println("missingnumber "+ missingnumber);
	
	}
}


OUTPUT:

8
1
2
3
5
6
7
8
9
missingnumber 4

````
##  Day 23 - Problem Solving for the day - 20.03.2025  
## Merge Two Sorted Arrays 
## Write a program to merge two sorted arrays into a single sorted array. 
## Example: 
Input:  
arr1 = {1, 3, 5},  
arr2 = {2, 4, 6}

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	  Scanner s=new Scanner(System.in);
	  int n=s.nextInt();
	  int m=s.nextInt();
	  int[] a=new int[n];
	  int[] b=new int[m];
	  int[] res=new int[m+n];
	  for(int x=0;x<n;x++){
	     a[x]=s.nextInt();
	 }
	 for(int x=0;x<m;x++){
	     b[x]=s.nextInt();
	     
	 }
	 int i=0,j=0,k=0;
	 while(i<n && j<m){
	     if(a[i]<b[j]){
	         res[k++]=a[i++];
	     }
	     else{
	         res[k++]=b[j++];
	     }
	 }
	 while(i<n){
	     res[k++]=a[i++];
	   
	 }
	 while(j<m){
	     res[k++]=b[j++];
	 }
	 System.out.println("Merged Sorted Array "+Arrays.toString(res));
	}
}

output:

3
3
1
3
5
2
4
6
Merged Sorted Array [1, 2, 3, 4, 5, 6]

````

## . Day 22 - Problem Solving for the day - 19.03.2025  
## Write a Java program to find the common elements between two arrays.. 
## Sample Input:  
Arr1 = {1,2,4,5,6} 
Arr2 ={4,5,2,7,8}

````java[]
import java.util.*;
public class Main
{
	public static void main(String[] args) {
	  Scanner s=new Scanner(System.in);
	  int n=s.nextInt();
	  int m=s.nextInt();
	  int[] a=new int[n];
	  int[] b=new int[m];
	  for(int x=0;x<n;x++){
	     a[x]=s.nextInt();
	 }
	 for(int x=0;x<m;x++){
	     b[x]=s.nextInt();
	     
	 }
	 System.out.println("Common Element");
    for(int i=0;i<n;i++){
        for(int j=0;j<m;j++){
            if(a[i]==b[j]){
                System.out.print(a[i]+" ");
            }
        }
    }
	}
}
OUTPUT:

5
5
1
2
4
5
6
4
5
2
7
8
Common Element
2 4 5
````
## 29. Day 19 - Problem  Solving for the day - 12.03.2025 
## Rearrange Positive and Negative Numbers 
## Write a program that rearranges the elements in an array so that positive and negative numbers are placed alternately.. 
## Sample input 01  
int[] arr = {1, -2, 3, -4, 5, -6, 7}; 
Sample input 02  
int[] arr = {1, -2, 3, -4, 5};
