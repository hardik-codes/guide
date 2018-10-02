---
title: Algorithm Performance
---
In mathematics, big-O notation is a symbolism used to describe and compare the _limiting behavior_ of a function.  
A function's limiting behavior is how the function acts as it trends towards a particular value and in big-O notation it is usually as it trends towards infinity.  
In short, big-O notation is used to describe the growth or decline of a function, usually with respect to another function.




NOTE: x^2 is equivalent to x * x or 'x-squared']

For example we say that x = O(x^2) for all x > 1 or in other words, x^2 is an upper bound on x and therefore it grows faster.  
The symbol of a claim like x = O(x^2) for all x > _n_ can be substituted with x <= x^2 for all x > _n_ where _n_ is the minimum number that satisfies the claim, in this case 1.  
Effectively, we say that a function f(x) that is O(g(x)) grows slower than g(x) does.

Comparitively, in computer science and software development we can use big-O notation in order to describe the time complexity or efficiency of algorithms  
Specifically when using big-O notation we are describing the efficiency of the algorithm with respect to an input: _n_, usually as _n_ approaches infinity.  
When examining algorithms, we generally want a lower time complexity, and ideally a time complexity of O(1) which is constant time.  
Through the comparison and analysis of algorithms we are able to create more efficient applications.

## Examples

As an example, we can examine the time complexity of the <a href='https://github.com/FreeCodeCamp/wiki/blob/master/Algorithms-Bubble-Sort.md#algorithm-bubble-sort' target='_blank' rel='nofollow'>[bubble sort]</a> algorithm and express it using big-O notation.

#### Bubble Sort:
```javascript
    // Function to implement bubble sort
    void bubble_sort(int array<a href='http://bigocheatsheet.com/' target='_blank' rel='nofollow'>], int n)
    {
        // Here n is the number of elements in array
        int temp;
        for(int i = 0; i < n-1; i++)
        {
            // Last i elements are already in place
            for(int j = 0; j < n-i-1; j++)
            {
                if (array[j] > array[j+1])
                {
                    // swap elements at index j and j+1
                    temp = array[j];
                    array[j] = array[j+1];
                    array[j+1] = temp;
                }
            }
        }
    }
```
Looking at this code, we can see that in the best case scenario where the array is already sorted, the program will only make _n_ comparisons as no swaps will occur.  
Therefore we can say that the best case time complexity of bubble sort is O(_n_).

Examining the worst case scenario where the array is in reverse order, the first iteration will make _n_ comparisons while the next will have to make _n_ - 1 comparisons and so on until only 1 comparison must be made.  
The big-O notation for this case is therefore _n_ * [(_n_ - 1) / 2] which = 0.5*n*^2 - 0.5*n* = O(_n_^2) as the _n_^2 term dominates the function which allows us to ignore the other term in the function.

We can confirm this analysis using [this handy big-O cheat sheet</a> that features the big-O time complexity of many commonly used data structures and algorithms

It is very apparent that while for small use cases this time complexity might be alright, at a large scale bubble sort is simply not a good solution for sorting.  
This is the power of big-O notation: it allows developers to easily see the potential bottlenecks of their application, and take steps to make these more scalable.

For more information on why big-O notation and algorithm analysis is important visit this <a href='https://www.freecodecamp.com/videos/big-o-notation-what-it-is-and-why-you-should-care' target='_blank' rel='nofollow'>video challenge</a>!

An algorithm is considered efficient if its resource consumption, also known as computational cost, is at or below some acceptable level. Roughly speaking, 'acceptable' means: it will run in a reasonable amount of time or space on an available computer, typically as a function of the size of the input. Since the 1950s computers have seen dramatic increases in both the available computational power and in the available amount of memory, so current acceptable levels would have been unacceptable even 10 years ago. In fact, thanks to the approximate doubling of computer power ever 2 years, tasks that are acceptably efficient on modern smartphones and embedded systems may have been unacceptably inefficient for industrial servers 10 years ago.

Computer manufacturers frequently bring out new models, often with higher performance. Software costs can be quite high, so in some cases the simplest and cheapest way of getting higher performance might be to just buy a faster computer, provided it is compatible with an existing computer.

There are many ways in which the resources used by an algorithm can be measured: the two most common measures are speed and memory usage; other measures could include transmission speed, temporary disk usage, long-term disk usage, power consumption, total cost of ownership, response time to external stimuli, etc. Many of these measures depend on the size of the input to the algorithm, i.e. the amount of data to be processed. They might also depend on the way in which the data is arranged; for example, some sorting algorithms perform poorly on data which is already sorted, or which is sorted in reverse order.

In practice, there are other factors which can affect the efficiency of an algorithm, such as requirements for accuracy and/or reliability. As detailed below, the way in which an algorithm is implemented can also have a significant effect on actual efficiency, though many aspects of this relate to optimization issues. 
