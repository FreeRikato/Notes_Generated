## Introduction to C++ STL

### What is STL?

- STL stands for Standard Template Library.
- It is a collection of pre-written C++ classes and functions that provide commonly used data structures and algorithms.
- STL is like a toolkit that provides reusable components to simplify and enhance C++ programming.

### Benefits of using STL:

- **Conciseness:** STL helps write shorter and more concise code.
- **Speed:** STL functions and containers are highly optimized, resulting in faster code execution.
- **Reliability:** STL code is thoroughly tested and free from errors, ensuring code stability.
- **Extensibility:** STL serves as a foundation for advanced data structures and algorithms used in various programming scenarios.

### Getting Started with STL

- Include the necessary header files:<br>
```cpp
#include <vector>
#include <set>
// ... (for other STL components)
```

### Basic STL Components

### Vectors

- A vector is a dynamic array, meaning its size can be adjusted at runtime.
- Vectors are useful for storing a collection of similar elements.

### Defining a Vector:

- **Empty vector:** `vector<int> v;`
- **Vector with initial size:** `vector<int> v(10);` // 10 elements initialized to 0
- **Vector with initial values:** `vector<char> v(10, 'H');` // 10 elements initialized to 'H'## Vectors: A Guide for Beginners

### Understanding Vectors

Vectors are dynamic data structures that store elements of the same type in a contiguous block of memory. They allow efficient insertion and deletion of elements at the end, and can dynamically change their size as needed.

### Creating and Initializing Vectors

To create an empty vector, use the syntax:

```cpp
vector<int> V; // Vector of integers
```

You can insert elements into the vector using the `push_back` function:

```cpp
V.push_back(5);
```

### Accessing and Modifying Elements

Elements in a vector can be accessed using their index. The first element has index 0:

```cpp
cout << V[0]; // Prints 5
``````cpp
cout << V[0]; // Prints 5
```

You can modify elements by assigning a new value to their index:

```cpp
V[0] = 6;
```

### Inserting and Deleting Elements

To insert an element at the end of the vector, use `push_back`:

```cpp
V.push_back(3);
```

To delete the last element, use `pop_back`:

```cpp
V.pop_back();
```

### Size and Capacity

The `size` method returns the number of elements in the vector:

```cpp
cout << V.size(); // Prints 2
```

The `capacity` method returns the total number of elements the vector can hold before it needs to allocate more memory:

```cpp
cout << V.capacity(); // Prints 2
```

### Clearing Vectors

To remove all elements from a vector, use the `clear` method:

```cpp
V.clear();
```

### Initializing Vectors with Default Values

By default, vectors are initialized with zero values. You can specify a default value during initialization:

```cpp
vector<int> V(50, 7); // Vector of 50 elements, all initialized to 7
```

### Importance of Vectors

Vectors are fundamental data structures due to their:

* **Efficiency:** Fast insertion and deletion at the end.
* **Dynamic size:** Automatically adjust their size as needed.
* **Flexibility:** Can store elements of various types.

### Example: Adjacency List in Graphs

Vectors are commonly used to represent adjacency lists in graphs. Each element in the vector represents a node, and the elements at its index represent its neighbors:

```cpp
vector<vector<int>> adjList; // Adjacency list of a graph
```## Understanding Vectors and the Sort Function in C++

### Vectors: A Convenient Container for Elements

- Vectors are a type of container in C++ that allows you to store a collection of elements.
- They are similar to arrays, but they can grow or shrink dynamically as needed.
- To use vectors, you first need to define a vector object. The syntax is:

```cpp
vector<type> vector_name;
```

- For example, to create a vector of integers named "numbers," you would write:

```cpp
vector<int> numbers;
``````cpp
vector<int> numbers;
```

- To add elements to a vector, use the `push_back` method. For example:

```cpp
numbers.push_back(1);
numbers.push_back(3);
numbers.push_back(5);
```

- Vectors can be sorted using the `sort` function, which arranges the elements in ascending order.

