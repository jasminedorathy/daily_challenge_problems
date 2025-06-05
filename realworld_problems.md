## Day 39 - Problem Solving for the day - 08.04.2025  
## You are given a function, Void *ReplaceCharacter(Char str[], int n, char ch1, char ch2); The function accepts a string  ‘ str’ of length n and two characters ‘ch1’ and ‘ch2’ as its arguments . Implement the function to modify and return the string ‘ str’ in such a way that all occurrences of ‘ch1’ in original string are replaced by ‘ch2’ and all occurrences of ‘ch2’  in original string are replaced by ‘ch1’. Assumption: String Contains only lower-case alphabetical letters. 
## Note: 
## Return null if string is null. 
## If both characters are not present in string or both of them are same, then return the string unchanged. 
## Example: 
## Input: 
Str: apples 
ch1:a 
ch2:p 
## Output: 
paales

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the string");
		String str=s.nextLine();
		System.out.println("Enter the two character");
		char ch1=s.next().charAt(0);
		char ch2=s.next().charAt(0);
		if(str==null)
		{
		    System.out.println("null");
		}
		if(ch1==ch2)
		{
		    System.out.println(str);
		}
		StringBuilder sb=new StringBuilder();
		for(char c:str.toCharArray())
		{
		    if(c==ch1)
		    {
		        sb.append(ch2);
		        
		    }
		    else if(c==ch2)
		    {
		        sb.append(ch1);
		    }
		    else{
		        sb.append(c);
		    }
		}
		System.out.println(sb.toString());
		
	}
}


OUTPUT:

Enter the string
apple
Enter the two character
a
p
paale

````

##  Day 38 - Problem Solving for the day - 07.04.2025  
## A carry is a digit that is transferred to left if sum of digits exceeds 9 while adding two numbers from right-to-left one digit at a time You are required to implement the following function. Int NumberOfCarries(int num1 , int num2); The functions accepts two numbers ‘num1’ and ‘num2’ as its arguments. You are required to calculate and return  the total number of carries generated while adding digits of two numbers ‘num1’ and ‘ num2’. Assumption: num1, num2>=0 
## Example: 
## Input 
Num 1: 451 
Num 2: 349 
## Output 
2

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the number 1");
		int n1=s.nextInt();
		System.out.println("Enter the number 2");
		int n2=s.nextInt();
		int carry=0;
		int count=0;
		while(n1>0 || n2>0)
		{
		    int d1=n1%10;
		    int d2=n2%10;
		    int sum=d1+d2+carry;
		    if(sum>=10)
		    {
		        carry=1;
		        count++;
		        
		    }
		    else{
		        carry=0;
		    }
		    n1/=10;
		    n2/=10;
		}
		System.out.println("count of the carry "+count);
	
	}
}

OUTPUT:
Enter the number 1
5892
Enter the number 2
3108
count of the carry 3

````


##  Day 37 - Problem Solving for the day - 05.04.2025 
 
## Selection of MPCS exams include a fitness test which is conducted on ground. There will be a batch of 3 trainees, appearing for running test in track for 3 rounds. You need to record their oxygen level after every round. After trainee are finished with all rounds, calculate for each trainee his average oxygen level over the 3 rounds and select one with highest oxygen level as the most fit trainee. If more than one trainee attains the same highest average level, they all need to be selected. 
 
## Display the most fit trainee (or trainees) and the highest average oxygen level. 
 
## Note: 
The oxygen value entered should not be accepted if it is not in the range between 1   and 100. 
If the calculated maximum average oxygen value of trainees is below 70 then declare the trainees as unfit with meaningful message as “All trainees are unfit. 
 
## Average Oxygen Values should be rounded. 
 
## Example 1: 
## INPUT VALUES 
95 
92 
95 
92 
90 
92 
90 
92 
90 
 
## OUTPUT VALUES 
Trainee Number : 1 
Trainee Number : 3 
 
## Note: 
Input should be 9 integer values representing oxygen levels entered in order as   
## Round 1 
Oxygen value of trainee 1 
Oxygen value of trainee 2 
Oxygen value of trainee 3 
 
