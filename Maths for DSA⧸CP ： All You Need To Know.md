**Markdown Notes on Mathematics in Competitive Programming**

**Prerequisites:** Basic school-level mathematics knowledge

**Objectives:** Understand the fundamental concepts of number theory, modular arithmetic, and basic combinatorics for competitive programming.

**Part 1: Divisors, Multiples, and Prime Numbers**

**Divisors:**

- Numbers that divide another number without leaving a remainder.
- Example: 18 has the divisors 1, 2, 3, 6, 9, 18.

**Multiples:**

- Numbers that are divisible by another number.
- Example: Multiples of 4 are 4, 8, 12, 16, ...

**Prime Numbers:**

- Numbers that have exactly two divisors: 1 and themselves.
- Example: 5 is a prime number because it is divisible only by 1 and 5.

**Factors:**

- Another term for divisors.

**Prime LT Check:**

- Determining whether a number is prime by counting its divisors.
- A number is prime if it has exactly two divisors (1 and itself).

**Counting Divisors:**

- To count the divisors of a number n, iterate from 1 to n and check if n is divisible by i for each i.
- Example: For n = 18, there are 6 divisors because it is divisible by 1, 2, 3, 6, 9, and 18.

**Part 2: Modular Arithmetic**

- Overview of modulo operator: % (in Python) or mod (in C++)
- Important rules:
    - (a + b) % m = (a % m + b % m) % m
    - (a * b) % m = (a % m * b % m) % m
    - (a - b) % m = (a % m - b % m + m) % m
  
- Applications in Competitive Programming:
    - Fast exponentiation: Calculating a^b % m efficiently.
    - Solving problems involving remainders and cycles.

**Part 3: Basic Combinatorics**

**Permutations:**

- Arrangements of objects in a specific order.
- Formula: P(n, r) = n! / (n - r)!

**Combinations:**

- Selections of objects without regard to order.
- Formula: C(n, r) = n! / (r! * (n - r)!)

**Applications in Competitive Programming:**

- Counting possible outcomes or arrangements.
- Solving problems involving choosing objects from a set.## Optimizing Prime Number Check: Square Root Approach

### Introduction### Introduction

Determining if a number is prime is a fundamental task in mathematics and computer science. A prime number is only divisible by itself and 1.

### Basic Approach

The basic approach for checking primality is to iterate from 1 to the input number **n** and check if any integers `i` divide **n** without leaving a remainder (i.e., `n % i == 0`). If no such `i` is found, the number is prime.

### Time Complexity Issue

However, this approach has a time complexity of **O(n)**, which can be inefficient for large numbers.

### Square Root Optimization

To optimize this process, we can leverage the following observation:

If **i** is a divisor of **n**, then **n / i** is also a divisor of **n**.

Using this observation, we can split the range of potential divisors into two parts:

- Divisors less than or equal to the square root of **n**
- Divisors greater than the square root of **n**

Since every divisor in the first group has a corresponding divisor in the second group, we only need to check divisors up to the square root of **n**.

### Optimized Code

```python
import math

def is_prime_optimized(n):
  if n <= 1:
    return False

  # Check divisors up to the square root of n
  for i in range(2, int(math.sqrt(n)) + 1):
    if n % i == 0:
      return False

  # No divisors found, so the number is prime
  return True
```

### Time Complexity

The optimized algorithm runs in **O(√n)** time, which is significantly faster for large numbers than the basic **O(n)** approach.**Foundational Concepts of Divisors and Prime Numbers**

**Divisors:**
- A divisor of a number is a positive integer that can divide the number evenly without leaving a remainder.
- For example, the divisors of 12 are 1, 2, 3, 4, 6, and 12.

**Prime Numbers:**
- Prime numbers are positive integers greater than 1 that have exactly two unique factors: 1 and themselves.
- For example, 5, 7, 11, and 13 are prime numbers.

**Efficiently Counting Divisor Count**

**Using Prime Factors:****Using Prime Factors:**
- To count the number of divisors for a number n, find all its unique prime factors.
- For each prime factor, determine its exponent in the prime factorization of n.
- Add 1 to each exponent and multiply them to get the count of divisors.