### The Sort Function: Efficiently Sorting Data

- The `sort` function is a powerful tool for sorting arrays and vectors.
- To use the sort function, provide it with a pointer to the first element and a pointer to the element after the last element:

```cpp
sort(array_name, array_name + length);
```

- The sort function uses a hybrid algorithm that combines quick sort, insertion sort, and heap sort for optimal efficiency.
- For example, to sort an array of integers named "array" with a length of 5:

```cpp
sort(array, array + 5);
```

### Example: Sorting Even and Odd Numbers

- Let's use vectors and the sort function to solve a common problem: sorting even and odd numbers from a given input.
- First, we create two vectors, one for even numbers and one for odd numbers:

```cpp
vector<int> even;
vector<int> odd;
```

- Then, we loop through the input and add each number to the appropriate vector:

```cpp
for (int i = 0; i < n; i++) {
  int number;
  cin >> number;
  if (number % 2 == 0) {
    even.push_back(number);
  } else {
    odd.push_back(number);
  }
}
```

- Finally, we sort both vectors and print them:

```cpp
sort(even.begin(), even.end());
sort(odd.begin(), odd.end());
for (int i = 0; i < even.size(); i++) {
  cout << even[i] << " ";
}
cout << endl;
for (int i = 0; i < odd.size(); i++) {
  cout << odd[i] << " ";
}
```

- This code will sort the numbers into two lines, one containing even numbers and the other containing odd numbers.## Understanding Data Structures: Arrays, Vectors, and Pairs

### Arrays: Storing Elements Contiguously

