---
title: "Asymptotic Notations B(OOT) : Big-O, Big-Omega, Big-Theta"
published: true
date: 2019-07-28T00:38:08+03:00
description: Defining the efficiency of an Algorithm
tags: algorithms, big-o, asymptotic, python
---

When you write an algorithm or solve some computational problem you would often like to have an efficient working code. In normal language we would say its fast or slow or fast enough. Well the term is quote OK to use but to be quantitative we have notations which could be used here. These notation are called Asymptotic Notations. So to keep it simple these are notations to analyze an algorithm on how it performs when given a certain input.

# Types of notations
1. **Big-O (Big O)**	 [Atmost or Upper Bound]
2. **Big-Ω (Big-Omega)** [AtLeast or Lower Bound]
3. **Big-θ (Big Theta)** [Range or Tight Bound]


1.**Big-O (Big O)**

This notation is used to define the upper bound of an algorithm or define the worst case of an algorithm.

**Mathematical notation:** f(n) = O(g(n)). Where positive constants c and n0 such that 0 ≤ f(n) ≤ c*g(n) for all n ≥ n0

**Graphical Representation:**

![](https://i.imgur.com/1pJRdVx.png)

Now, Big-O notation is the most popular one, and mostly when we talk about time complexity its usually related to Big-O.

Big-O has several notations. Lets see one by one.
    
- **Constant - O(1)**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It means that no mater what the input size be, the execution time will always be the same. 

**Example:**

```python
		item = items[0]
```

**Graphical Representation:**

![](https://i.imgur.com/dMFdtwG.png)

- **Linear - O(n)**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It means that the execution time is in direct propotion to the input i.e. if the input size increases or decreases so does the execution time increases or decreases.

**Example:**

```python
		element_found = [x for i,x in enumerate([2,3,5]) if x==5]
```

In the above example searching an element in a linear search manner.

**Graphical Representation**

![](https://i.imgur.com/I0P7TQl.png) 

- **Quadratic - O(n<sup>2</sup>)**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It means that the execution time of an algorithm is directly proportion to the square of the size of the input.

**Example:**

```python
		for i in [2,3,4,5]:
			for z in [5,4,3,2]:
				print(f"Match {z}") if i == z else ''
```

Above example has nested loop which makes it a quadratic operation. 

**Graphical Representation**

![](https://i.imgur.com/399gEs2.png)
			

- **Exponential - O(2<sup>n</sup>)**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; It means the execution time will double with each additional element in the input set.

**Example:**

```python
	def fibonacci(n):
		if n <= 1:
			return n
		else:
			return((fibonacci(n-1) + fibonacci(n-2)))
```

**Graphical Representation**

![](https://i.imgur.com/KDHF4j1.png)

- **Logarithmic - O(log(n))**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; If an algorithm solves the problem by dividing it into half each time then its a O(log n). *A great example of it is Binary Search Algorithm*.

**Graphical Representation**

![](https://i.imgur.com/Fg01005.png)

As you can see with the graph that with initial input it tends to grow but with increase in input size it gradually stops growing or grows at a linear rate. Its very much suitable for larger input set.

- **Factorial - O(!n)**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Is an algorithm which tries all the permutation of a given input array. Its one of the worst performaning algorithm hence you dont want your algorithm to be to this level.

**Example:**

Most commonly talked about factorial complexity algorithm is Travelling Salesman problem when does using Brute force method, where all the possible path combinations are evaluated. Another example is to get the factorial of a number.

```python
		def factorial(n):
			for i in range(n):
				factorial(n-1)
```

Outer loop is O(n), inner function is called recursively with (n-1) you get n * (n-1)* (n-2)*...*1 = n! so the function is O(n!).

2.**Big-Ω (Big-Omega)**

This notation is used to define the lower bound of an algorithm. So we can say a given algorithm will take *atleast* a certain amount of time.

**Mathematical notation:** f(n) = Ω(g(n)). Where positive constants c and n0 such that 0 ≤ c*g(n) ≤ f(n) for all n ≥ n0

**Graphical Representation:**

![](https://i.imgur.com/WP1QO6y.png) 


**Example:**

In case of Binary search algorithm we can say that it has its best case as Ω(1), if the number you are finding falls right in the middle.


3.**Big-Θ (Big-Theta)**

This notation defines a tight bound of an algorithim execution time. So, there is an upper bound and a lower bound and the algorithm execution time would fall within the range.

**Mathematical notation:** f(n) = θ(g(n)). Where positive constants n<sub>0</sub>, c<sub>1</sub>, c<sub>2</sub> are such that at the right of n<sub>0</sub> , the value of f(n) always lies between c<sub>1</sub>g(n) and c<sub>2</sub>g(n) i.e. 0 ≤ c<sub>1</sub>g(n) ≤ f(n) ≤ c<sub>2</sub>g(n) for all n ≥ n0

**Graphical Representation:**

![](https://i.imgur.com/Ly9Ct2u.png)

**Example:**

```python
		def search_index(num):
			for i, x in enumerate(list):
				if num == x:
					return i
```

In the above example, lower bound (best case) would be O(1) where the item is found at 0 index. And upper bound (worst case) would be O(n) where the item is found at the last index.


**Readings and References:**

*https://www.khanacademy.org/computing/computer-science/algorithms/asymptotic-notation/a/asymptotic-notation*

*http://web.mit.edu/16.070/www/lecture/big_o.pdf*

*https://i.stack.imgur.com/nLm8w.png*

*https://guide.freecodecamp.org/computer-science/notation/big-o-notation/*

*https://stackabuse.com/big-o-notation-and-algorithm-analysis-with-python-examples/*

*https://www.daveperrett.com/articles/2010/12/07/comp-sci-101-big-o-notation/*

*https://www.101computing.net/big-o-notation/*