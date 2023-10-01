### Resources used:
To understand Prolog used ChatGPT and videos on Youtube.

### Naming convention:
As per assignment documentation.

### How to run:
## 1
Open Prolog Terminal (swipl in VSC).
## 2
Use command to open the file: consult("<filename>").
## 3
Run function in file directly by function call with args constraints.

### Logic and Design Decisions:
## subseq.pl:
    It checks whether the head element of both list match, if it match then it recursively call the same predicate without the head element. If the list turns out to be empty then answer is true. Else answer is false.
    # How to run :- 
        Call the predicate subsequence(A,B).
        True - A is subsequence of B.
        False - Otherwise.
    # Sample Queries :-
        ?- subsequence([1,2,3],[4,5,1,5,2,7,3]).
        true .

        ?- subsequence([1,2,3],[4,5,2,7,3]).
        false.

## triplicates.pl:
    It checks whether if the list of elements L does not contain three (or more) copies of an element by checking for count of every element. If count exceeds 2 then return false.
    # How to run :- 
        Call the predicate has_no_triplicates(L).
        True - If there is no triplicate in A
        False - Otherwise.
    # Sample Queries :-
        ?- has_no_triplicates([1,1,2,34,56,73,5,2,6,2]).
        false.

        ?- has_no_triplicates([1,1,2,34,56,73,5,2,6]).
        true .

## arith.pl:
    It returns a single valid equation with the help of list of elements given.
    The logic involves checking all possible permutation of number and operators. And return it.
    # How to run :- 
        Call the predicate arith(L).
    # Bonus :-
        To check for more equations remove the '!,' from the solve predicate.
    # Design Decision :- 
        Bracketing introduced to check correctness. If more operators introduced (Eg. '*','/').
        '--' as -a where a is an integer is used to apply negation of -a as to maintain the visibility of -a, --a is used.

    # Sample Queries :-
        ?- arith([1,2,1]).
        -1=-(2-1)
        true.

        ?- arith([1,2,1,5,4,3]).
        -1=+(2+(1-(5-(4-3))))
        true.

        ?- arith([1,2,1,5,4]).
        false.

## ABCD.pl:
    It returns two values,
    1. -> Who paddled twice with output showing X paddled twice.
    2. -> The path followed for travelling.
    Convention of path followed : 1,3,5 occurence shows the travel from left to right.
                                  2,4 occurence shows the travel from right to left.
    # How to run :- 
        Call the predicate abcd.
    # Bonus :-
        For multiple paths use ';' while calling abcd predicate.

    # Sample queries :-
        ?- abcd.
            Carol paddled twice.
            Path :[[davis,alice],[alice],[carol,alice],[carol],[bob,carol]]
            true ;
            Carol paddled twice.
            Path :[[carol,alice],[alice],[davis,alice],[carol],[bob,carol]]
            true ;
            Carol paddled twice.
            Path :[[davis,alice],[alice],[bob,carol],[carol],[carol,alice]]
            true ;
            Carol paddled twice.
            Path :[[bob,carol],[carol],[davis,alice],[alice],[carol,alice]]
            true ;
            Carol paddled twice.
            Path :[[carol,alice],[carol],[bob,carol],[alice],[davis,alice]]
            true ;
            Carol paddled twice.
            Path :[[bob,carol],[carol],[carol,alice],[alice],[davis,alice]]
            true ;
            false.
            
# Author :- Mayank.