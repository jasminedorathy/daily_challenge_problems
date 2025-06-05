## Day 69 - Problem Solving for the day - 08.05.2025
## You're working on a text simplification tool that removes duplicate characters for normalization.
## Remove all duplicate characters from a string and return the result in order of first appearance.
## Test case 01 :
Input  : "programming"
Output  : "progamin"

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		String str=s.next();
		HashSet<Character> set=new HashSet<>();
		StringBuilder sb=new StringBuilder();
		for(char c:str.toCharArray())
		{
		    if(!set.contains(c))
		    {
		        set.add(c);
		        sb.append(c);
		    }
		}
		System.out.println("After remove the duplicate character:"+sb.toString());
	}
}


OUTPUT:

PROGRAMMING
After remove the duplicate character:PROGAMIN

````
## Day 67 - Problem Solving for the day - 06.05.2025
## You are building a plagiarism detection system for a university. To compare student assignments, your system needs to analyze all possible substrings of a given string (such as a sentence or paragraph fragment) to look for similarities.  Your task is to write a function that, given a string, returns all possible substrings that can be formed from it.
## Note: A substring is a contiguous sequence of characters within a string. For a string of length n, there are n * (n + 1) / 2 possible substrings.
## Test case 01  :
## Input  :"xyz"
## Output  : ["x", "xy", "xyz", "y", "yz", "z"]
## Test case 02  :
## Input : "abc"
## Output : ["a", "ab", "abc", "b", "bc", "c"]

````java[]

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		String str=s.next();
		int n=str.length();
		List<String> res=new ArrayList<>();
		for(int i=0;i<n;i++)
		{
		  for(int j=i+1;j<=n;j++) 
		  {
		      res.add(str.substring(i,j));
		  }
		}
		System.out.println(res);
	}
}


OUTPUT:

xyz
[x, xy, xyz, y, yz, z]


`````

## Day 66 - Problem Solving for the day - 05.05.2025
## Ramya working as a software developer at a search engine company. Users frequently type in search queries, and your system suggests autocomplete results. To optimize autocomplete functionality, you are tasked with identifying the longest common prefix among a set of possible completions for a user's partial input. Your system receives a list of these suggestions, and you must write a function that returns the longest common prefix string that appears at the beginning of all given suggestions. If there is no common prefix, return an empty string.
## Test case 01  :
## Input : suggestions = {"interview", "internet", "internal", "interval"}
## output  : "inte"
## Test case 02  :
## Input : suggestions = {"dog", "racecar", "car"}
## output : ""

````java[]

import java.util.*;
public class Main
{
    public static String longest(String[] str)
    {
        if(str==null || str.length==0 )
        {
            return "";
        }
        StringBuilder sb=new StringBuilder();
        for(int i=0;i<str[0].length();i++)
        {
            char c=str[0].charAt(i);
            for(int j=1;j<str.length;j++)
            {
                if(i>=str[j].length() || str[j].charAt(i)!=c)
                {
                    return sb.toString();
                }
            }
            sb.append(c);
        }
        return sb.toString();
    }
	public static void main(String[] args) 
	{
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		 s.nextLine();
		System.out.println("Enter the string");
		String[] str=new String[n];
		for(int i=0;i<n;i++)
		{
		    str[i]=s.nextLine();
		}
		String result=longest(str);
		System.out.println("longest prefix substring: "+result);
	}
}

output:
3
Enter the string
interview 
internet
interval
longest prefix substring: inter

````
## Day 72 - Problem Solving for the day - 10.05.2025
## In a grammar-checking tool, you're required to detect if a given sentence uses all the letters of the alphabet at least once — also known as a pangram.Return true if the input is a pangram, else false.
## Test Case  :
## Input :"the quick brown fox jumps over a lazy dog"
## Output  : true

````java[]

package array;
import java.util.*;
public class Checksentence {
	public static boolean check(String s) {
		boolean[] res=new boolean[26];
		int count=0;
		for(char c:s.toCharArray())
		{
			if(c>='a' && c<='z')
			{
				int index=c-'a';
				if(!res[index])
				{
					res[index]=true;
					count++;
				}
			}
		}
		return count==26;
	}

	public static void main(String[] args) {
	Scanner s=new Scanner(System.in);
	System.out.println("Enter the string");
	String str=s.nextLine();
	boolean result=check(str);
	System.out.println("Is pangram? " +result);
	

	}

}

output:

Enter the string
"the quick brown fox jumps over a lazy dog"
Is pangram? true
````
## Day 65 - Problem Solving for the day - 04.05.2025 
## Pattern : Replace even numbers with their square
## Description: Square only the even elements.
## Sample Input: arr = [2,3,4]
## Sample Output: [4,3,16]

````java[]
package array;
import java.util.*;
public class Replacearray {
	public static int[] replace(int[] a,int n)
	{
		for(int i=0;i<n;i++)
		{
			if(a[i]%2==0)
			{
				a[i]=a[i]*a[i];
			}
		}
		return a;
	}

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
		int[] res=replace(a,n);
		System.out.println(Arrays.toString(res));

	}

}

output:
3
2
3
4
[4, 3, 16]

`````
## Day 64 - Problem Solving for the day - 03.05.2025 
## Pattern : Replace negative values with zero
## Description: Write a program to convert all negative elements to 0.
## Sample Input: arr = [1,-2,3,-4]
## Sample Output: [1,0,3,0]

