# Fundamentals of Python

## Chương trình đầu tiên
```python
print("Hello World")
```

```
Hello World
```

## Cú pháp của Python
Các cú pháp của python sẽ phân biệt các ký tự thường và hoa.

### Từ khoá (keyword)

Các từ khóa là từ được định nghĩa sẵn và không thể sử dụng làm tên biến, hàm hoặc bất kỳ định danh nào khác.

Sau đây là các từ khoá của Python (phiên bản 3.10 trở lên):

````python
False      await      else       import     pass
None       break      except     in         raise
True       class      finally    is         return
and        continue   for        lambda     try
as         def        from       nonlocal   while
assert     del        global     not        with
async      elif       if         or         yield
````

Ta có thể sử dụng module `keyword` để kiểm tra danh sách từ khoá hiện tại trong Python:

```python
import keyword
print(keyword.kwlist)
```

### Chú thích (comment)

Để chú thích 1 dòng trong python ta sử dụng ký tự `#`:

```python
# print("Hello World")
```

Sử dụng `'''` để chú thích 1 đoạn (nhiều dòng):

```python
'''
print("We are in a comment")
print ("We are still in a comment")
'''
```

### Dấu ' và "

Python sẽ không phân biệt dấu ```'``` và ```"```.

Thông thường đối với biến chỉ có 1 từ thì ta để dấu `'`. Còn đối với 1 câu hay đoạn thì ta để dấu `"` hoặc `"""`.

```python
word = 'word'
sentence = "This is a sentence."
message = """This's message will ... span several lines."""
```

### Căn lề

Trong Python, ta bắt buộc phải căn lề để bao các khối lệnh của hàm, lớp hoặc luồng điều khiển,...

 Số khoảng trắng dùng để căn lề có thể tuỳ ý nhưng tất cả lệnh ttrong một khối phải được canh lề như nhau.

 ```python
 if True:
    print "Answer"
    print "True"
 else:
    print "False"
 ```

 ### Viết câu lệnh

 Sử dụng ký tự `\` để có thể viết được trên nhiều dòng:

 ```python
 print("This message has writen \
in two lines")
 ```

 ```
 This message has writen in two lines
 ```

Sử dụng dấu `;` để viết nhiều lệnh trên dòng

```python
import sys; x = 'foo'; sys.stdout.write(x + '\n')
```

## Biến

Biến là một đại diện cho một giá trị nhất định như integer, float, string, boolean,...

1. Số nguyên (integer)

```python 
age = 10
age: int = 10
```

2. Số thực (float)

```python 
height = 1.65
height: float = 1.65
```

3. Biến chuỗi (String)

```python
name = 'Python'
name: str = 'Python
```

Chuỗi có nhiều kiểu định dạng khác nhau.

```python
message1 = "Name: %s, Age: %d, Height: %.2f" % (name, age, height)
message2 = "Name: {}, Age: {}, Height: {:.2f}".format(name, age, height)
message3 = f"Name: {name}, Age: {age}, Height: {height:.2f}"
```

```
Name = Python, Age: 10, Height: 1.65
```

Ngoài ra còn có một số ký tự đặc biệt trong chuỗi:

```markdown
\n: Di chuyển đến dòng tiếp theo
\t: Di chuyển đến khoảng cách tiếp theo nếu nhấn phím “Tab”
\\: Thêm 1 ký tự \
\": Thêm 1 ký tự "
\': Thêm 1 ký tự '
```

4. Biến Boolean lưu giá trị `True` hoặc `False`

```python
is_student = True
is_student: bool = True
```

### Ép kiểu (Type casting)

Ép kiểu biến từ kiểu dữ liệu này sang kiểu dữ liệu khác.

```python
age: int = 25

print(type(age))

age = float(age)

print(type(age))
print(age)
```

```
<class 'int'>
<class 'float'>
25.0
```

### User input

Sử dụng để nhập dữ liệu từ bàn phím người dùng. Dữ liệu mặc định sẽ là kiểu string, để đổi sang kiểu khác ta sẽ thực hiện ép kiểu.

```python
name = input("Your name:")
age = int(input("Your age:"))

print(f"Name: {name}, Age: {age}")
```

## Toán tử (arithmetic operator)

### Phép toán số học

![Arithmetic Operator](./images/arithmetic_operators.png)

### Toán tử so sánh

Giá trị trả về là kiểu `bool`

![Comparison Operator](./images/comparison_operators.png)

### Phép gán

![Assignment Operator](./images/assignment_operators.png)

### Toán tử logic

![Logical Operator](./images/logical_operators.png)

## Cấu trúc điều khiển (Flow control)

### if else stament

```python
age: int = 20

if age >= 18:
    print('adult')
else:
    print('child')
```

```
adult
```

Sử dụng nhiều if else hơn:

```python
if age >= 60:
    print('old')
elif age >= 18:
    print('adult')
else:
    print('child')
```

Viết trên 1 dòng lệnh (ngắn gọn):

```python
print('adult' if age >= 18 else 'child')
```

### match case (python 3.10+)

```python
match value:
    case 'a':
        return "Option A"
    case 'b':
        return "Option B"
    case 'c':
        return "Option C"
    case _: # default
        return "Unknown option"
```

## Cấu trúc lặp

### Vòng lặp while

```python
number: int = 6

while number >= 1:
    number -= 1
    print(number)
```

```
5
4
3
2
1
0
```

### Lệnh điều khiển vòng lặp.

Lệnh `continue`: bỏ qua các câu lệnh còn lại trong vòng lặp và tiếp tục vòng lặp tiếp theo.

```python
number: int = 6

while number >= 1:
    number -= 1
    if number == 3:
        continue
    print(number)
```
```
5
4
2
1
0
```

Lệnh `break`: bỏ qua các câu lệnh còn lại trong vòng lặp và kết thúc vòng lặp.

```python
number: int = 6

while number >= 1:
    number -= 1
    if number == 3:
        continue
    print(number)
```
```
5
4
```

### Vòng lặp for

```python
for i in range(5):
    print(i)
```
```
0
1
2
3
4
```