## Round 2 
Oxygen value of trainee 1 
Oxygen value of trainee 2 
Oxygen value of trainee 3 
## Round 3 
Oxygen value of trainee 1 
Oxygen value of trainee 2 
Oxygen value of trainee 3 
Output must be in given format as in above example. For any wrong input final output should display “INVALID INPUT”

````JAVA[]

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter the oxygen level for each round:");
        
        int[][] oxygen = new int[3][3];
        boolean isValid = true;

        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                int input = s.nextInt();
                if (input < 1 || input > 100) {
                    isValid = false;
                }
                oxygen[i][j] = input;
            }
        }

        if (!isValid) {
            System.out.println("INVALID INPUT");
            return;
        }

        int[] avg = new int[3];
        for (int t = 0; t < 3; t++) {
            int sum = 0;
            for (int r = 0; r < 3; r++) {
                sum += oxygen[r][t];
            }
            avg[t] = Math.round(sum / 3.0f);
        }

        int maxAverage = avg[0];
        for (int i = 1; i < avg.length; i++) {
            maxAverage = Math.max(maxAverage, avg[i]);
        }
        if (maxAverage < 70) {
            System.out.println("All trainees are unfit");
        } else {
            for (int i = 0; i < 3; i++) {
                if (avg[i] == maxAverage) {
                    System.out.println("Trainee Number : " + (i + 1));
                }
            }
        }
    }
}


OUTPUT:

Enter the oxygen level for each round:
95
92
95
92
90
92
90
0 92
90
Trainee Number : 1
Trainee Number : 3

````

##  Day 36 - Problem Solving for the day - 04.04.2025 
  
## Particulate matters are the biggest contributors to Delhi pollution. The main reason behind the increase in the concentration of PMs include vehicle emission by applying Odd Even concept for all types of vehicles. The vehicles with the odd last digit in the registration number will be allowed on roads on odd dates and those with even last digit will on even dates. Given an integer array a[], contains the last digit of the registration number of N vehicles traveling on date D(a positive integer). The task is to calculate the total fine collected by the traffic police department from the vehicles violating the rules. 
 
## Note : For violating the rule, vehicles would be fined as X Rs. 
 
## Example 1: 
 
## Input :  
4 -> Value of N 
 
{5,2,3,7} -> a[], Elements a[0] to a[N-1], during input each element is separated by a 
new line 
 
12 -> Value of D, i.e. date  
 
200 -> Value of x i.e. fine 
 
## Output : 
 
600  -> total fine collected

````java[]

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
       int n=s.nextInt();
       int[] a=new int[n];
       System.out.println("Enter the element");
       for(int i=0;i<n;i++)
       {
           a[i]=s.nextInt();
       }
       System.out.println("Enter the date");
       int d=s.nextInt();
       System.out.println("Enter the fine amount ");
       int x=s.nextInt();
       int totalfine;
       if(d%2==0)
       {
           int count=0;
           for(int i=0;i<n;i++)
           {
               if(a[i]%2 !=0)
               {
                   count++;
               }
               
           }
            totalfine=x*count;
       }
       else{
            int count1=0;
           for(int i=0;i<n;i++)
           {
               if(a[i]%2 ==0)
               {
                   count1++;
               }
               
           }
           totalfine=x*count1;
           
       }
       System.out.println("Total fine "+ totalfine);
    }
}


OUTPUT:

4
Enter the element
5
2
3
7
Enter the date
12
Enter the fine amount 
200
Total fine 600

