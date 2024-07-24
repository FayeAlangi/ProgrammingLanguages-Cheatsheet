C# provides a variety of data structures that can be used to store, manage, and manipulate collections of data. Here are some of the basic data structures in C# along with explanations and examples of how to use them:
## Data Structures
### 1. Arrays
Arrays are fixed-size collections of elements of the same type. They are indexed by integers.

#### Declaration and Initialization
```csharp
int[] numbers = new int[5]; // Declares an array of integers with 5 elements
int[] numbers = { 1, 2, 3, 4, 5 }; // Declares and initializes an array
```

#### Accessing Elements
```csharp
int firstNumber = numbers[0]; // Accesses the first element
numbers[1] = 10; // Sets the second element to 10
```

### 2. Lists
`List<T>` is a dynamic array that can grow in size. It is part of the `System.Collections.Generic` namespace.

#### Declaration and Initialization
```csharp
using System.Collections.Generic;

List<int> numbers = new List<int>(); // Declares an empty list of integers
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 }; // Declares and initializes a list
```

#### Adding and Removing Elements
```csharp
numbers.Add(6); // Adds an element to the list
numbers.Remove(3); // Removes the first occurrence of the specified element
numbers.RemoveAt(0); // Removes the element at the specified index
```

#### Accessing Elements
```csharp
int firstNumber = numbers[0]; // Accesses the first element
numbers[1] = 10; // Sets the second element to 10
```

### 3. Dictionaries
`Dictionary<TKey, TValue>` is a collection of key-value pairs. It is part of the `System.Collections.Generic` namespace.

#### Declaration and Initialization
```csharp
using System.Collections.Generic;

Dictionary<string, int> ageDictionary = new Dictionary<string, int>(); // Declares an empty dictionary
Dictionary<string, int> ageDictionary = new Dictionary<string, int>
{
    { "Alice", 30 },
    { "Bob", 25 }
}; // Declares and initializes a dictionary
```

#### Adding and Removing Elements
```csharp
ageDictionary.Add("Charlie", 35); // Adds a key-value pair to the dictionary
ageDictionary.Remove("Alice"); // Removes the element with the specified key
```

#### Accessing Elements
```csharp
int bobAge = ageDictionary["Bob"]; // Accesses the value associated with the specified key
ageDictionary["Bob"] = 26; // Sets the value associated with the specified key
```

### 4. Queues
`Queue<T>` is a first-in, first-out (FIFO) collection. It is part of the `System.Collections.Generic` namespace.

#### Declaration and Initialization
```csharp
using System.Collections.Generic;

Queue<int> queue = new Queue<int>(); // Declares an empty queue
```

#### Adding and Removing Elements
```csharp
queue.Enqueue(1); // Adds an element to the end of the queue
int firstElement = queue.Dequeue(); // Removes and returns the element at the beginning of the queue
```

#### Accessing Elements
```csharp
int firstElement = queue.Peek(); // Returns the element at the beginning of the queue without removing it
```

### 5. Stacks
`Stack<T>` is a last-in, first-out (LIFO) collection. It is part of the `System.Collections.Generic` namespace.

#### Declaration and Initialization
```csharp
using System.Collections.Generic;

Stack<int> stack = new Stack<int>(); // Declares an empty stack
```

#### Adding and Removing Elements
```csharp
stack.Push(1); // Adds an element to the top of the stack
int topElement = stack.Pop(); // Removes and returns the element at the top of the stack
```

#### Accessing Elements
```csharp
int topElement = stack.Peek(); // Returns the element at the top of the stack without removing it
```

### 6. HashSets
`HashSet<T>` is a collection that contains no duplicate elements. It is part of the `System.Collections.Generic` namespace.

#### Declaration and Initialization
```csharp
using System.Collections.Generic;

HashSet<int> set = new HashSet<int>(); // Declares an empty hash set
HashSet<int> set = new HashSet<int> { 1, 2, 3, 4, 5 }; // Declares and initializes a hash set
```

#### Adding and Removing Elements
```csharp
set.Add(6); // Adds an element to the set
set.Remove(3); // Removes the specified element from the set
```

#### Accessing Elements
```csharp
bool contains = set.Contains(2); // Checks if the set contains the specified element
```

## Common Functions

### String Manipulation
- **`Substring`**: Extracts a substring from a string.
  ```csharp
  string text = "Hello, world!";
  string result = text.Substring(7, 5); // "world"
  ```

