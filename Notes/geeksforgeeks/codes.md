```python
class Solution:
    def subarraySum(self, arr, target):
        # code here
        l = 0
        r = 0
        sum_arr = 0
        while r < len(arr):
            sum_arr += arr[r]

            while sum_arr > target:
                sum_arr -= arr[l]
                l += 1
            if sum_arr == target:
                return [l+1, r+1]
            r += 1
        return [-1]
```

```python
class Solution:
    # Function to return a list of integers denoting spiral traversal of matrix.
    def spirallyTraverse(self, matrix):
        # code here
        r = len(matrix)
        c = len(matrix[0])

        res = []
        left = 0
        right = c - 1
        top = 0
        bottom = r - 1

        while top <= bottom and left <= right:
            for i in range(left, right+1):
                res.append(matrix[top][i])
            top += 1

            for i in range(top, bottom + 1):
                res.append(matrix[i][right])
            right -= 1

            if top <= bottom:
                for i in range(right, left-1, -1):
                    res.append(matrix[bottom][i])
            bottom -= 1

            if left <= right:
                for i in range(bottom, top - 1, -1):
                    res.append(matrix[i][left])
            left += 1

        return res
```

```python

def gcd(a, b):
	if b == 0:
		return a
	else:
		while b > 0:
			temp =  a % b
			b = a
			a = temp
	return a 
```