````
## Day 35 - Problem Solving for the day - 03.04.2025  
## There are total n number of Monkeys sitting on the branches of a huge Tree. As travelers offer Bananas and Peanuts, the Monkeys jump down the Tree. If every Monkey can eat k Bananas and j Peanuts. If total m number of Bananas and p number of Peanuts are offered by travelers, calculate how many Monkeys remain on the Tree after some of them jumped down to eat. At a time one Monkeys gets down and finishes eating and go to the other side of the road. The Monkey who climbed down does not climb up again after eating until the other Monkeys finish eating. Monkey can either eat k Bananas or j Peanuts. If for last Monkey there are less than k Bananas left on the ground or less than j Peanuts left on the ground, only that Monkey can eat Bananas(<k) along with the Peanuts(<j). Write code to take inputsas n, m, p, k, j and return  the number of Monkeys left on the Tree.
## Where, n= Total no of Monkeys 
## k= Number of eatable Bananas by Single Monkey (Monkey that jumped down last may get less than k Bananas) 
## j = Number of eatable Peanuts by single Monkey(Monkey that jumped down last may get less than j Peanuts) 
## m = Total number of Bananas 
## p  = Total number of Peanuts 
 
## Remember that the Monkeys always eat Bananas and Peanuts, so there is no possibility of k and j having a value zero 
 
## Example 1: 
## Input Values     
20 
2 
3 
12 
12 
 ## Output Values 
 
Number of  Monkeys left on the tree:10 
 
## Note: Kindly follow  the order of inputs as n,k,j,m,p as given in the above example. 
And output must include  the same format  as in above example(Number of Monkeys left on the Tree:)
For any wrong input display INVALID INPUT

````java[]

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter the total number of monkey");
       int n=s.nextInt();
       System.out.println("Enter the Number of eatable Bananas by Single Monkey ");
       int k=s.nextInt();
       System.out.println("Enter the Number of eatable peanuts by Single Monkey ");
       int j=s.nextInt();
       System.out.println("Enter the total number of banana");
       int m=s.nextInt();
       
       System.out.println("Enter the total number of peanuts");
       int p=s.nextInt();
       
       if(m<=0 || k<=0 || j<=0 ||p<=0 )
       {
           System.out.println("Invalid input");
       }
       int left=n;
       for(int i=0;i<n;i++)
       {
           if(m>=k)
           {
               m-=k;
               left--;
           }
           else if(p>=j)
           {
               p-=j;
               left--;
           }
           else {
               break;
           }
       }
       System.out.println("Number of  Monkeys left on the tree: "+ left);
       
    }
}


OUTPUT:

Enter the total number of monkey
20
Enter the Number of eatable Bananas by Single Monkey 
2
Enter the Number of eatable peanuts by Single Monkey 
3
Enter the total number of banana
12
Enter the total number of peanuts
12
Number of  Monkeys left on the tree: 10

````

## Day 34 - Problem Solving for the day - 02.04.2025  
## There is a JAR full of candies for sale at a mall counter. JAR has the capacity N, that is JAR can contain maximum N candies when JAR is full. At any point of time. JAR can have M number of Candies where M<=N. Candies are served to the customers. JAR is never remain empty as when last k candies are left. JAR if refilled with new candies in such a way that JAR get full. Write a code to implement above scenario. Display JAR at counter with available number of candies. Input should be the number of candies one customer can order at point of time. Update the JAR after each purchase and display JAR at Counter. Output should give number of Candies sold and updated number of Candies in JAR. If Input is more than candies in JAR, return: “INVALID INPUT” 
## Given, 
## N=10, where N is NUMBER OF CANDIES AVAILABLE 
## K =< 5, where k is number of minimum candies that must be inside JAR ever. 
## Example 1:(N = 10, k =< 5) 
Input Value 
3 
Output Value 
NUMBER OF CANDIES SOLD : 3 
NUMBER OF CANDIES LEFT : 7 
## Example 2 : (N=10, k<=5) 
Input Value 
0 
Output Value 
INVALID INPUT 
NUMBER OF CANDIES LEFT : 10

````java[]

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter the candies to you want purchase");
       int or=s.nextInt();
       int n=10;
       int k=5;
       int jar=n;
       if(or<=0 || or>=n)
       {
           System.out.println("Invalid input");
           System.out.println("NUMBER OF CANDIES LEFT : "+jar);
       }
       else 
       {
           jar-=or;
           System.out.println("NUMBER OF CANDIES SOLD : "+or);
           if(jar<=k)
           {
               jar=n;
           }
            System.out.println("NUMBER OF CANDIES LEFT : "+jar);
       }
       
    }
}


