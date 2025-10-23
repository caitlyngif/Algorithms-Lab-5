# CMPS 2200 Reciation 5
## Answers

**Name:** Caitlyn Gifford


Place all written answers from `recitation-05.md` here for easier grading.







- **1b.**

Sorted permutations:

|   n |   selection sort |   qsort-fixed-pivot |   qsort-random-pivot |
|-----|------------------|---------------------|----------------------|
| 100 |            8.802 |               0.283 |                0.065 |
| 200 |           25.225 |               0.794 |                0.123 |
| 500 |           57.734 |               5.117 |                0.355 |
| 995 |          247.297 |              19.777 |                0.809 |

Random permutations:

|   n |   selection sort |   qsort-fixed-pivot |   qsort-random-pivot |
|-----|------------------|---------------------|----------------------|
| 100 |            7.791 |               0.059 |                0.066 |
| 200 |           18.798 |               0.124 |                0.144 |
| 500 |           86.598 |               0.387 |                0.383 |
| 995 |          266.802 |               0.961 |                0.934 |

selection sort matches its asymptotic bound of O(n^2). It performs the worst on both the sorted and random permutations due to it having to scan the list to find the minimum, regardless of whether the minimum is the first index.

qsort-fixed-pivot runs faster on the random permutations, but can reach worst case O(n^2) upper bound when it is run on sorted permutations. This is because pivoting from the first (smallest) index creates unbalanced partitions.

qsort-random-pivot runs about the same on both sorted and random permutations, and matches the O(n log n) bound regardless. 

- **1c.**

Sorted permutation:

|   n |   qsort-random-pivot |   Timsort |
|-----|----------------------|-----------|
| 100 |                0.143 |     0.002 |
| 200 |                0.418 |     0.002 |
| 500 |                0.767 |     0.003 |
| 995 |                1.503 |     0.005 |

Random permutation:

|   n |   qsort-random-pivot |   Timsort |
|-----|----------------------|-----------|
| 100 |                0.108 |     0.008 |
| 200 |                0.214 |     0.015 |
| 500 |                0.613 |     0.041 |
| 995 |                1.498 |     0.088 |

Timsort's best case O(n) is achieved on sorted permutations. Its worst case is O(n log n). It is faster than qsort-random-pivot (which was the fastest of the three from 1b) on both sorted and random permutations, but Timsort outperforms qsort-random-pivot the most when it is sorted.