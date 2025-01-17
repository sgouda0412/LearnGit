study of organizing data efficiently
Data structures manage how data is stored and accessed, while algorithms focus on processing this data
```python
n % 2 == 0 [ # Even No check]
n & 1 == 0 [ # Even No Check]
n == ( n >> 1 ) << 1 [ # For Even Check]

a, b = b, a [ # Swap numbers]

7 - n [opposite of dice]

n * ( n + 1 ) // 2 [sum of nth natural numbers]

d = arr[i] - arr[i - 1] [difference in AP]

n = n % 10 -> Extract the last digit

n //= 10 -> Remove the last digit

for i in range(n, n):  # Empty range , Loops doesn't execute here
	if n % i == 0:
		return False
```


# Check divisibility from 2 to the square root of n
```python
for i in range(2, int(math.sqrt(n)) + 1):  [ # + 1 we are check for all the value upto n]
	if n % i == 0:
		return False

check if y is a power of x
if x == 1:
	return True
pow = 1
while pow < y:
	pow = pow * x
return pow == y

append 0 in 2 D matrix -> [[0 for i in range(cols)] for j in range(rows)]
append 0 in 1 D matrix -> [0 for i in range(N)]


d.setdefault("key", value) "if value already present than no change" 
							if value not present add it to dictionary

d.get(key, default_value)

curr = head
while curr.next:		# Traverse to last Node
	curr = curr.next

temp = Node(x)
curr.next = temp
return head

return (((x2 - x1)**2 + (y2 - y1)**2)**0.5)  # The distance between 2 points

if (a + b <= c) or (a + c <= b) or (b + c <= a) : return False else: return True  # Valid Triangle 
res = 1
for i in range(n+1):res *= i  # Factorial of a number
```
# insert at beg
```python
temp = Node(x)
temp.next = head
head = temp
return head
```

# insert at end
```python
temp = Node(x)
if head is None:
	return Node(x)
curr = head
while curr.next:
	curr = curr.next
curr.next = temp
return head
```

# insert at specific position

```python
if pos < 1:
	print("Invalid") return head
if pos == 1:
	temp = Node(x)
	temp.next = head
	return temp
count = 0
curr = head
while curr:				# when not traversing till last node,  always use while curr:
	count += 1
	if count == k - 1:
		temp = Node(x)
		temp.next = curr.next
		curr.next = temp
		break
	curr = curr.next
return head
```

#SQLNotes
sub query
---------
sub query in select statement should return only 1 row
sub query in From statement act as a temporary or subset of table
sub query in where statement acts as a filter query -> can return 1 row or multiple row
```SQL
CREATE VIEW view1 AS 
	SELECT roll_no, name, subject FROM student;  # A Virtual table, selecting only a specific set of data. 

SELECT * FROM view1;
```

Recursion-> function calling itself, stop only after hitting a Base Condition.

### Tower of Hanoi
```python
def toh(n, fromm, to, aux):
	if n == 0:
		return 0
	if n == 1:
		return 1
	x = toh(n - 1, fromm, aux, to)
	y = toh(n - 1, aux , to, fromm)
	return x + y + 1
```

### sqrt
```
res = 1
while res * res <= n:
	res += 1
return res - 1
```