OUTPUT:

Enter the candies to you want purchase
3
NUMBER OF CANDIES SOLD : 3
NUMBER OF CANDIES LEFT : 7

````

## Day 33 - Problem Solving for the day - 31.03.2025  
## Remove the N-th node from the end of a singly linked list. 
## Sample Input : 1 -> 2 -> 3 -> 4 -> 5 and n = 2  (Approach: Use two pointers to find the N-th node from the end)

````java[]

package sample;

import java.util.*;
class Node{
	int data;
	Node next;
	Node(int data)
	{
		this.data=data;
		this.next=null;
		}
}
 class Linkedlist
{  
	 Node head,tail;
	public void insertatbegin(int data)
	{
		Node newnode=new Node(data);
		if(head==null)
		{
			head=newnode;
		}
		else
		{
			newnode.next=head;
			head=newnode;
		}
	}
	public void insertatend(int data)
	{
		Node newnode=new Node(data);
		if(head==null)
		{
			head=newnode;
			tail=newnode;
		}
		else
		{
			tail.next=newnode;
			tail=newnode;
		}
	}
	
	
	public void display()
	{
		Node temp=head;
		while(temp!=null)
		{
			System.out.print(temp.data+" ");
			temp=temp.next;
		}
	}
	public Node finddel(int n)
	{
		Node dummy=new Node(0);
		dummy.next=head;
		Node first=dummy;
		Node second=dummy;
		for(int i=0;i<=n;i++)
		{
			first=first.next;
		}
		while(first!=null)
		{
			first=first.next;
			second=second.next;
		}
		second.next=second.next.next;
		return dummy.next;
		
	}
}
public class Main{

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		Linkedlist obj=new Linkedlist();
		System.out.println("Enter the element");
		while(true)
		{
			int val=s.nextInt();
			if(val==-1)
			{
				break;
			}
			obj.insertatend(val);
		}
		obj.display();
		System.out.println("\nEnter the n value");
		int n=s.nextInt();
		System.out.println("After Delete nth element");
		obj.finddel(n);
		obj.display();
		
	}

}


OUTPUT:

Enter the element
1
2
3
4
5
-1
1 2 3 4 5 
Enter the n value
2
After Delete the element
1 2 3 5

`````

##   Day 32 - Problem Solving for the day - 29.03.2025  
## Write a java program to find the middle element in singly linked list  
## Sample Input : 
## Linked List: 1 -> 2 -> 3 -> 4 -> 5

````JAVA[]

package sample;

import java.util.*;
class Node{
	int data;
	Node next;
	Node(int data)
	{
		this.data=data;
		this.next=null;
		}
}
 class Linkedlist
{  
	 Node head,tail;
	public void insertatbegin(int data)
	{
		Node newnode=new Node(data);
		if(head==null)
		{
			head=newnode;
		}
		else
		{
			newnode.next=head;
			head=newnode;
		}
	}
	public void insertatend(int data)
	{
		Node newnode=new Node(data);
		if(head==null)
		{
			head=newnode;
			tail=newnode;
		}
		else
		{
			tail.next=newnode;
			tail=newnode;
		}
	}
	
	
	public void display()
	{
		Node temp=head;
		while(temp!=null)
		{
			System.out.print(temp.data+" ");
			temp=temp.next;
		}
	}
	
	public int middle( )
	{
		Node slow=head;
		Node fast=head;
		while(fast!=null && fast.next!=null)
		{
			slow=slow.next;
			fast=fast.next.next;
		}
		return slow.data;
	}
}
public class Main{

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		Linkedlist obj=new Linkedlist();
		System.out.println("Enter the element");
		while(true)
		{
			int val=s.nextInt();
			if(val==-1)
			{
				break;
			}
			obj.insertatend(val);
		}
		obj.display();
		System.out.println("\nMiddle element of the list "+obj.middle())
	}
}

OUTPUT:

Enter the element
20
30
40
50
60
70
-1
20 30 40 50 60 70
Middle element of the list 50

`````