**Python Code for Prime Factorization:**

```python
def count_divisors(n):
    divisors = 1
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            divisor_count = 0
            while n % i == 0:
                divisor_count += 1
                n //= i
            divisors *= divisor_count + 1
    if n > 1:
        divisors *= 2
    return divisors
```
**Example:**
```python
print(count_divisors(18))  # Output: 6
print(count_divisors(5))  # Output: 2
print(count_divisors(100))  # Output: 9
```

**Sieve of Eratosthenes for All Numbers from 1 to n**

- Create an array of size n+1, initially all set to 1.
- For each number i from 2 to n:
  - If i is not marked as 0 (not already crossed out):
    - Mark all multiples of i as 0 (excluding i)
  - Count the number of remaining 1s in the array as the count of divisors for each number.

**Python Code for Sieve of Eratosthenes:**

```python
def sieve_of_eratosthenes(n):
    sieve = [1] * (n + 1)
    for i in range(2, int(n ** 0.5) + 1):
        if sieve[i] == 1:
            for j in range(i * i, n + 1, i):
                sieve[j] = 0
    return sieve

def count_divisors_from_sieve(sieve, n):
    counts = [0] * (n + 1)
    for i in range(1, n + 1):
        if sieve[i] == 1:
            counts[i] = 2
        else:
            for j in range(1, int(i ** 0.5) + 1):
                if sieve[j] == 1 and i % j == 0:
                    counts[i] += 1
                    if i // j != i:
                        counts[i] += 1
    return counts
```
**Example:**
```python
sieve = sieve_of_eratosthenes(100)
counts = count_divisors_from_sieve(sieve, 100)
print(counts[10])  # Output: 4
print(counts[25])  # Output: 3
```**Concept: Optimizing Divisors Calculations for Numbers 1 to N**

**Introduction:****Introduction:**

When solving problems involving finding divisors or factors of numbers, a naive approach is to check every number from 1 to N for divisibility. This can be time-consuming. A more efficient way is to calculate divisors and store them in an array.

**Step 1: Create an Array to Store Divisors**

- Initialize an array `divisors` of length N+1, where N is the upper bound.
- Set all elements of `divisors` to 0.

**Step 2: Calculate Divisors for Each Number**

- Iterate from `i = 1` to `i <= N`.
- For each `i`:
  - Calculate the divisors of `i` by iterating from `j = i` to `j <= N`:
    - Increment `divisors[j]` by 1, as `i` is a divisor of `j`.

**Step 3: Print Divisors**

- Iterate from `i = 1` to `i <= N`.
- Print `divisors[i]` as the number of divisors for `i`.

**Time Complexity Analysis:**

- The time complexity of this approach is O(N log N).
- We iterate from 1 to N, which is O(N).
- For each `i`, we iterate from `i` to N, which adds up to O(N log N).

**Key Points to Remember:**

- This approach is faster than the naive approach because it avoids unnecessary iterations.
- It can be used to calculate divisors for a range of numbers, making it suitable for problems where multiple divisors need to be found.
- The time complexity of O(N log N) is still not optimal for large N. For large N, the sieve of Eratosthenes algorithm offers a better time complexity of O(N log log N).**Prime Number Generation: Sieve of Eratosthenes**

**Introduction:**

The goal is to efficiently determine all prime numbers within a given range. Prime numbers are those divisible only by 1 and themselves.

**Method:**

1. **Initialize an Array:** Create an array of booleans, initially set to `True`, representing the potential primality of numbers. Mark `1` as non-prime.

2. **Loop from 2 to √n:** Iterate through numbers from 2 to the square root of the range.

3. **Mark Multiples:** For each number `i`, mark all multiples of `i` (starting from `i*i`) as non-prime.4. **Check for Prime:** Numbers that remain marked as `True` after the loop are prime.

**Code Example (Python):**