- **`Replace`**: Replaces all occurrences of a specified substring with another substring.
  ```csharp
  string text = "Hello, world!";
  string result = text.Replace("world", "C#"); // "Hello, C#!"
  ```

- **`Split`**: Splits a string into an array of substrings based on a specified delimiter.
  ```csharp
  string text = "one,two,three";
  string[] parts = text.Split(','); // ["one", "two", "three"]
  ```

- **`Trim`**: Removes all leading and trailing whitespace characters from a string.
  ```csharp
  string text = "   Hello, world!   ";
  string result = text.Trim(); // "Hello, world!"
  ```

### Collection Handling
- **`Add`** (for `List<T>`): Adds an object to the end of the list.
  ```csharp
  List<string> list = new List<string>();
  list.Add("item1");
  ```

- **`Contains`** (for `List<T>`, `HashSet<T>`, etc.): Determines whether a collection contains a specific element.
  ```csharp
  List<string> list = new List<string> { "item1", "item2" };
  bool hasItem = list.Contains("item1"); // true
  ```

- **`Sort`** (for `List<T>`): Sorts the elements in the list.
  ```csharp
  List<int> numbers = new List<int> { 3, 1, 4, 1, 5 };
  numbers.Sort(); // [1, 1, 3, 4, 5]
  ```

### LINQ (Language Integrated Query)
- **`Where`**: Filters a sequence of values based on a predicate.
  ```csharp
  var numbers = new List<int> { 1, 2, 3, 4, 5 };
  var evenNumbers = numbers.Where(n => n % 2 == 0); // [2, 4]
  ```

- **`Select`**: Projects each element of a sequence into a new form.
  ```csharp
  var numbers = new List<int> { 1, 2, 3, 4, 5 };
  var squaredNumbers = numbers.Select(n => n * n); // [1, 4, 9, 16, 25]
  ```

- **`Aggregate`**: Applies an accumulator function over a sequence.
  ```csharp
  var numbers = new List<int> { 1, 2, 3, 4 };
  var sum = numbers.Aggregate((total, next) => total + next); // 10
  ```

### File Handling
- **`ReadAllText`**: Reads the contents of a file into a string.
  ```csharp
  string content = File.ReadAllText("file.txt");
  ```

- **`WriteAllText`**: Writes a string to a file.
  ```csharp
  File.WriteAllText("file.txt", "Hello, world!");
  ```

### Data Conversion
- **`Parse`**: Converts a string representation of a number to its numeric type.
  ```csharp
  int number = int.Parse("123"); // 123
  ```

- **`TryParse`**: Attempts to convert a string representation of a number to its numeric type and returns a boolean indicating success or failure.
  ```csharp
  bool success = int.TryParse("123", out int number); // success = true, number = 123
  ```
## Examples

#### 1. Sort Array By Increasing Frequency
Given an array of integers nums, sort the array in increasing order based on the frequency of the values. If multiple values have the same frequency, sort them in decreasing order.

Return the sorted array.
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
public class Solution {
    public int[] FrequencySort(int[] nums) {
        var frequencyDict = nums.GroupBy(n => n)
                                .ToDictionary(g => g.Key, g => g.Count());

     
        var sortedList = nums.OrderBy(n => frequencyDict[n])
                             .ThenByDescending(n => n)
                             .ToList();

        return sortedList.ToArray();
   
    }
}

```

#### 2. Two Sum
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

```csharp
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
        Dictionary<int,int> numDict= new Dictionary<int,int>();
        for (int i=0;i<nums.Length;i++){
            if (numDict.ContainsKey(target-nums[i])){
                return new[] { i,numDict[target-nums[i]]};
            }
            numDict[nums[i]]=i;
        }
        return [];
        
    }
}

```

#### 3. Palindrome Number

Given an integer x, return true if x is a palindrome, and false otherwise.

```csharp

public class Solution {
    public bool IsPalindrome(int x) {
        if ( x < 0 || (x!=0 && x%10==0)){return false;}
        int reversedNum=0;
        int originalNum=x;
        while (x > 0){
            reversedNum=reversedNum*10+x%10;
            x/=10;

        }
        return reversedNum==originalNum;
    }
}

```

#### 4.Greatest Common Divisor of Strings
For two strings s and t, we say "t divides s" if and only if s = t + t + t + ... + t + t (i.e., t is concatenated with itself one or more times).

Given two strings str1 and str2, return the largest string x such that x divides both str1 and str2.

```csharp
public class Solution {
    public string GcdOfStrings(string str1, string str2) {
        if (str1+str2!= str2+str1){
            return "";
        }
        int GCD (int a, int b){
            while (b!=0){
                int temp=a;
                a=b;
                b=temp%b;
            }
            return a;  
        }
        int gcd = GCD(str1.Length, str2.Length);

        return str1.Substring(0,gcd);
    }
}

