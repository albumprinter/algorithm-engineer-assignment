<img src="default_albelli.nl.jpg" width="200">

# Algorigthm Engineer Technical Assignment

## Things we look for in this test

We expect the candidate to show us their skills in building testable and maintainable software with design and architecture in mind using industry best practices.
We value _simple_ more highly than _complex_, _working_ is better than _nice_. Readability matters.

## Business flow

A customer wants to order photobook with multiple pages.  
State of art algorithm analyzes pictures and predicts the order these pictures should follow in photobook.  
Now we need to place pictures to specific pages in photobook, so that order is not broken.

## Assignment

Create a an app that parses the ordered list of pictures, and calculates the mimimum number of pages these pictures would fit.  

Every picture has an unique id, from 1 to PictureCount.
Picture dependencies are listed as pairs [PictureId1, PictureId2].  This means that PictureId1 should go before PictureId2 in the photobook.
Whole list of dependencies would look like [[1,2],[1,4],[4,5]]. This means picture 1 should go before picures 2 and 4, and picture 4 should go before picture 5.

The last parameter that needs to be taken into consideration is Limit.  This means every page can have _at most_ Limit pictures per page. 

Format of the input file
```
PictureCount
[[id1, id2],[id3,id4]...]
Limit
```


## Example 1
```
          ┌───┐
          │ 2 │
          └───┘
            │
            │
            ▼
┌───┐     ┌───┐
│ 3 │ ──▶ | 1 │
└───┘     └───┘
            │
            │
            ▼
          ┌───┐
          │ 4 │
          └───┘
```

input file
```
4
[[2,1],[3,1],[1,4]]
2
```
Expected output: 3 

Explanation: 
The figure above representa a picture dependency graph. 
We can put pictures  2 and 3 on the first page, then we put picture  1 on the second page and finally put picture 4 on the third page.


## Example 2

```


          ┌───┐
          │ 2 │
          └───┘
            │
            │
            ▼
┌───┐     ┌───┐     ┌───┐
│ 4 │ ──▶ │ 1 │ ◀──│ 3 │
└───┘     └───┘     └───┘
            │
            │
            ▼
          ┌───┐
          │ 5 │
          └───┘

```

input file
```
5
[[2,1],[3,1],[4,1],[1,5]]
2
```

Expected output: 4

Explanation:


The figure above represents a picture dependency graph. 
Optimal solution for this case would be putting pictures 2 and 3 on the first page.
Then put picture 4 on the second page. 
Put picture 1 on the third page.
And finally put picture 5 on the fourth page.


## Example 3

input file
```
11
[]
2
```

Expected outcome:
6

## Constraints

    1 <= PictureCount <= 15
    1 <= Limit <= PictureCount
    0 <= dependencies.length <= PictureCount * (PictureCount-1) / 2
    All prerequisite relationships are distinct, that is, dependencies[i] != dependencies[j].
    The given graph is a directed acyclic graph.


## Source Code

You should create a public GitHub and let us know when you've completed the exercise.

## Tools and libraries

You are free to use any additional third-party libraries and frameworks.

## Additional information

The authentication/authorization of the API is outside of scope.
Feel free to improve the application as **you** see fit (e.g. no logging but some tests are nice).  
If you have any questions please reach out to us.
