# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

Add your answers to this markdown file.

-----

To verify the claim, I could create an algorithm that generates a random list of two elements, a random list of three elements, etc. up to a random list of 1000 elements. The algorithm would give X and a general sorting algorithm the same of each list and keep track of how long it takes the sorting algorithms to sort each list. It would do this by starting two timers, one for each algorithm, when it gives both sorting algorithms the 2 element list and would stop an algorithm’s timer when it sorted all of the lists. Once both algorithms sorted all lists, the times would be compared. If the general sorting algorithm is slower by at least log(n), that means the claim is true since X would be asymptotically faster.

To tell if the general sorting algorithm is slower by at least log(n), I could create a graph, where the x-axis represents the input size and the y-axis represents the time it takes for the algorithm to sort the list.  I could then compare the lines of the general sorting algorithm with X, and if the line of the general sorting algorithm grows more linearly than X, which would be growing logarithmically if it is asymptotically faster, then that means the general sorting algorithm is slower by at least log n.

I don’t believe X could be correct. Since comparison-based sorting algorithms work like binary decision trees, X can’t have a runtime faster than O(nlogn). The height of the tree with L leaves can’t be less than log2(L) because the maximum number of leaves a binary tree of height h can have is 2^h. With a runtime of O(n), the height of the tree would have to be smaller than log2(L), which isn’t possible since there are at least n! leaves.

-----

I recieved minimal help from ChatGPT on my answer to the second part of the assignment (the theoretical argument for why X could or could not be correct). I simply asked it to explain slide 63 of the sorting slides so I could have a better understanding on why the complexity of a general comparison-based sorting algorithm is Ω(nlogn). After I had a better understanding, I was able to write my answer.

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

-----

I started this assignment last semester, so I have added on to my previous answer.  The explanation for how to tell if the general sorting algorithm is slower by at least log(n) is what was added on.