```python
import math

def sieve_of_eratosthenes(n):
    primes = [True] * (n + 1)
    primes[1] = False
    
    for i in range(2, int(math.sqrt(n)) + 1):
        if primes[i]:
            for j in range(i*i, n+1, i):
                primes[j] = False

    return primes

# Usage:
n = 100
primes = sieve_of_eratosthenes(n)
print("Prime numbers up to {}:".format(n))
for i in range(2, n+1):
    if primes[i]:
        print(i)
```

**Advantages:**

- Efficient for large ranges (asymptotic complexity of O(n log log n)).
- Faster than brute-force methods (O(n^2)).
- Can be used for various applications, such as cryptography and data security.

**Limitations:**

- Requires precomputing a large array when handling extensive ranges.
- Can be impractical for small ranges where brute-force methods are faster.
- May not be optimal for specific applications where the range is known beforehand.**Constants**

**Definition:** Constants are values that remain the same throughout the execution of a program.

**Use Cases:**
- Defining the size of an array
- Representing a universal physical constant (e.g., gravitational constant)
- Specifying configuration settings

**Syntax (C++):**
```cpp
const data_type constant_name = value;
```

**Example:**
```cpp
const int ARRAY_SIZE = 10;
```

**Greatest Common Divisor (GCD)**

**Definition:** The GCD is the greatest number that divides both the given numbers without leaving a remainder.

**Formula:**
```
GCD(a, b) = GCD(b, a % b)
```

**Example:**
```
GCD(18, 8) = 2
```

**Co-Prime Numbers:**

**Definition:** Two numbers are co-prime if their GCD is 1.

**Properties:**

* The GCD of two co-prime numbers is 1.
* Co-prime numbers are used to simplify calculations and improve performance in competitive programming.

**Euclidean Algorithm (Finding GCD):**

**Algorithm:**
1. If either number is 0, return the other number.
2. Subtract the smaller number from the larger number.2. Subtract the smaller number from the larger number.
3. Repeat steps 1-2 until one number becomes 0.

**Syntax (C++):**
```cpp
int gcd(int a, int b) {
  if (a == 0) return b;
  if (b == 0) return a;
  return gcd(b, a % b);
}
```

**Time Complexity:** O(log(max(a, b)))

**Example:**
```cpp
cout << gcd(18, 8) << endl;  // Output: 2
```**Euclidean Algorithm for GCD:**

**Definition:**
The greatest common divisor (GCD) of two numbers a and b is the largest positive integer that divides both a and b without leaving a remainder.

**Euclidean Algorithm:**
A simple and efficient method to find GCD(a, b) is the Euclidean Algorithm, which is a recursive algorithm based on the following principles:

- GCD(a, 0) = a
- GCD(a, b) = GCD(b, a mod b)

**Implementation:**

1. If b is 0, return a.
2. Repeat the following steps until b becomes 0.
   - Calculate the remainder: r = a % b.
   - Update a to b and b to r.

**Example:**

To find GCD(8, 18):
- r = 8 % 18 = 8
- a = 18, b = 8
- r = 18 % 8 = 2
- a = 8, b = 2
- r = 8 % 2 = 0
- Return a = 8

**Modular Arithmetic:**

**Definition:**
Modular arithmetic is a system of arithmetic that operates on integers by wrapping around within a specified range or modulus.

**Notation:**
a mod m represents the remainder of a when divided by m.

**Properties:**

- (a + b) mod m = (a mod m + b mod m) mod m
- (a - b) mod m = (a mod m - b mod m) mod m
- (a * b) mod m = (a mod m * b mod m) mod m

**Applications:**

- Cryptography and digital signatures
- Cyclic data structures (e.g., arrays, queues)
- Time-stamping and clock arithmetic
- Number theory and abstract algebra

**Example:**

To calculate (8 + 18) mod 13:
- 8 + 18 = 26
- 26 mod 13 = 10**Understanding Modular Arithmetic**

**Introduction:**

Modular arithmetic is a fundamental concept in computer science and mathematics. It involves working with numbers within a specific range, known as the modulus. Understanding modular arithmetic is crucial for various applications, including cryptography and data structures.

