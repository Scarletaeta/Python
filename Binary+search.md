
# Binary Search Algorithm

## Exercise: 

Given a sorted array arr[ ] of n elements, write an function to search a given element x in arr[] by dividing by 2 repeatedly

## My approach:
i - the index of the element we wish to get

i_max - the index of the last item in the array. This will be equal to the length of the array minus 1 (as indexes start at 0)

i_min - the starting index. This will be 0 by default


- Firstly, i_max must be => i, otherwise, that element isn't even in the array. Don't start the search.

- The middle index is mid = (i_max - i_min)/2 + 1. I want this to be rounded up so I can search through the bottom half later.

- If i < mid, I need to repeat the process between i_min and mid - 1 (I already know that i != mid from the above step, so I can exclude it). 'elif'

- If i > mid I can repeat the process between mid + 1 (again excluding mid) and i_max, 'else'

- If i = mid, I've found the element! End the search and return the element. This must come first ('if')


```python
import math

def binary(array, i, i_max, i_min=0):
    '''
    array = array name
    i = index
    i_max = array end index (= len(array)-1 )
    i_min = array start index (default is 0)
    '''
    
    if i <= i_max:
        mid = int(math.ceil((i_max - i_min)/2 +1)) #math.ceil(...) (round up) -> decimal. NB: math.floor(...) (round down)
        if mid == i:
            return array[mid] #forgot to write it as an index!!!!!!!!!!!!!!!!
        elif i < mid:
            return binary(array, i, mid-1, i_min)  #search through the lower half
        else:
            return binary(array, i, i_max, mid+1)  #else -> search through the upper half
    else:
        return False
```


```python
arr = [2,10,20,30,40,50]
arr[3]
```




    30




```python
max = len(arr)-1
binary(arr, 3,max)
```




    30


