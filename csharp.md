C# provides a variety of data structures that can be used to store, manage, and manipulate collections of data. Here are some of the basic data structures in C# along with explanations and examples of how to use them:

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

Sure! Here are some common and useful functions and methods in C#:

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