**Modulus Function:****Modulus Function:**

The modulus function, denoted as '%', calculates the remainder when one number is divided by another. For example, in Python:

```python
>>> 10 % 3
1
```

This means that when 10 is divided by 3, the remainder is 1.

**Core Concepts:**

**Remainder:** The remainder is the number that is left over after dividing one number by another.

**Modulus:** The modulus is the number used to determine the range of values.

**Modular Arithmetic:** Modular arithmetic involves performing arithmetic operations (addition, subtraction, multiplication) on numbers within a specified modulus.

**Formula for Addition and Multiplication:**

* Addition: `(a + b) % m`
* Multiplication: `(a * b) % m`

where `a` and `b` are the operands, and `m` is the modulus.

**How to Derive the Formula (for Addition):**

Let `a = k1 * m + r1` and `b = k2 * m + r2`, where `k1` and `k2` are integers, and `r1` and `r2` are remainders.

Then, `(a + b) = (k1 * m + r1) + (k2 * m + r2)`
`= (k1 + k2) * m + (r1 + r2)`

Since `(k1 + k2) * m` will be divisible by `m`, we are left with:
`= r1 + r2`
`= (a % m) + (b % m)`
`= (a + b) % m`

**Subtraction Formula:**

* Subtraction: `(a - b + m) % m`

This formula ensures that the result is always non-negative.

**Example:**

**Addition:**

Let's calculate `(3 + 4) % 5`. Using the formula:
```
(3 % 5) + (4 % 5) = 3 + 4 = 7
7 % 5 = 2
```
Therefore, `(3 + 4) % 5` is `2`.

**Multiplication:**

Let's calculate `(9 * 13) % 5`. Using the formula:
```
(9 % 5) * (13 % 5) = 4 * 3 = 12
12 % 5 = 2
```
Therefore, `(9 * 13) % 5` is `2`.

**Usefulness of Modular Arithmetic:**

* Simplifies calculations involving large numbers
* Facilitates data storage and manipulation in hash tables
* Ensures that certain values repeat within a specified range (e.g., cyclic data structures)
* Provides a basis for secure communication protocols (e.g., RSA encryption)**Modular Arithmetic: Power Calculation Using Recursion**

**Introduction:****Introduction:**
Modular arithmetic deals with calculations where the result wraps around to a smaller range after exceeding a certain limit. In this case, the result is always kept below a specified modulus, typically represented by 'm'. This concept is often applied in cryptography, computer science, and other fields.

**Modular Exponentiation:**
To calculate a^b mod m efficiently, we use recursion. The key property we utilize is:

- a^b mod m = a^(b mod m) mod m

**Recursive Function for a^b mod m:**

```cpp
int pw(int a, int b, int m) {
  if (b == 0) return (a % m);

  if (b % 2 == 0) {
    int t = pw(a, b / 2, m);
    return (1ll * t * t) % m;
  } else {
    int t = pw(a, (b - 1) / 2, m);
    return (1ll * t * t % m) * a % m;
  }
}
```

**Explanation:**

- If b is even, we calculate a^(b/2) and square it, giving us a^b.
- If b is odd, we calculate a^((b-1)/2), square it, and multiply by 'a' to get a^b.
- We use long long (1ll) to prevent potential integer overflow during multiplication.

**Example:**

```cpp
int main() {
  int a = 3;
  int b = 4;
  int m = 5;
  cout << pw(a, b, m) << endl; // Output: 1
}
```

**Result:**
3^4 = 81, and 81 mod 5 = 1.

**Benefits of Recursion:**

- Efficiency: The recursive approach is more efficient than iteratively multiplying 'a' 'b' times.
- Simplicity: The recursive code is easier to understand and implement compared to iterative methods.## Binary Exponentiation (Bin Pow)

Binary exponentiation is a technique for finding the value of `a^b` in O(log b) time.

### How it Works:

Imagine calculating `3^8` using binary exponentiation:

