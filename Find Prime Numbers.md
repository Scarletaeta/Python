
# Finding the prime numbers in a list of 0-n numbers

I made a function which returns True for primes and False for non primes between 0 and and n


```python
def primes(n):
    if n < 2:
        return False #0 and 1 are only divisible by 0 and themselves, but they aren't primes!
    for i in range(2, int(n**0.5 +1)): #divide the number, n, by all numbers up to its square root (this needs to be rounded UP, so I've used the integer of sqrt(n)+1 for safety). Could equally import math and use math.cieling() function to round up
        if n % i == 0:
            return False
    return True
```


```python
prime_list = [(p, primes(p)) for p in range(20)] #creates a tuple for p and whether it is a prime (True) or not (False)
for pair in prime_list: #for loop over all pairs in the list to print all pairs
    print(pair)
```

    (0, False)
    (1, False)
    (2, True)
    (3, True)
    (4, False)
    (5, True)
    (6, False)
    (7, True)
    (8, False)
    (9, False)
    (10, False)
    (11, True)
    (12, False)
    (13, True)
    (14, False)
    (15, False)
    (16, False)
    (17, True)
    (18, False)
    (19, True)
    


```python
prime_list = [p for p in range(1000) if primes(p)] #adds p values to array if 'True' (ie. if it's a prime)
print(prime_list)
```

    [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97, 101, 103, 107, 109, 113, 127, 131, 137, 139, 149, 151, 157, 163, 167, 173, 179, 181, 191, 193, 197, 199, 211, 223, 227, 229, 233, 239, 241, 251, 257, 263, 269, 271, 277, 281, 283, 293, 307, 311, 313, 317, 331, 337, 347, 349, 353, 359, 367, 373, 379, 383, 389, 397, 401, 409, 419, 421, 431, 433, 439, 443, 449, 457, 461, 463, 467, 479, 487, 491, 499, 503, 509, 521, 523, 541, 547, 557, 563, 569, 571, 577, 587, 593, 599, 601, 607, 613, 617, 619, 631, 641, 643, 647, 653, 659, 661, 673, 677, 683, 691, 701, 709, 719, 727, 733, 739, 743, 751, 757, 761, 769, 773, 787, 797, 809, 811, 821, 823, 827, 829, 839, 853, 857, 859, 863, 877, 881, 883, 887, 907, 911, 919, 929, 937, 941, 947, 953, 967, 971, 977, 983, 991, 997]
    