## Day 31 - Problem Solving for the day - 28.03.2025  
## The company uses a system that tracks the delivery of packages in a sequence of locations (represented as an array). Each location is identified by an integer (e.g., 1 for Location 1, 2 for Location 2, etc.). Due to a change in the delivery route, the system needs to shift (rotate) the locations by a certain number of positions. Given an array of integers representing the delivery route, you need to rotate the array by K positions to the right. If K is negative, the rotation should be to the left. For example, rotating an array [1, 2, 3, 4, 5] by 2 positions results in [4, 5, 1, 2, 3]. 
## Sample Input 01 : 
Enter the number of delivery locations: 5 
Enter the delivery locations (integers): 1 2 3 4 5 
Enter the number of positions to rotate: 2 
## Sample Input 02 : ( Negative Rotation ) 
Enter the number of delivery locations: 6 
Enter the delivery locations (integers):  10 20 30 40 50 60 
Enter the number of positions to rotate: -3


````java[]

package sample;
import java.util.*;
public class Main2 {

	public static void leftrotate(int a[],int d,int n)
	{
		d%=n;
		reverse(a,0,d-1);
		reverse(a,d,n-1);
		reverse(a,0,n-1);
	}
	public static void rightrotate(int a[],int d,int n)
	{
		d%=n;		
		reverse(a,n-d,n-1);
		reverse(a,0,n-d-1);
		reverse(a,0,n-1);
	}
	public static void reverse(int[] a,int start,int end)
	{
		while(start<end)
		{
			int temp=a[start];
			a[start]=a[end];
			a[end]=temp;
			start++;
			end--;
		}
	}
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
         System.out.println("Enter the number of delivery locations: ");
         int n=s.nextInt();
         int[] a=new int[n];
         System.out.println("Enter the delivery locations (integers): ");
         for(int i=0;i<n;i++)
         {
        	 a[i]=s.nextInt();
         }
         System.out.println("Enter the number of positions to rotate: ");
         int k=s.nextInt();
         if(k>0) {
        	 rightrotate(a,k,n);
        	 
         }
         else
         {
        	 leftrotate(a,-k,n);
        	
         }
         System.out.println(Arrays.toString(a)); 
	}

}


OUTPUT:
Enter the number of delivery locations: 
6
Enter the delivery locations (integers): 
10
20
30
40
50
60
Enter the number of positions to rotate: 
-3
[40, 50, 60, 10, 20, 30]


````

##  Day 30 - Problem Solving for the day - 27.03.2025  
## Write a java program to count the number of substrings that match a given condition.( Only Vowels) 
## Sample Input : 
Enter a string: aeio 
Enter a string: hello 
Enter a string: education 
Enter a string: aeiou

````java[]

package sample;
import java.util.*;
public class Main3 {
public static boolean isvowel(char ch)
{
	return "aeiouAEIOU".indexOf(ch) !=-1;
}
public static int countsub(String str)
{
	int count=0;
	int n=str.length();
	for(int i=0;i<n;i++)
	{
		if(!isvowel(str.charAt(i)))
		{
			continue;
		}
		for(int j=i;j<n;j++)
		{
			if(isvowel(str.charAt(j)))
			{
				count++;
			}
			else {
				break;
			}
		}	
	}
	return count;
	
}
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the string ");
		String str=s.nextLine();
		int res=countsub(str);
		System.out.println(" Number of substring given string "+res);		
	}
}

OUTPUT:

Enter the string 
hello
Number of substring given string 2

````

##  Day 29 - Problem Solving for the day - 26.03.2025  
## Write a java program to remove all whitespace characters from a given string. 
## Sample input  : 
"  Java  Programming   is   Awesome   " 
"   Remove   spaces   from  here!    " 
"Multiple   spaces    between   words" 
"  Hello World  " 

````java[]

package sample;
import java.util.*;
public class Main3 {

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the string ");
		String str=s.nextLine();
		String res=str.replaceAll("\\s+", "");
		System.out.println(" After remove the whitescpace "+res);
	}

}
OUTPUT:

Enter the string 
"  Java  Programming   is   Awesome   " 
 After remove the whitescpace "JavaProgrammingisAwesome"

````

##  Day 28 - Problem Solving for the day - 25.03.2025  
## Write a java program to count how many times a given character appears in a string. 
## Sample Input  : 
1) Enter a string: programming 
Enter a character to count: g 
2) Enter a string: java programming 
Enter a character to count: a 
3) Enter a string: hello there 
Enter a character to count: e 
4) Enter a string: quick brown fox 
Enter a character to count: o

````java[]

package sample;
import java.util.*;
public class Main3 {

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the string ");
		String str=s.nextLine();
		System.out.println("Enter the character ");
		char ch=s.next().charAt(0);
		int count=0;
		for(int i=0;i<str.length();i++)
		{
			if(str.charAt(i)==ch)
			{
				count++;
			}
		}
		System.out.println(" count of the character occurence "+count);
	}

}


OUTPUT:

Enter the string 
programming 
Enter the character 
g
count of the character occurence 2

Enter the string 
hello there 
Enter the character 
e
count of the character occurence 3

````
## Day 27 - Problem Solving for the day - 24.03.2025 
## Check if two strings are anagrams (contain the same characters in a different order).  
## Sample Input  : 
1) String str1 = "listen"; 
String str2 = "silent"; 
2) String str1 = "aabbcc"; 
String str2 = "abcabc"; 
3) String str1 = "rat"; 
String str2 = "car"; 
4) String str1 = "hello"; 
String str2 = "world";

````java[]

package sample;
import java.util.*;
public class Main3 {

	 
	  
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		System.out.println("Enter the string 1");
		String str=s.nextLine();
		System.out.println("Enter the string 2 ");
		String str1=s.nextLine();
        str=str.toLowerCase();
        str1=str1.toLowerCase();
        if(str.length()==str1.length()) {
        	char[] c1=str.toCharArray();
        	char[] c2=str.toCharArray();
        	
        	Arrays.sort(c1);
        	Arrays.sort(c2);
        	boolean res=Arrays.equals(c1, c2);
        	if(res)
    		{
    			System.out.println("Anagram");
    		}
    		else {
    			System.out.println("Not anagram ");
    		}
        }
        else {
        	System.out.println("Not anagram");
        }
		
	}

}


OUTPUT:

Enter the string 1
listen
Enter the string 2 
silent
Anagram

````

## Day 26 - Problem Solving for the day - 23.03.2025 
## Create a online store’s inventory management system. The system needs to find which products are currently available in two different warehouses. Each warehouse has its own inventory list, and you need to identify which products are common in both warehouses. Given two arrays of integers representing the product IDs available in two different warehouses, write a Java function that finds the intersection of these two arrays. The intersection should contain only the product IDs that are present in both arrays. The returned array should not have duplicates. 
## Example Input: 
## Warehouse 1 :  Inventory (Arr 1): [1, 2, 2, 1, 5, 7] 
## Warehouse 2 :  Inventory (Arr 2): [2, 2, 3, 4, 5, 6]

````java[]

package sample;
import java.util.*;
public class Main4 {

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
        int[] a=new int[n];
        System.out.println("Enter element array 1");
        for(int i=0;i<n;i++)
        {
        	a[i]=s.nextInt();
        }
        int n1=s.nextInt();
        int[] a1=new int[n];
        System.out.println("Enter element array 2");
        for(int i=0;i<n1;i++)
        {
        	a1[i]=s.nextInt();
        }
        Set<Integer> unique=new HashSet<>();
        Set<Integer> res=new HashSet<>();
        for(int num:a)
        {
        	unique.add(num);
        }
        for(int num:a1)
        {
        	if(unique.contains(num))
        	{
        		res.add(num);
        	}
        }
        int j=0;
        int result[]=new int[res.size()];
        for(int num:res)
        {
        	result[j++]=num;
        }
        System.out.println(Arrays.toString(result));
        
	}

}

OUTPUT:
6
Enter element array 1
1
2
2
1
5
7
6
Enter element array 2
2
2
3
4
5
6
[2, 5]

````