- Start with `b = 8` in binary: `1000`.
- Break `8` into its binary digits: `1` and `000`.
- For each non-zero digit, multiply the result so far by `a` and square it:
  - `3^1 * 3^3 = 27 * 9 = 243` (for '1')
- Return the final result: `243`

### Why it's O(log b):

At each step, the exponent `b` is halved (binary digits decrease from right to left) until it becomes 0. Therefore, the number of steps is at most `log b`.### Division Under Modulo (`a / b mod m`)

In modular arithmetic, division is achieved using multiplicative inverses.

### Multiplicative Inverse:

For two numbers `a` and `b`, if `a * b mod m = 1`, then `b` is the multiplicative inverse of `a` under modulo `m`.

### Finding Multiplicative Inverse:

To find the multiplicative inverse of `a` under modulo `m`:

- Try dividing `a` sequentially by 1, 2, 3, ... until the remainder is `1`.
- The divisor that gives a remainder of `1` is the multiplicative inverse.

### Example:

To find 6 / 2 mod 5:

- Calculate 6 mod 5 = 1
- Calculate 2 mod 5 = 2
- The multiplicative inverse of 2 under modulo 5 is 3 (6 / 2 mod 5 = 2 * 3 = 6)

### Code Example:

```python
def binary_pow(a, b):
    """Calculate a^b using binary exponentiation."""
    result = 1
    while b > 0:
        if b % 2 == 1:
            result *= a
        a *= a
        b //= 2
    return result

def div_mod(a, b, m):
    """Perform division (a / b) under modulo m."""
    inverse = 0
    for divisor in range(1, m):
        if (divisor * b) % m == 1:
            inverse = divisor
            break
    return (a * inverse) % m
```**Multiplicative Inverse**

**Concept:**
The multiplicative inverse of a number is a number that, when multiplied by the original number, gives a product of 1.

**Key Details:**

* The multiplicative inverse of b (denoted as b^-1) modulo m is a number that satisfies the equation: (b * b^-1) mod m = 1
* Finding the multiplicative inverse is important for solving certain types of mathematical problems, such as finding remainders efficiently.

**Existence of Multiplicative Inverse:**
* The multiplicative inverse of b modulo m exists if and only if the greatest common divisor (gcd) of b and m is 1.
* In other words, b and m must be co-prime (have no common factors other than 1).

**Finding the Multiplicative Inverse:**
* If the gcd(b, m) = 1, then the multiplicative inverse of b modulo m is given by: b^-1 = b^(m - 2) mod m* This can be computed efficiently using binary exponentiation (logarithmic time complexity).

**Example:**
* To find the multiplicative inverse of 2 modulo 5:
    * gcd(2, 5) = 1, so the inverse exists.
    * b^-1 = 2^(5 - 2) mod 5 = 2^3 mod 5 = 3
* So, the multiplicative inverse of 2 modulo 5 is 3.

**Alternative Method Using Modulo Arithmetic:**
* To compute (a / b) mod m without knowing b^-1 directly:
    * Compute a mod m and b mod m.
    * Find the multiplicative inverse of b mod m using the formula above.
    * Result = (a mod m) * (b^-1 mod m) mod m

* **Note:** This method only works if m is a prime number.## Modular Arithmetic and Fermat's Little Theorem

### Introduction
- Modular arithmetic involves performing mathematical operations on numbers while considering a predefined modulus (remainder).
- It's widely used in cryptography, computer science, and various mathematical applications.

### Fermat's Little Theorem
- Fermat's Little Theorem states that for a prime number `m` and any integer `a`, the following holds:
  > **a^m mod m = a**

### Applying Fermat's Theorem for Modular Operations
- Fermat's Little Theorem provides a method to efficiently find the multiplicative inverse of a number `b` module a prime number `m`:
  > **b^-1 mod m = b^(m-2) mod m**
- Using this inverse, we can perform modular arithmetic calculations, including addition, subtraction, multiplication, and division, within the bounds of the prime modulus `m`.
- This eliminates the need for large intermediate calculations and prevents overflows.
- For efficiency, operations are typically modified to use the modulus `m` throughout, referred to as "modular addition," "modular multiplication," etc.

