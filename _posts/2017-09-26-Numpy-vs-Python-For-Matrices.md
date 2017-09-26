---
layout: post
comments: true
title:  "Pure Python vs. Numpy for matrices"
excerpt: "Which one wins?"
date:   2017-09-26 22:00:00
---

Hello there!

I recently worked on a [class assignment](https://github.com/ayesha92ahmad/Pure-python-vs-numpy) in which my Machine Intelligence and Deep learning Professor asked us to code some operations in both pure Python and Numpy. By pure python we mean, without the use of external libraries, i.e. the traditional way using loops and lists and lists of lists. It was an **eye opener**! The moment we start using python for matrices, we use Numpy. As if, there isn't a better way to work on matrices. And, that is the reason we worked on that [assignment](https://github.com/ayesha92ahmad/Pure-python-vs-numpy). The thing that I enjoyed the most was revisiting some linear algebra concepts that I had worked on earlier and performing the operations by writing raw code, and thus realizing how far we have come along and how dependent we are on these external libraries such as Numpy and Pandas, and for good reason.


The following steps are performed on Matrices using both Pure python and numpy and their speeds are compared

1. Create a zeros array of size (3,5) and store in variable z.
2. Set all the elements in first row of z to 7.
3. Set all the elements in second column of z to 9.
4. Set the element at (second row, third column) of z to 5.
5. Create a vector of size 50 with values ranging from 50 to 99 and store in variable x.
6. Create a 4x4 matrix with values ranging from 0 to 15 and store in variable y.
7. Create a 5x5 array with 1 on the border and 0 inside.
8. Generate a 50x100 array of integer between 0 and 5,000 and store in variable a.
9. Generate a 100x200 array of integer between 0 and 20,000 and store in variable b.
10. Multiply matrix a and b together (real matrix product) and store to variable c.
11. Normalize a 3x3 random matrix ((x-min)/(max-min)) and store to variable d.
12. Subtract the mean of each row of matrix a.
13. Subtract the mean of each column of matrix b.
14. Transpose matrix c, add 5 to all elements in matrix, and store to variable e.
15. Reshape matrix e to 1d array, store to variable f, and print shape of f matrix.
![Comparison Report](https://github.com/ayesha92ahmad/ayesha92ahmad.github.io/blob/master/assets/img/report.png)


We see that though for smaller matrices Python has better timing, Numpy performs visibly better for larger matrices and lists.


References:
1. [Python documentation](https://docs.python.org/3/)
2. [Numpy documentation](https://docs.scipy.org/doc/numpy-1.13.0/reference/)
