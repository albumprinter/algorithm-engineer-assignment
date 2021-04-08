<img src="default_albelli.nl.jpg" width="200">

# Algorithm Engineer Technical Assignment

## Things we look for in this test

We expect the candidate to show us they can solve algorithmic problems in a
clear and concise manner. Test cases should be included to demonstrate
correctness. We value _simple_ more highly than _complex_, _working_ is better
than _nice_. Readability matters.

## Problem

A customer would like to place their photos in a photobook. Flipping through the
book, certain photos are expected to be placed on a page before others. For
example:

- a picture of a wedding should come on a page before one of the honeymoon
- photos of a child unwrapping their birthday gift should be on earlier pages
  than pictures of them playing with their new toy

Our state-of-the-art algorithms can predict which pairs of photos in a set have
this property. We want to automatically place all the photos in a book using as
few pages as possible.

## Assignment

The first line of the input consists of three numbers `n`, `m` and `k`, where
`n` is the total number of photos in the set (labeled `1,2,..,n`) and `m` the
maximum allowed number of photos per page.

Then follow `k` lines, with on every i<sup>th</sup> line two numbers `u_i` and
`v_i`. This defines the property that photo `u_i` should be on a page that comes
strictly before the page containing photo `v_i`.

Output should consist of a single line, containing either a single number
indicating the minimum number of pages required to place all photos, or
`Impossible` if no valid book can be created.

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

Input file

```
4 2 3
2 1
3 1
1 4
```

Expected output: `3`

Pictures `2` and `3` can go on the first page, `1` on the second, and `4` on the
third.

## Example 2

```
          ┌───┐
          │ 2 │
          └───┘
            │
            │
            ▼
┌───┐     ┌───┐     ┌───┐
│ 4 │ ──▶ │ 1 │ ◀── │ 3 │
└───┘     └───┘     └───┘
            │
            │
            ▼
          ┌───┐
          │ 5 │
          └───┘
```

Input file

```
5 2 4
2 1
3 1
4 1
1 5
```

Expected output: `4`

Pictures `2` and `4` can go on the first page, `3` on the second, `1` on the
third, and `5` on the fourth.

## Example 3

input file

```
11 2 0
```

Expected output: `6`

## Constraints

    1 <= n <= 15
    1 <= m <= n
    0 <= k <= n * (n - 1) / 2
    1 <= u_i, v_i <= n for all i

## Source Code

You should create a public GitHub and let us know when you've completed the
exercise. Only C/C++, Java(Kotlin, Scala), Rust and C#(F#) are allowed.

## Tools and libraries

You are free to use any additional third-party libraries and/or frameworks.

## Additional information

Document a method of compiling your code and running a test case(s).

Your application should be able to take input from the test file, and print only the result number to stdout.

```shell
$ myprogram  input1.txt
3
```

## Bonus requirements
After you finish your assignment, you can convert it to Python and add to the same repo. This is not a hard requirement, but might add some bonus points.
