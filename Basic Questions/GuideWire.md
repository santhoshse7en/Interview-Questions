## GuideWire Interview Questions

## Question 1 - Print list in a tabular format
Align the value in right side and each cell contains exactly one value, create number of columns based on K. 

#### Solution

```python
import sys

def solution(A, K):
    new_list = [A[i:i + K] for i in range(0, len(A), K)]
    max_length = max([len(str(i)) for i in A])
    last_edge= len(new_list[:-1])
    
    for i, d in enumerate(new_list):
        sys.stdout.write('%s+\n' % (('+%s' % (max_length * '-')) * K))
        sys.stdout.write('|%s|\n' % ('|'.join(str(i).rjust(max_length) for i in d)))
        if i == last_edge:
            sys.stdout.write('%s+\n' % (('+%s' % (max_length * '-')) * len(d)))
```

#### Output

```shell

A = [4, 35, 80, 123, 12345, 44, 8, 5, 24, 3]
K = 4

solution(A,K)

+-----+-----+-----+-----+
|    4|   35|   80|  123|
+-----+-----+-----+-----+
|12345|   44|    8|    5|
+-----+-----+-----+-----+
|   24|    3|
+-----+-----+

```
