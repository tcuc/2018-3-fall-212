# Lab 03: The Great Algorithm Race

## Introduction

Different algorithm implementations often take different lengths of time to complete, even if they solve the same problem. This lab will be completed in teams, depending on your lab section:

##### Wednesday Lab
Work in teams of two or three. Do all your scratch work on a sheet of paper or in a text editor, just make sure all of your teammates can see it.

##### Friday Lab
Work with the other students at your table. Do all of your scratch work on your table's whiteboard.

The goal of the lab is to get a hands-on look at algorithm complexity by benchmarking three different algorithms for different input sizes, and printing a table of the results to the console.

## Instructions

There are two primary goals in this lab:
1. Design algorithms to solve three different (but related) problems
2. Benchmark implementations of these algorithms on different input sizes and report on the results

Note that the first goal is **not** to write code, but to come up with strict, step-by-step procedures (algorithms) by which you can solve the problems described in this lab. The purpose of this is to separate the process of solving a problem from the process of creating code that compiles, runs and works correctly. Preemptively jumping into code can result in a "try it until it works" mindset, which can get in the way of solving the problem at hand. Plus, if you can come up with an algorithm that solves a certain problem, and you are confident in the correctness of your algorithm, turning it into code will be a much easier task.

That being said, you should first discuss the problem and how you will try to solve it with your teammates, and write out the algorithm your team decides on in plain english or pseudocode. Then, you should think of various different test cases and see if your algorithm works for all of them. If it doesn't, adjust your algorithm so that it does.

*Only when you feel satisfied with the correctness of your algorithm* should you implement it in the starter code and ensure that it works correctly there, too.

Once you have implemented all three algorithms you can use the other functions in the starter code to time them against one another and report on the results. Make sure to use the same input variables of each of the three functions.

## The Starter Code

The starter code for this lab is available in the link `lab-03.cpp` above. This code contains two functions you will use: `gen_rand_list` and `delete_list`, and three you will implement: `num_in_array`, `sum2_in_array`, and `sum3_in_array`. 

> `num_in_array`: Determine whether or not a given number `num` is in a list of numbers `arr`

> `sum2_in_array`: Determine whether or not there are two numbers `x1` and `x2` in a list of numbers `arr` such that `x1 + x2` is equal to a given number `num`

> `sum3_in_array`: Determine whether or not there are three numbers `x1`, `x2`, and `x3` in a list of numbers `arr` such that `x1 + x2 + x3` is equal to a given number `num`

The three functions you will implement need not actually be called directly, as the starter code contains a way to call each function from a function array, but you may use each function explicitly instead if you wish. They each take an integer array, its length, and a number `num` as parameters, and return `true` if the condition is met, and `false` otherwise. To generate randomized arrays for the algorithms to work with you can use `gen_rand_list`, which takes the length of the array as a parameter and returns a pointer to a randomized integer array. These arrays are allocated on the heap, so use either `delete_list` or the `delete` keyword to free the memory when you're done with them. 

## Compiling

Ensure that your terminal is in the same directory as the .cpp files and then compile your program using the command:   

```bash
g++ -g -std=c++11 name_of_file.cpp -o name_of_file
```

>Replace `name_of_file` with the name of the file you are trying to compile

Also notice the -std=c++11 flag. This is needed because this lab's code uses some features that are only available in C++11, such as the `<chrono>` library and the `auto` specifier.
 
The program should compile without errors.

This program takes no arguments so the command is `./name_of_file`

> Make sure your program runs without errors before proceeding.

## Benchmarking

Measuring the time an algorithm or a section of code takes to run is called benchmarking. It times the code just like you would do in real life. It looks at the time when the code starts, runs the code, then looks at the time it ends. This is how you do it in C++:

```C++
#include <iostream>
#include <chrono>

int main() {
    // Get the starting Time
    auto start = std::chrono::steady_clock::now();
    /*
        The part of your code you want to time
    */
    // Get the ending time
    auto end = std::chrono::steady_clock::now();
    
    // This finds the time your code took to run by subtracting the end and start times. It assigns it to the variable  t  as a double
    // Now you can use std::cout to print  t  to the console.
    double t = std::chrono::duration<double> (end - start).count();
    return 0;
}
```

> Note that for this lab's starter code, each function you implement will stop running if it runs for longer than one minute, and will return `-1` instead of the actual answer. In the case where the algorithm is running for too long, `N/A` should be used as a placeholder in the output since the algorithm did not actually complete.

## Printing Running Times

For successful completion of this lab, you must print to the console a table of running times for each of the algorithms, given different input sizes. The input sizes you should use for this lab are 10, 100, 1000, and 10000. These should be printed across the top of the table, and the algorithms should be printed along the left side (you may simply use "A1, A2 and A3" in place of "num_in_array, sum2_in_array, and sum3_in_array" respectively). To ensure that you print the columns out evenly, you may use `std::cout.precision(x)` to set the number of digits after the decimal to be printed, and `std::cout << std::fixed` to print the results in regular decimal format instead of scientific. The output to your program should look something like this:

```
    10         100        1000       10000      
A1  0.0000284  0.0037321  0.5383260  N/A
A2  0.0000117  0.0001362  0.0017957  0.1353368
A3  0.0000039  0.0000063  0.0000117  0.0001200
```

> if you want to get more precise values in this table, each running time can be the average of 10 different runs

## Submission

You will submit 2 text files named `lab-03.cpp` and `lab-03.txt` on Gradescope. Please ensure your files contain the following:

1. `lab-03.cpp` should contain your entire source code
2. `lab-03.txt` should contain the table (running times) generated by your program