### Overflow Prevention
- In modular arithmetic, intermediate results never exceed `m^2`.
- To prevent overflow during multiplication, use long long data types.

### Practical Applications
- Modular arithmetic is commonly used in:
  - Number theory
  - Coding competitions
  - Encryption and decryption algorithms- Encryption and decryption algorithms
  - Error-checking in data transmission

### Additional Information
- The mathematical proof of Fermat's Little Theorem involves concepts such as Euler's Totient Function, which is beyond the scope of this introduction.
- For coding purposes, you can define a function that takes `b` and `m` as parameters and calculates the multiplicative inverse using Fermat's Little Theorem.## Combinatorics and Modulo Arithmetic

### Introduction

Combinatorics deals with counting the number of possible arrangements or selections from a given set of elements.

### NCR (Number of Combinations)

**Definition:**

NCR (Number of Combinations) represents the number of ways to choose R objects from a set of N objects without regard to their order.

**Formula:**

```
NCR = N! / (R! * (N-R)!)
```

where:

* N is the total number of objects
* R is the number of objects to choose

### Modulo Arithmetic

**Definition:**

Modulo arithmetic involves performing arithmetic operations on numbers while taking a specific modulus M into account. The result is always less than M.

### Combining NCR and Modulo Arithmetic

Combinatorics problems often involve large numbers, making it impractical to perform calculations directly. Modulo arithmetic allows us to work with smaller values.

### Storing Factorials

**Storing Factorials:**

To optimize NCR calculations, we can store the factorials of numbers from 1 to N in an array (fact[]):

```
fact[N] = 1
for i = 2 to N:
    fact[i] = fact[i-1] * i
```

**Storing Inverse Factorials:**

To perform NCR with modulo arithmetic more efficiently, we can also store the inverse factorials (inv_fact[]) of numbers from 1 to N:

```
inv_fact[N] = 1
for i = N-1 to 1:
    inv_fact[i] = inv_fact[i+1] * pow(i + 1, -1, M)
```

### Optimized NCR Calculation

Using the stored factorials and inverse factorials, we can calculate NCR efficiently:

```
def ncr(n, r, M):
    return (fact[n] * inv_fact[r] * inv_fact[n-r]) % M
```

### Advantages```

### Advantages

By storing factorials and inverse factorials, we reduce the time complexity of NCR calculations to O(1) (constant time), regardless of the values of N and R.**Factorial and Inverse Factorial**

**Factorial**
* The factorial of a non-negative integer n, denoted by n!, is the product of all positive integers less than or equal to n.
* Example: 5! = 5 x 4 x 3 x 2 x 1 = 120

**Inverse Factorial**
* The inverse factorial of a non-zero integer n, denoted by 1/n!, is the reciprocal of its factorial.
* Example: 1/5! = 1 / (5 x 4 x 3 x 2 x 1) = 1 / 120

**Relationship between N Factorial Inverse and N Minus 1 Factorial Inverse**
* 1/N! = 1/N * 1/(N-1)!
* Multiplying both sides by N, we get:
    * 1/(N-1)! = N * 1/N!

**Calculating Inverse Factorials**
* The inverse factorial of N can be calculated by multiplying the factorial of N by 1/N.
* This allows us to find the inverse factorial of all numbers from 1 to N in linear time (O(N)).

**Application: Calculating Combinations (nCr)**
* The number of ways to select r objects from a set of n distinct objects, denoted by nCr, can be calculated as:
    * nCr = n! / (r! * (n-r)!)

**Code Snippet for Calculating nCr**
```python
# Preprocess: Calculate factorials and inverse factorials
fact = [1]
inverse_fact = [1]
for i in range(1, N+1):
    fact.append(fact[-1] * i)
    inverse_fact.append(inverse_fact[-1] / i)

# Function to calculate nCr
def nCr(n, r):
    if r > n or r < 0 or n < 0:
        return 0
    return fact[n] * inverse_fact[n-r] * inverse_fact[r]
```