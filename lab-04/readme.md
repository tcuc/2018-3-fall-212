# Lab 04: Basic Sorting Algorithms with Different Input Types
```
What does a sorting algorithm say when it's broken?

Out of order!
```
## Introduction

> For this lab you will form groups of at least 2 and no more than 5 members.

To become more familiar with the concept of benchmarking programs and its practical application, this week you are going to be testing some algorithms you write yourselves. You will be implementing the Insertion and Selection sort algorithms you learned about in class and benchmarking them against the standard C++ library sorting algorithm.

Things to note about this lab:
1. Be sure to call each of your sorting algorithms on **the same array** for each of the different input types.
2. `std::sort` will sort your array **in place** so you must be sure not to attempt to sort an already sorted array. In order to avoid sorting an already sorted array, use the `copy_array` function contained in the starter code.
3. Make sure any arrays allocated using the `new` operator are deleted after you are finished with them using the `delete` operator
4. This lab has its own starter code (`lab-04.cpp`)

## Inputs

The performance of an algorithm can depend greatly on the type of input it recieves. In fact, most professional sorting algorithms are *hybrid* alrgorithms, which use different routines depending on the size of the input. As you've seen, even algorithms that grow in complexity faster than others can be more effective on small input sizes. Along with input size, as a programmer, you should also consider what state the input will be in on arrival; i.e. is there a chance it is already sorted? Partially sorted?

Generally, these different scenarios will be referred to as **best case**, **average case**, and **worst case**. To explore this topic further, today you will examine what happens given a variety of inputs:

+ Random Unsorted Lists
+ Already Sorted Lists
+ Reverse Sorted Lists
+ Partially Sorted Lists

Don't worry about writing the generator functions for these input types, they will be provided for you in `lab-04.cpp`.

## The Algorithms

In case you need a reminder of how insertion sort and selection sort work ...

**Insertion sort** scans through the array from left to right. At each iteration, each element is moved backwards until the array up to the starting point of the iteration is sorted.

**Selection sort** also scans through the array from left to right. At each iteration the lowest element that has not yet been seen is found and swapped to the starting point of the iteration, such that the array up to that point must be sorted.

## Instructions

  1. Discuss a plan for implementing insertion and selection sort with your group. You **may not** use the slides or any online resources to guide your implementation, but instead should come up with the algorithms on your own based on your understanding of how insertion and selection sort work
  2. Implement insertion sort
  3. Test to make sure the code compiles and insertion sort works correctly
  4. Implement selection sort
  5. Perform the same testing on selection sort as insertion sort
  6. Write the code that benchmarks the three algorithms on the different types of data
  7. Answer the questions at the end of the lab
  
## Questions

> **Question 1:** On which type(s) of input did insertion sort perform best? On which type(s) did it perform worst?

> **Question 2:** What was the overall difference between insertion sort's best-case input and its worst-case input? (no need for numbers on this question, just describe the difference the two input types made).

> **Question 3:** On which type(s) of input did selection sort perform best? On which type(s) did it perform worst?

> **Question 4:** What was the overall difference between selection sort's best-case input and its worst-case input?

> **Question 5:** Would insertion or selection sort ever be good sorting algorithms to use in a more general program? Explain your answer.

> **Question 6:** Generate multiple tables by changing the value of `input_size` (e.g. 50, 500, 5000, 10000).  What are your overall conclusions regarding the performance of these three algorithms, considering different input sizes and different input types?

## Submission

Each group will submit 2 files named `lab-04.txt` and `lab-04.cpp` on Gradescope. Please ensure your files contain the following:

1. `lab-04.cpp` should contain your entire source code
2. `lab-04.txt` should contain your answers to the questions above including your sort implementations and formated benchmarking data. 

If you are unable to complete the entire lab, submit your `lab-04.cpp`, and submit the answers of questions pertaining to the sections you completed along with a summary of the difficulties you encountered during this lab in your `lab-04.txt`.

> Make sure you add all group members to your submission on Gradescope
