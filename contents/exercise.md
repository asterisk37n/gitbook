# Exericise
It's time you code for yourself! You can see a any site and any book.

Questions 6 - 10 are sited from atcoder and have test cases.
Question 6 and 7 are from [Atcoder Beginner Contest 063](http://abc063.contest.atcoder.jp/)
Question 8 are from [Atcoder Beginner Contest 053](http://abc053.contest.atcoder.jp/)
Question 9 is from [Atcoder Biginner Contest 066 C Push Push](http://abc066.contest.atcoder.jp/)
Question 10 is from [Atcoder Regular Contest 076](http://arc076.contest.atcoder.jp/)

---

## Questions {#questions}

### Q1 Odd sum
Caulculate the sum of 1 + 3 + ... + 99 + 100

[answer](#answer1)

### Q2 FizzBuzz
Counts the numbers, but when the number is divisible by three, replace by "fizz",
divisible by fibe by the word "buzz", and divisible by both by "fizzbuzz"
1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, FIzz, 13, 14, FizzBuzz, 16, 17, Fizz, 19, Buzz, Fizz, ...

[answer](#answer2)

### Q3 Fibonacci numbers
Add the last two numbers to create the next number. Start with 1, 1.
1
1
2
3
5
8
11
...

[answer](#answer3)

### Q4 
Find the integers x, y, and z satisfying $$x + y + z = 1000, 0 < x <= y <= z$$

[answer](#answer4)

### Q5 Hello world in the rectangular
Write a function that takes a list of strings an pdrints them, one per line, in a rectangular frame. For example the list ["Hello", "World", "in", "a", "frame"] gets printed as:

```py
*********
* Hello *
* World *
* in    *
* a     *
* frame *
*********
```

[answer](#answer5)

### Q6 Restricted

You have two inputs A and B. Calculate the value A+B and output it, but when A + B is more than 9, output 'error'.
Sample Input 1
```
6 3
```
Sample Output 1
```
9
```
Sample Input 2
```
6 4
```
Sample Output 2
```
error
```

[answer](#answer6)

### Q7 Varied
You are given a string S consisting of lowercase English letters. Determine whether all the characters in S are different.
Constraints

    2≤|S|≤26, where |S| denotes the length of S.
    S consists of lowercase English letters.

Sample Input 1
```
abcdexyz
```

Sample Output 1
```
yes
```

Sample Input 2
```
different
```
Sample Output2
'''
no
'''

[answer](#answer7)

### Q8 Judge it the number is more than 1200
You are given an integer x. If x is less than 1200, print 'ABC', otherwise print('ARC')
Sample Input 1
```
1000
```
Sample Output 1
```
ABC
```

Sample Input 1
```
2000
```
Sample Output 2
```
ARC
```

[answer](#answer8)

### Q9 Push and reverse

Problem Statement

You are given an integer sequence of length n, a1,…,an. Let us consider performing the following n operations on an empty sequence b.

The i-th operation is as follows:

    Append ai to the end of b.
    Reverse the order of the elements in b.

Find the sequence b obtained after these n operations.
Constraints

    1≤n≤2×105
    0≤ai≤109
    n and ai are integers.

Sample Input 1
```
1 2 3 4
```
Sample Output 1
```
4 2 1 3
```
As operation follows
1 -> 1
1, 2 -> 2, 1
2, 1, 3 -> 3, 1, 2
3, 1, 2, 4 -> 4, 2, 1, 3

Sample Input 2
```
1 2 3
```
Sample Output 2
```
3 2 1
```
Sample Input 3
```
1000000
```
Sample Output 3
```
1000000
```

[answer](#answer9)


### Q10 Monkey and Dog Combinations
Snuke has N dogs and M monkeys. He wants them to line up in a row.

As a Japanese saying goes, these dogs and monkeys are on bad terms. ("ken'en no naka", literally "the relationship of dogs and monkeys", means a relationship of mutual hatred.) Snuke is trying to reconsile them, by arranging the animals so that there are neither two adjacent dogs nor two adjacent monkeys.

How many such arrangements there are? Find the count modulo $$10^9+7$$ (since animals cannot understand numbers larger than that). Here, dogs and monkeys are both distinguishable. Also, two arrangements that result from reversing each other are distinguished.
Constraints

    1≤N,M≤105

Sample 1
When N = 2, M = 2, Output is 8.

Monkey1, Dog1, Monkey2, Dog2
Monkey1, Dog2, Monkey2, Dog1
Monkey2, Dog1, Monkey1, Dog2
Monkey2, Dog2, Monkey1, Dog1
Dog1, Monkey1, Dog2, Monkey2
Dog1, Monkey2, Dog2, Monkey1
Dog2, Monkey1, Dog1, Monkey2
Dog2, Monkey2, Dog1, Monkey1

Sample 2
When N = 3, M = 2, output is 12.
Sample 3
When N = 1, M = 8, output is 0
When N = 100000, M = 100000, output is 530123477

[answer](#answer10)

---
## Answers {#answers}
### Answer 1 {#answer1}

```py
s = 0
for i in range(101):
    if i % 2 == 1:
        s += i
print(s)
```

You can simplify code by list comprehension. This is more pythonic way.
```py
odd_values = [i for i in range(101) if i % 2 == 1]
print(sum(odd_values))
```

### Answer 2{#answer2}
```py
for i in range(1, 101):
    if i % 15 == 0:
        print('FizzBuzz')
    elif i % 5 == 0:
        print('Buzz')
    elif i % 3 == 0:
        print('Fizz')
    else:
        print(i)
```

This is called generator with def ... yield. This is faster than above with list.
```
def fizzbuzz(n):
    for i in range(1, n+1):
        if i % 15 == 0:
            yield 'FizzBuzz'
        elif i % 5 == 0:
            yield 'Buzz'
        elif i % 3 == 0:
            yield 'Fizz'
        else:
            yield i

for x in fizzbuzz(100):
    print(x)
```

### Answer 3 {#answer3}
```py
def fib(n):
    if n == 0: return 0
    elif n == 1: return 1
    else: return fib(n-1) + fib(n-2)
```

Generator
```py
def fib():
    a,b = 0,1
    yield a
    yield b
    while True:
        a, b = b, a + b
        yield b
for i in fib():
    if i == 0: continue
    if i > 100: break
    print(i)
```

### Answer 4 {#answer4}

The most simple answer is the below. $$O(n^3)$$
```py
for x in range(1,100):
    for y in range(x, 100):
        for z in range(y, 100):
            if x + y + z == 100:
                print(x, y, z)
```

The third loop fo z is not needed. $$O(n^2)$$
```py
for x in range(1, 100):
    for y in range(x, 100):
        z = 100 - x - y
        if y <= z <= 100:
            print(x, y, z)
```

x and y cannot be greater than 33 as x =< y =< z.
```py
for x in range(1, 34):
    for y in range(x, 34):
        z = 100 - x - y
        if y <= z <= 100:
            print(x, y, z)
```

### Answer 5 {#answer5}

```py
def rec(x):
    maxlen = len(max(x, key=len))
    print('*' * (maxlen + 2)) 
    for row in x:
        print('*' + row.ljust(maxlen, ' ') + '*')
    print('*' * (maxlen + 2))
```

### Answer 6 {#answer6}

```py
def less_than10(a, b):
    print(a + b if a + b < 10 else 'error')
``` 

```py
def less_than10(a, b):
    s = a + b
    if a + b < 10:
        print(a + b)
    else:
        print('error')
```

### Answer 7 {#answer7}
```py
def different(s):
    print('yes' if len(s) == len(set(s)) else 'no')
```

```py
def different(s):
   print(['no','yes'][len(s) == len(set(s))]) 
```

```py
def different(s):
    print('no' * (len(set(s)) < len(s)) or 'yes')
```

'no' \* false is false. false or 'yes' returns false
'no \* True is 'no'. 'no' or 'yes' returns 'no'.

### Answer 8 {#answer8}

```py
def lessthan1200(x):
    if x < 1200:
        print('ABC')
    else:
        print('ARC')
```

```py
def lessthan1200(x):
    print('ABC' if x < 1200 else 'ARC')
```

### Answer 9 {#answer9}
```py
def pushpush(x):
    y = []
    for i in x:
        y.append(i)
        y.reverse()
    return y # returns a list
pushpush([1,2,3,4]) # [4, 2, 1, 3]
```

This is faster and well thought.
```py
def pushpush(al):
    n = len(al)
    odd = al[1::2]
    even = al[0::2]
    odd.reverse()
    r = odd + even
    if(n%2 == 1):
        r.reverse()
    print(' '.join([str(i) for i in r])) returns a string
pushpush([1,2,3,4]) # 4 2 1 3
```

### Answer110 {#answer10}
This code works but heavy.
```py
import math
def monkeydog(n, m):
    print(0 if abs(n-m) > 1 else (math.factorial(n) * math.factorial(m) * (2 if n == m else 1)) % int(1e9 + 7))
```

This code is faster as it divide by modulo  when calculating n!
```py
def fac(n, mod):
    a = 1
    for i in range(n, 0, -1):
        a = (a * i) % mod
    return a
    
def solve(N, M):
    mod = 10**9 + 7
    if N > M + 1 or M > N + 1:
        return 0
    if N == M:
        return (2 * fac(N, mod)**2) % mod
    else:
        return (fac(N, mod) * fac(M, mod)) % mod
```