````java[]

package array;

import java.util.Arrays;
import java.util.Scanner;

public class Replacenagative {

	public static int[] replace(int[] a,int n)
	{
		for(int i=0;i<n;i++)
		{
			if(a[i]<0)
			{
				a[i]=0;
			}
		}
		return a;
	}

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
		int[] res=replace(a,n);
		System.out.println(Arrays.toString(res));
	}
}

output:

4
1
-2
3
-4
[1, 0, 3, 0]
````

## Day 63 - Problem Solving for the day - 02.05.2025 
## Pattern : Find the sum of odd elements only
## Description: write a program to add only the odd values from the array.
## Sample Input: arr = [1,2,3,4]
## Sample Output: 4

```java[]

package array;

import java.util.*;

public class Sumofoddnumber {
	public static int replace(int[] a,int n)
	{
		int sum=0;
		for(int i=0;i<n;i++)
		{
			if(a[i]%2!=0)
			{
				sum+=a[i];
			}
		}
		return sum;
	}

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
		int res=replace(a,n);
		System.out.println(" sum of the odd number "+ res);
	}
}

OUTPUT:

4

1
2
3
4
 sum of the odd number 4

````
## Day 62 - Problem Solving for the day - 01.05.2025 
## Pattern : Find the sum of even elements only
## Description: Write a program to add only the even values from the array.
## Sample Input: arr = [1,2,3,4]
## Sample Output: 6

````JAVA[]

package array;

import java.util.*;

public class Sumofevennumber {
	public static int replace(int[] a,int n)
	{
		int sum=0;
		for(int i=0;i<n;i++)
		{
			if(a[i]%2==0)
			{
				sum+=a[i];
			}
		}
		return sum;
	}

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
		int res=replace(a,n);
		System.out.println(" sum of the even number "+ res);
	}
}

output:
4
1
2
3
4
 sum of the even number 6

````

## Day 60 - Problem Solving for the day - 29.04.2025
## Pattern : Rotate array to the right by 1
## Description:Write a program to shift all elements one place to the right.
## Sample Input: arr = [1,2,3,4]
## Sample Output: [4,1,2,3]

````java[]

package array;
import java.util.*;
import java.util.Scanner;

public class Rotatebyone {
	public static int[] rotate(int[] a,int n)
	{
		int last=a[n-1];
		for(int i=n-1;i>0;i--)
		{
			a[i]=a[i-1];
		}
		a[0]=last;
		return a;
	}

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
		int[] res=rotate(a,n);
		System.out.println("Rotate the array by one  "+ Arrays.toString(res));
	}
}

OUTPUT:

4
1
2
3
4
Rotate the array by one  [4, 1, 2, 3]

````
## Day 59 - Problem Solving for the day - 28.04.2025
## Pattern : Rotate array to the left by 1
## Description:write a program to shift all elements one place to the left.
## Sample Input: arr = [1,2,3,4]
## Sample Output: [2,3,4,1]

````java[]

package array;

import java.util.Arrays;
import java.util.Scanner;

public class Leftrotatebyone {
	public static int[] rotate(int[] a,int n)
	{
		int first=a[0];
		for(int i=0;i<n-1;i++)
		{
			a[i]=a[i+1];
		}
		a[n-1]=first;
		return a;
	}

	public static void main(String[] args) {
		Scanner s=new Scanner(System.in);
		int n=s.nextInt();
		int[] a=new int[n];
		for(int i=0;i<n;i++)
		{
			a[i]=s.nextInt();
		}
		int[] res=rotate(a,n);
		System.out.println("Rotate the array  left side by one  "+ Arrays.toString(res));
	}
}

OUTPUT:
4
1
2
3
4
Rotate the array  left side by one  [2, 3, 4, 1]
````




