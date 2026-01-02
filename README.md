# Balanced-Subarrays

You are given an array A of N integers.

A subarray is called balanced if the number of even elements in the subarray is equal to the number of odd elements.

Your task is to count the total number of balanced subarrays in the array A.

Input
The first line contains a single integer 
N — the size of the array.
The second line contains 
N integers 

Output
Print a single integer — the number of balanced subarrays.
Constraints

1≤N≤10 
1≤A[i]≤10 

n = int(input())
A = list(map(int, input().split()))

from collections import defaultdict

freq = defaultdict(int)
freq[0] = 1   # empty prefix

balance = 0
ans = 0

for x in A:
    if x % 2 == 0:
        balance += 1
    else:
        balance -= 1

    ans += freq[balance]
    freq[balance] += 1

print(ans)
 
