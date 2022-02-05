# Linear Data Structures

Here we are looking at basic datastructures.  

## Arrays

### Basic Operations

The basic operations supported by an array are as stated below −  
1.Traverse − print all the array elements one by one.  
2.Insertion − Adds an element at the given index.  
3.Deletion − Deletes an element at the given index.  
4.Search − Searches an element using the given index or by the value.  
5.Update − Updates an element at the given index. 

## List

### Basic List Operations

1. Length
2. Concatenation
3. Repetition  
   * `['Hi']*2 will give ['Hi','Hi']`
4. Membership
   * `1 in [1,2] will give True` 
5. Delete List Element  
   * `list1 = ['physics', 'chemistry', 1997, 2000]`  
      `del list1[2]`

## Dictionary

Keys must be immutable. Which means you can use strings, numbers or tuples as dictionary keys but something like ['key'] is not allowed.

## Matrix

Matrix is created uing numoy array, adding a column and deleting a column is tricky come back and learn.  

### Adding a Column

We can add column to a matrix using the insert() method. here we have to mention the index where we want to add the column and a array containing the new values of the columns added.In the below example we add t a new column at the fifth position from the beginning.

`from numpy import *`  
`m = array([['Mon',18,20,22,17],['Tue',11,18,21,18],`  
`['Wed',15,21,20,19],['Thu',11,20,22,21],`  
`['Fri',18,17,23,22],['Sat',12,22,20,18],`  
`['Sun',13,15,19,16]])`  
`m_c = insert(m,[5],[[1],[2],[3],[4],[5],[6],[7]],1)`  

## Sets

Mathematically a set is a collection of items not in any particular order. A Python set is similar to this mathematical definition with below additional conditions.  

1. The elements in the set cannot be duplicates.
2. The elements in the set are immutable(cannot be modified) but the set as a whole is mutable.
3. There is no index attached to any element in a python set. So they do not support any indexing or slicing operation.

A set is created by using the set() function or placing all the elements within a pair of curly braces.  
`Days=set(["Mon","Tue","Wed","Thu","Fri","Sat","Sun"])`  
`Months={"Jan","Feb","Mar"}`  

