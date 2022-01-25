# Week 3 - Sequences

* for ex. Determining the order of the nucleotides within a gene is known as DNA sequencing
* A sequence is a list of objects that are in order (like a queue)
  * ex. a string is a sequence of characters
* Computers can only understand finite sequences such as lists and arrays
* For notation we usually use a variable with index like a[i] to represent the elements of a sequence
* Usually has a pattern or a rule
* Sometimes we can relate an element of a sequence to its index, and express it using a formula
* If next term in a sequence can be expressed in terms of the previous terms, then it's called a recursive sequence
* Mathematical induction
    * suppose S(n) is a statement that depends on n. We use induction to prove that S(n) is true
        * it's true for the smallest value of n S(n[0])
        * if it's true for everything less than n, then it's truen for n, (S(n)->S(n+1))
* Recursion is an algorithmic technique where you solve a problem by using the solutions to smaller instances of the same problem
  * Factorial
* Mathematical induction ensures that the above technique is logically correct
