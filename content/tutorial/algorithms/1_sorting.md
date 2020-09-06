---
title: Sorting

date: 2020-01-12T00:00:00
# lastmod = 2018-09-09T00:00:00

draft: false
toc: true 
type: docs


# Add menu entry to sidebar.
#linktitle: Sorting
menu:
    algorithms:
        name: "Sorting"
        weight: 1
---

The general framework we have in sorting is that we are given a sequence of $n$ numbers, and we want to construct an algorithm which orders those numbers from smallest to largest. 

**Input**: A sequence of $n$ numbers $\langle a_1, a_2, \cdots, a_n \rangle$ <br>
**Output**: A permutation (or reordering)   $\langle a_1', a_2', \cdots, a_n' \rangle$ of the inputs such that $a_1' \le a_2' \le \cdots \le a_n'$.

In general, the items we would like to sort do not have to be numbers, as they can also be objects, which some sense of ordering for them, as we will see later.

In the following we describe some of the most common sorting algorithms.


## Insertion sort

This is an efficient algorithm for sorting a small number of elements. Works the way many people would sort a hand of playing cards! Every time the dealer hands you a card, you insert this card in the correct position within your current hand. To do this, you compare it with each of the cards already in hard, from left to right.  


### Algorithm

```python
def insertion_sort(a):
    for j in range(1, len(a)):
        key = a[j]
        i = j - 1
        while i >= 0 and a[i] > key:
            a[i+1] = a[i]
            i = i - 1
        a[i + 1] = key
```
 

Best case scenario is when array is sorted, we have linear time $O(n)$. Worst case scenario when array sorted in reverse order, we have $O(n^2)$.

Another flavors of insertion sort is using a recursive procedure where we recursively sort `A[1..n-1]` and then insert `A[n]` into the sorted array `A[1..n-1]`.  
Another faster way is to implement binary search within the while loop, which has $O(\lg n)$ time instead of linear search time for insertion position. 


## Selection Sort

```python
def selection_sort(a):
    for i in range(len(a)-1):
        min_idx = i
        for j in range(i+1, len(a)):
            if a[j] < a[min_idx]:
                min_idx = j

        if min_idx != i:
            a[i], a[min_idx] = a[min_idx], a[i]
```

Finds the smallest element in 2 and replace with `a[0]`, second smallest and replace with `a[1]`, etc...

Best and worst running times are the same and they are $O(n^2)$.

 
## Merge Sort

Divide an $n$-element sequence into two subsequences of sizes $n/2$ each. Recursively sort the two subsequences and merge them after sorting.  

```python

def merge(A, p, q, r):
    """
    Merges the two sorted sub-arrays A[p:q] and A[q+1:r] such that the
    final subarray a[q:r] is in sorted order.

    Parameters
    ----------
    A : list
        A list of numbers of size `n`.

    p : int
        The begin index of the left array.

    q : int
        The begin index of the right array, and 1 + end index of left array.

    r : int
        End index of right array + 1.

    Return
    ------
    : None
        This function sorts array `A` in-place.
    """
    L, R = A[p:q], A[q:r]
    i, j = 0, 0

    for k in range(p, r):
        try:
            if L[i] <= R[j]:
                A[k] = L[i]
                i += 1
            else:
                A[k] = R[j]
                j += 1
        except IndexError:
            if i >= len(L):
                A[k] = R[j]
                j += 1
            elif j >= len(R):
                A[k] = L[i]
                i += 1


def merge_sort(a, p=0, r=None):
    if r is None:
        r = len(a)

    if r - p > 1:
        q = (p + r)//2
        merge_sort(a, p, q)
        merge_sort(a, q, r)
        merge(a, p, q, r)

```

Merge sort has a running time of $O(n\lg n)$.

## Bubble sort

## Heap sort

We first need to define what is a heap. 

## Quick sort

## Count sort

## Radix sort

## Sorting in python

In python, there is the built in algorithm `sorted()`.  So what algorithm does this function use?

## References
