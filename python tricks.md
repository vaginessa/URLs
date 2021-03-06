#### Convert to int, float
`int()` or `float()`

#### Convert to string
`str()`

#### Split a string to characters
`list("Hello")`

#### Add to, remove from list
```
n = []  
n.append(3)  
n.append(4)  
n.pop(0) ## index position  
n.remove(4) ## actual value  
```

#### Accept list of comma separated integers
`n = [int(i) for i in input().split(',')]`

#### Split a number into corresponding digits
`arr = [int(i) for i in list(str(24869453))]`

#### Remove duplicates from list
`l = list(set(l))`

#### Reverse a list
`L = L[::-1]`

#### Copy a list
`arrcpy = arr[:]`

#### Print upto 6 decimal places
`print('{0:.6f}')`

#### Find max of a list below a maximum limit
`max([i for i in m if i <= 2]) ## finds max number of list m below 2`

#### Use global variable
```
def fun1():  
  global s  
  s = "Hello"  

def fun2():  
  print(s)  
```

#### Convert decimal number to any other base
```
def findToBase(num, base):  

  if num == 0:  
    return 0  

  if num < base:  
    r = num  
  else:  
    r = num % base  

  return int(str(findToBase(int(num/base), base)) + str(r))  
```

#### nCr in list
```
def get_nCr(r, arr):  
    nCr = []  
    if r == 1:  
        for i in arr:  
            nCr.append([i])  
    elif r > 1:  
        n = len(arr)  
        for i in range(n-r+1):  
            a = arr[i]  
            last = get_nCr(r-1, arr[i+1:])  
            element = []  
            for l in last:  
                l = [a] + l  
                if l not in nCr and l not in element: element.append(l)  
            nCr += element  

    return nCr  
```

#### find lcm of a list
```
from math import gcd  
def getLCM(arr):  

  LCM = arr[0]  
  for i in arr[1:]:  
    LCM = LCM*i/gcd(int(LCM),i)  

  return LCM  
```

#### Magic 3*3 matrix possible cases
[  
[[8, 1, 6], [3, 5, 7], [4, 9, 2]],  
[[6, 1, 8], [7, 5, 3], [2, 9, 4]],  
[[4, 9, 2], [3, 5, 7], [8, 1, 6]],  
[[2, 9, 4], [7, 5, 3], [6, 1, 8]],  
[[8, 3, 4], [1, 5, 9], [6, 7, 2]],  
[[4, 3, 8], [9, 5, 1], [2, 7, 6]],  
[[6, 7, 2], [1, 5, 9], [8, 3, 4]],  
[[2, 7, 6], [9, 5, 1], [4, 3, 8]],]  

(https://www.hackerrank.com/challenges/magic-square-forming/problem)[https://www.hackerrank.com/challenges/magic-square-forming/problem]  

## Recursive way to get list of all subsets which sum up to a specific number  
```
def main():  
    global all  
    all = []  
    subsetSum(6, [1,2,3,4,5,3])  
    print(all)  

def subsetSum(m, l):  
    if (len(l) == 0):  
        return  
    if (sum(l) == m and l not in all):  
        all.append(l)  
    for i in range(len(l)):  
        subsetSum(m, l[:i] + l[i+1:])  
        
if __name__ == '__main__':  
    main()  
```
Gives output: `[[3, 3], [2, 4], [1, 5], [1, 2, 3]]`  