- Arrays hold elements of the same data type.
- Elements are stored contiguously in memory, with indices starting from 0.
- To sort an array partially (e.g., first three elements):
```cpp```cpp
array.sort(array.begin(), array.begin() + 3);
```

### Vectors: Dynamic Arrays for Enhanced Flexibility

- Vectors are dynamic arrays that can grow automatically as needed.
- Like arrays, elements are stored contiguously and have indices.
- Vector iterators (`v.begin()` and `v.end()`) define the range of elements.
- To sort a vector:
```cpp
sort(v.begin(), v.end());
```

### Pairs: Combining Different Data Types

- Pairs allow us to store two values of different data types in a single variable.
- Syntax: `pair<type1, type2> variable_name;`
- Values can be accessed using `.first` and `.second`.
- Example: `pair<int, string> p = {1, "Hello"};`

### Composite Data Types and Nesting

- Composite data types can contain other data types, including arrays, vectors, and pairs.
- Pairs can be nested to create complex data structures.
- Example: `pair<vector<int>, pair<int, string>> nested_pair;`

### Advantages of Pairs

- Useful for functions that need to return multiple values.
- Keeps data of different types together in a single variable.**Introduction to Pairs**

Pairs are a fundamental data structure in C++ that allow us to group two values of the same or different types into a single object. You can think of them as tuples with only two elements.

**Creating and Accessing Pairs**

To create a pair, you use the `pair` template syntax:

```cpp
pair<int, string> p;
```

Here, `p` is a pair that holds an integer and a string. You can access each element of the pair using the dot operator:

```cpp
p.first = 17;  // Assign 17 to the integer element
p.second = "Utkarsh";  // Assign "Utkarsh" to the string element
```

**Modifying and Printing Pairs**

You can modify and print pairs as follows:

```cpp
p.first += 10;  // Add 10 to the integer element
cout << p.first << " " << p.second << endl;  // Print the pair elements
```

**Using Pairs to Return Multiple Values**

Pairs are useful for returning multiple values from a function:

```cpp
pair<int, int> divide(int a, int b) {```cpp
pair<int, int> divide(int a, int b) {
  return {a / b, a % b};  // Return a pair containing quotient and remainder
}
```

**Sorting Pairs**

Pairs are frequently used for sorting. When sorting an array of pairs, they are sorted based on the first element. If two pairs have equal first elements, they are sorted based on the second element:

```cpp
vector<pair<int, int>> v = {{1, 2}, {5, 4}, {3, 1}};
sort(v.begin(), v.end());  // Sort the vector of pairs
```

**Example: Sorting Student Scores**

Suppose you have a list of student names and their scores. You can use pairs to sort the names in decreasing order of scores:

```cpp
vector<pair<int, string>> students;
// Populate the vector with student names and scores

sort(students.begin(), students.end(),
     [](const auto& a, const auto& b) { return a.first > b.first; });
```

This will sort the student names based on their scores in decreasing order.## Understanding Iterators and Containers

**Iterators**

* Iterators are objects that allow you to traverse a container and access its elements one by one.
* They behave similarly to pointers in arrays.
* **v.begin()** returns an iterator pointing to the first element in a vector.
* **auto** keyword can be used to simplify the declaration of iterators.
* You can dereference an iterator using the `*` operator to access the underlying element.
* Iterators can be incremented (**) and decremented (--) to move through the container.
* You can add/subtract values to an iterator to move by multiple elements.

**Containers**

**Set**

* A set is a container that stores a unique, sorted collection of elements.
* Only one copy of each element is kept in a set.
* **s.insert(element)** inserts an element into the set.
* **s.erase(element)** removes an element from the set.
* **s.count(element)** returns the number of occurrences of an element in the set (only 0 or 1).
* **s.clear()** removes all elements from the set.
* **s.size()** returns the number of elements in the set.**Introduction to Sets in Programming****What is a Set?**
- A set is a data structure that stores unique elements.
- It ensures that there are no duplicate values in the set.
- Unlike vectors, sets are unordered.

**Creating a Set**
- Use the `set` keyword followed by the data type enclosed in angle brackets.
- For example, to create a set of integers: `set<int> s;`
- You can also create sets of strings, pairs, or other composite data types.

**Set Operations:**
- **s.insert(x):** Adds element `x` to the set.
- **s.count(x):** Returns the number of occurrences of element `x` in the set. If `x` is not present, it returns 0.
- **s.erase(x):** Removes element `x` from the set.
- **s.empty():** Checks if the set is empty.

**Example: Working with a Set of Integers**
```cpp
set<int> s;
s.insert(10);
s.insert(15);

cout << "Count of 10 in the set: " << s.count(10) << endl; // Output: 1
cout << "Count of 9 in the set: " << s.count(9) << endl;  // Output: 0
cout << "Count of 15 in the set: " << s.count(15) << endl; // Output: 1

s.erase(10);
cout << "After erasing 10, count of 10: " << s.count(10) << endl; // Output: 0
```

**Properties of Sets:**
- Sets are always sorted in ascending order.
- Sets do not allow random access using square brackets (`[]`).

**Iterating through Sets:**
- Use iterators to access elements in a set (`s.begin()`, `s.end()`).
- Iterators allow for incrementing and decrementing.
- Accessing an element by index is not allowed.

**Complexity:**
- Insert, erase, and count operations have a time complexity of O(log n).

**Additional Functions**
- **find(x):** Returns an iterator to the element with value `x`, or `s.end()` if `x` is not found.
- **erase(it):** Removes the element pointed to by the iterator `it`.**Sets in C++**

**Introduction**

* Sets are a type of container in C++ that store unique elements.
* Elements in a set are automatically sorted in ascending order.
* Sets use a binary search tree internally to maintain their sorted nature.

**Inserting Elements**

* `s.insert(element)`: Inserts an element into the set.* `s.insert(element)`: Inserts an element into the set.
* If the element already exists, the insertion is ignored.

**Erasing Elements**

* `s.erase(iterator)`: Erases the element pointed to by the specified iterator.
* `s.erase(element)`: Erases the specified element from the set.
* If the element does not exist, the erasure is ignored.

**Example: Erasing the Smallest Element**

* `s.begin()`: Returns an iterator pointing to the smallest element.
* `s.erase(s.begin())`: Erases the smallest element.

**Example: Iterating Through a Set**

* `auto it = s.begin()`;
* `while (it != s.end())`
* `{ std::cout << *it << " "; ++it; }`

**Maps in C++**

**Introduction**

* Maps are a type of container in C++ that store key-value pairs.
* Keys are unique and can be of any data type.
* Values can be of any data type.
* Maps use a balanced binary search tree internally to maintain their sorted nature.

**Declaring a Map**

* `map<key_data_type, value_data_type> map_name;`

**Inserting Elements**

* `map_name[key] = value;`
* This syntax creates a new key-value pair in the map or modifies the existing value associated with the key.

**Accessing Elements**

* `map_name[key]`
* This syntax returns the value associated with the specified key. If the key does not exist, a new key-value pair is created with the default value for the value data type.

**Erasing Elements**

* `map_name.erase(key);`
* This syntax removes the key-value pair with the specified key from the map.

**Example: Counting Frequency of Objects**

* Maps can be used to count the frequency of objects by using the object itself as the key and the frequency as the value.## Chapter 10: Basic STL Structures - Maps

### Introduction to Maps

- Maps are a data structure that stores key-value pairs.
- Keys are unique and sorted in lexicographically increasing order.
- Values can be of any type.

### Key Features of Maps

- **Unique and Sorted Keys:** Maps guarantee that all keys are unique and stored in sorted order.- **O(log n) Complexity:** Operations like finding, inserting, and deleting elements in a map have a time complexity of O(log n), where n is the number of elements in the map.
- **Key-Value Association:** Maps allow for efficient lookup and retrieval of values based on their associated keys.

### Map Operations

- **Insertion:** `map.insert(key, value)` adds a new key-value pair to the map. If the key already exists, the value is updated.
- **Deletion:** `map.erase(key)` removes the key-value pair with the specified key from the map.
- **Finding:** `map.find(key)` returns a pointer to the key-value pair with the specified key, or `map.end()` if the key does not exist.
- **Access:** `map[key]` returns a reference to the value associated with the specified key. If the key does not exist, a new key-value pair is created with a value of 0.

### Iterators in Maps

- Map iterators are similar to set iterators.
- When dereferenced, map iterators return a pair containing the key and value of the current element.
- The shorthand `second` can be used to access the value directly.

### Example

Consider a map `m` of integers to strings:

```cpp
map<int, string> m;
```

Inserting a key-value pair:

```cpp
m[10] = "Hello";
```

Finding a key-value pair:

```cpp
auto it = m.find(10);
if (it != m.end()) {
  cout << it->first << ": " << it->second << endl;  // Output: 10: Hello
}
```

Iterating over a map:

```cpp
for (auto it = m.begin(); it != m.end(); it++) {
  cout << it->first << ": " << it->second << endl;  // Print all key-value pairs
}
```## Getting Started with Maps

**Concept:**
Maps are collections that store key-value pairs, allowing for efficient retrieval of values based on corresponding keys.

**Example:**
If you have a list of students' names and their corresponding IDs, a map can be used to store this information. To find a student's ID, you can directly provide their name (the key) and the map will provide their ID (the value).

**Use Case:****Use Case:**
Maps are particularly useful for storing frequencies or counts of elements. For instance, you can store the frequency of words in a text by using words as keys and their frequency as values.

## Iterating Containers

**Concept:**
Iterators are objects that allow you to traverse a container and access its elements one by one.

**Iterating with Iterators:**
- `auto it = s.begin()`: Initializes an iterator `it` pointing to the first element of container `s`.
- `it != s.end()`: Checks if `it` has not reached the end of `s`.
- `it++`: Advances `it` to the next element.
- `*it`: Accesses the element pointed to by `it`.

**Shorthand Notation:**
- For `set` and `vector` containers, you can use a C++11-style `for` loop:
```cpp
for (auto& x : s) {
  // Access elements using just 'x'
}
```

- For `map` containers, you need to use a pair to access both key and value:
```cpp
for (auto& [key, value] : s) {
  // Access key using 'key' and value using 'value'
}
```

## Properties of Sets

Sets are ordered collections of unique elements.

**Unique Elements:**
- Sets only store each element once, even if it is added multiple times.
- When you iterate a set, you will encounter each element only once.

**Sorted Order:**
- Sets maintain their elements in a sorted order, either ascending or descending.
- The ordering is determined by the comparison operator defined for the elements' type.**Markdown Notes on Sets**

**Introduction**

* A set is a collection of unique elements that are ordered in ascending order.
* Sets are powerful because they offer fast searching and efficient management of data.

**Advantages of Using Sets**

* **Guaranteed Order:** Elements are always maintained in increasing order, simplifying searching and retrieval.
* **Fast Lookups:** O(log n) time complexity for searching, making them suitable for large datasets.
* **Avoidance of Duplicates:** Sets automatically prevent the inclusion of duplicate elements, ensuring data integrity.

**Basic Operations on Sets****Basic Operations on Sets**

* **Insert:** `s.insert(element)` adds a new element to the set.
* **Find:** `s.find(element)` searches for an element in the set and returns an iterator.
* **Remove:** `s.erase(iterator)` removes an element from the set using its iterator.

**Example of Using Sets**

**Problem:** Manage a shop inventory of items where each item has a name and a price. Implement functionality to easily identify and sell the cheapest item.

**Solution:**

1. Create a set of pairs: `set<pair<int, string>> s`.
2. For each item in the inventory, insert a pair of (price, name) into the set: `s.insert({price, name})`.
3. When a customer wants to buy the cheapest item:
   * Get the iterator to the first element using `s.begin()`.
   * Retrieve the name of the cheapest item using `(*s.begin()).second`.
   * Remove the item from the set using `s.erase(s.begin())`.

**Advanced Concepts**

* **Iterators:** Iterators allow you to traverse and modify the elements of a set.
* **Reverse Iterators:** `rbegin()` and `rend()` provide iterators to traverse the set in reverse order.
* **STL (Standard Template Library):** Contains various containers and functions, including sets.

**References**

* [C++ Reference - Sets](https://en.cppreference.com/w/cpp/container/set)

**Additional Tips**

* **Practice:** Solve problems on competitive programming platforms to improve your understanding of sets.
* **Experiment:** Try implementing different operations on sets to gain a deeper understanding of their behavior.**Custom Comparators in C++**

**Introduction:**
- Custom comparators allow you to define your own rules for sorting data in C++.
- This enables sorting based on specific criteria beyond the default increasing order.

**How it Works:**
- Define a custom comparator function that takes two elements as input.
- In the function, specify the comparison logic, returning:
   - Positive value: If the first element should come after the second.
   - Negative value: If the first element should come before the second.- Zero: If the elements are equal.
- Pass the comparator function as an argument to the sort function.

**Example:**
```cpp
struct AgeComparator {
public:
  bool operator()(const Person& lhs, const Person& rhs) {
    return lhs.age > rhs.age;
  }
};

std::vector<Person> people = { {20}, {30}, {10} };

std::sort(people.begin(), people.end(), AgeComparator());

// people will be sorted in decreasing order of age
```

**Other Advanced C++ Containers**

**Queuing Containers:**
- **queue:** First-in, first-out (FIFO)
- **stack:** Last-in, first-out (LIFO)
- **deque (double-ended queue):** Can insert and remove elements from both ends

**Priority Queue:**
- Stores elements in a heap data structure, ensuring highest priority elements are accessed first.

**Sets and Maps:**
- **set:** Stores unique elements, sorted in ascending order.
- **map:** Associates keys (often strings) with values (often data structures).

**Multisets and Multimaps:**
- Similar to sets and maps, but allow for duplicate elements.

**Ordered Sets and Maps:**
- Maintain elements in order of insertion.
- May be less efficient and reliable than their unordered counterparts.

**Learning Resources:**
- [C++ Comparators](https://www.learncpp.com/cpp-tutorial/comparators-in-cpp/)
- [C++ Standard Library](https://en.cppreference.com/w/cpp/container)