```
#### 5.Kids With the Greatest Number of Candies
```csharp
using System;
using System.Linq;


public class Solution {
    public IList<bool> KidsWithCandies(int[] candies, int extraCandies) {

        List<bool> result= new List<bool>();
        int maxCandies= candies.Max();
        foreach (int candy in candies){
            if (candy+extraCandies >= maxCandies){
                result.Add(true);
            }
            else{
                result.Add(false);
            }
        }
        return result;
        
    }
}

```

#### 6. Can Place Flowers

```csharp
public class Solution {
    public bool CanPlaceFlowers(int[] flowerbed, int n) {
        int length=flowerbed.Length;
        for (int i=0;i<length;i++){
            if (flowerbed[i]==0){
                bool emptyLeft= (i==0 || flowerbed[i-1]==0);
                bool emptyRight= (i==length-1 || flowerbed[i+1]==0);
                if (emptyLeft && emptyRight){
                    flowerbed[i]=1;
                    n--;
                    if (n <=0){
                        return true;
                    }
                }
            
            }
        }
        return n<=0;
        
    }
}


```

#### 7. Reverse Vowels of a String


```csharp

using System;
using System.Collections.Generic;
public class Solution {
    public string ReverseVowels(string s) {
        int p1 = 0;
        int p2 = s.Length-1;
        char[] chars= s.ToCharArray();
        HashSet<char> vowels= new HashSet<char> {'a','e','i','o','u'};
        while (p1 < p2){
            while (p1 < p2 && !vowels.Contains(char.ToLower(chars[p1]))){
                p1++;
            }
            while (p1 < p2 && !vowels.Contains(char.ToLower(chars[p2]))){
                p2--;
            }
            (chars[p1],chars[p2])=(chars[p2],chars[p1]);
            p1++;
            p2--;
        }

        return String.Join("", chars);
        
    }
}
```

### Creating a Class in C#

```csharp
using System;
using System.Collections.Generic;

public class Report
{
    // Properties
    public string Title { get; set; }
    public DateTime CreatedDate { get; set; }
    public string Author { get; set; }
    public List<string> Metrics { get; set; } // Metrics being tracked
    public Dictionary<string, string> Filters { get; set; } // Filters for report data
    public string VisualizationType { get; set; } // e.g., "Bar Chart", "Pie Chart", etc.
    public string Content { get; set; } // Report content or summary

    // Constructor
    public Report(string title, string author)
    {
        Title = title;
        CreatedDate = DateTime.Now;
        Author = author;
        Metrics = new List<string>();
        Filters = new Dictionary<string, string>();
        VisualizationType = "Table"; // Default visualization type
        Content = string.Empty;
    }

    // Method to add a metric
    public void AddMetric(string metric)
    {
        Metrics.Add(metric);
    }

    // Method to add a filter
    public void AddFilter(string key, string value)
    {
        Filters[key] = value;
    }

    // Method to set content
    public void SetContent(string content)
    {
        Content = content;
    }

    // Method to display the report
    public void DisplayReport()
    {
        Console.WriteLine($"Title: {Title}");
        Console.WriteLine($"Created Date: {CreatedDate}");
        Console.WriteLine($"Author: {Author}");
        Console.WriteLine("Metrics:");
        foreach (var metric in Metrics)
        {
            Console.WriteLine($"- {metric}");
        }
        Console.WriteLine("Filters:");
        foreach (var filter in Filters)
        {
            Console.WriteLine($"- {filter.Key}: {filter.Value}");
        }
        Console.WriteLine($"Visualization Type: {VisualizationType}");
        Console.WriteLine("Content:");
        Console.WriteLine(Content);
    }
}

class Program
{
    static void Main()
    {
        // Create a new report
        Report report = new Report("Sales Performance", "John Doe");

        // Add metrics
        report.AddMetric("Total Sales");
        report.AddMetric("Conversion Rate");

        // Add filters
        report.AddFilter("Date Range", "Last 30 Days");
        report.AddFilter("Region", "North America");

        // Set content
        report.SetContent("This report provides an overview of sales performance and conversion rates over the last 30 days.");

        // Display the report
        report.DisplayReport();
    }
}

```