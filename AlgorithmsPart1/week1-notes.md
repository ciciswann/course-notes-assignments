# Week 1

### Merge Sort
**Implementations**: <a href="#"><img src="https://img.shields.io/badge/Python-blue"></a> <a href="#"><img src="https://img.shields.io/badge/C++-green"></a>
* Divide and Conquer 
* Simple Pseudocode:
  * recursively sort 1st half of input array
  * rescursively sort 2nd half of input array
  * merge two sorted sublists into one
* populate the output array in sorted order 
* Pseudocode for merge:
<img width="873" alt="Screen Shot 2022-04-13 at 6 25 01 🌃" src="https://user-images.githubusercontent.com/17733481/163295720-cff5bf3b-6dbd-46b8-971c-e209d3826fbd.png">

### Guiding Principles for Analysis of Algorithms
* **Guiding Principle #1** - Worst-case analysis: our running time bound holds for every input of length n. Appropriate for general purpose routines.
  * BONUS: worst-case usually easier to analyze 
* **Guiding Principle #2** - Won't pay much attention to constant factors, lower-order terms.
  * Justifications: way easier, constants depend on architecture/compiler/programmer anyway, lose very little predictive power
* **Guiding Principle #3** - Asymptotic analysis: focus on running time for large input sizes n. E.g. 6nlogn + 6n "better than" any function that has a quadratic dependence on n (iff n is sufficiently large)
  * Justifications: only big problems are interesting! 
  * [Moore's Law](https://www.synopsys.com/glossary/what-is-moores-law.html#:~:text=Moore's%20law%20is%20a%20term,doubles%20about%20every%20two%20years.)
* What is a "fast" algorithm? - worst case running time grows slowly as a function of the input size

### Asymptotic Analysis
* The Gist - Importance: vocabulary for the design and analysis of algorithms (e.g. "big-oh" notation)
  * identifies a sweet spot for high level reasoning about algorithms
  * coarse enough to suppress architecture/language/compiler-dependent details
  * sharp enough to make useful comparisons btwn different algos, especially on large inputs (e.g., sorting or integer multiplication)
* Idea: suppress constant factors and lower-order terms
* lower-order terms become increasingly irrelevant for large inputs
* Example: 6nlogn+6n would equate to nlogn - drop the 6n since it's the lower order term 
* Example: One Loop - O(n)

### Big Oh Notation
* 
