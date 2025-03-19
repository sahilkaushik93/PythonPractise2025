# TOPICS:
1. Installation & Environment Setup
2. Data Types

#### 1. INSTALLATION & ENVIRONMENT SETUP


```python

# to check if it is installed or not
! python --version 

# to create virtual env in windows
# ! python -m venv venv 

# to activate virtual env
# ! venv\Scripts\activate 

# create a requirements.txt
# to install all packages in requirements.txt -> pip install -r requirements.txt
```

    Python 3.12.3
    

#### 2. Data Types


```python
import pandas as pd

# create a DataFrame
df = pd.DataFrame({
    "Category":["Numeric", "Numeric", "Numeric", "Text", "Boolean", "Sequence", "Sequence", "Sequence", "Set Types", "Set Types", "Mapping", "Binary", "Binary", "Binary", "None Type"],
    "Data Type": ["int", "float", "complex", "str", "bool", "list", "tuple", "range", "set", "frozenset", "dict", "bytes", "bytearray", "memoryview", "NoneType"],
    "Example": ["x = 10", "y = 10.5", "z = 3 + 4j", 
                's = "Hello"', "flag = True", "[1, 2, 3]", 
                "(1, 2, 3)", "range(5)", "{1, 2, 3}", 
                "frozenset([1,2,3])", '{"key": "value"}', 
                "b'hello'", "bytearray(5)", "memoryview(bytes(5))", "x = None"]
})

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Category</th>
      <th>Data Type</th>
      <th>Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Numeric</td>
      <td>int</td>
      <td>x = 10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Numeric</td>
      <td>float</td>
      <td>y = 10.5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Numeric</td>
      <td>complex</td>
      <td>z = 3 + 4j</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Text</td>
      <td>str</td>
      <td>s = "Hello"</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Boolean</td>
      <td>bool</td>
      <td>flag = True</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Sequence</td>
      <td>list</td>
      <td>[1, 2, 3]</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Sequence</td>
      <td>tuple</td>
      <td>(1, 2, 3)</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Sequence</td>
      <td>range</td>
      <td>range(5)</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Set Types</td>
      <td>set</td>
      <td>{1, 2, 3}</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Set Types</td>
      <td>frozenset</td>
      <td>frozenset([1,2,3])</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Mapping</td>
      <td>dict</td>
      <td>{"key": "value"}</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Binary</td>
      <td>bytes</td>
      <td>b'hello'</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Binary</td>
      <td>bytearray</td>
      <td>bytearray(5)</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Binary</td>
      <td>memoryview</td>
      <td>memoryview(bytes(5))</td>
    </tr>
    <tr>
      <th>14</th>
      <td>None Type</td>
      <td>NoneType</td>
      <td>x = None</td>
    </tr>
  </tbody>
</table>
</div>




```python
## NUMERIC DATA TYPES
# int methods
x = 10
x.bit_length() # 4 # number of bits required to represent the number in binary
x.to_bytes(2, byteorder='big') # b'\x00\n' # coverting to bytes
x.to_bytes(2, byteorder='little') # b'\n\x00' 
x.from_bytes(b'\x00\n', byteorder='big') # 10 # coverting from bytes
x.from_bytes(b'\n\x00', byteorder='little') # 10 
x.bit_count() # 2 # number of 1 bits in the binary representation of the number

# float methods
y = 10.5
y.as_integer_ratio() # (21, 2) # return a tuple of two integers whose ratio is exactly equal to the original float
y.is_integer() # False # check if the float is an integer
y.hex() # '0x1.5000000000000p+3' # hexadecimal representation of the float
fromhex = float.fromhex('0x1.5000000000000p+3') # 10.5 # convert from hexadecimal representation
from_float = float.fromhex(y.hex()) # 10.5

# complex methods
z = 3 + 4j
z.real # 3.0 # real part of the complex number
z.imag # 4.0 # imaginary part of the complex number
z.conjugate() # (3-4j) # conjugate of the complex number
z.conjugate().imag # -4.0

# Built-in functions for numeric data types
abs(-10) # 10 # absolute value
divmod(10, 3) # (3, 1) # quotient and remainder
pow(2, 3) # 8 # power
round(10.5) # 10 # round off
round(10.5, 0) # 10.0
round(10.5, 1) # 10.5
sum([1, 2, 3]) # 6 # sum of elements
max([1, 2, 3]) # 3 # maximum element
min([1, 2, 3]) # 1 # minimum element

# math module
import math
math.ceil(10.5) # 11 # round up
math.floor(10.5) # 10 # round down
math.trunc(10.5) # 10 # truncate
math.factorial(5) # 120 # factorial
math.gcd(10, 5) # 5 # greatest common divisor
math.lcm(10, 5) # 10 # least common multiple
math.isqrt(10) # 3 # integer square root
math.sqrt(10) # 3.1622776601683795 # square root
math.exp(1) # 2.718281828459045 # exponential
math.log(10) # 2.302585092994046 # natural logarithm
math.log10(10) # 1.0 # base 10 logarithm
math.log2(10) # 3.321928094887362 # base 2 logarithm
math.isfinite(float('inf')) # False # check if the number is finite
math.isinf(float('inf')) # True # check if the number is infinite
math.isnan(float('nan')) # True # check if the number is not a number
math.isclose(10.5, 10.5000000001) # True # check if two numbers are close
math.isclose(10.5, 10.5000001) # False
math.isclose(10.5, 10.5000001, rel_tol=1e-6) # True
math.isclose(10.5, 10.5000001, rel_tol=1e-7) # False
```


```python
# Challenge 1:
# Write a Python script that:

# Takes a number as input.
# Determines if it’s an integer or float.
# If it's an integer, calculate its square root and factorial.
# If it's a float, convert it to hexadecimal and round it to 2 decimal places.
# If it's a complex number, return its conjugate and real part.

# Solution:
num = input("Enter a number: ")
print(num)
if type(num) == int:
    print(f"Square root: {math.sqrt(num)}")
    print(f"Factorial: {math.factorial(num)}")
elif type(num) == float:
    print(f"Hexadecimal: {float.hex(num)}")
    hex_num = float.hex(num)
    print(f"Rounded: {round(float.fromhex(hex_num), 2)}")
elif type(num) == complex:
    print(f"Conjugate: {num.conjugate()}")
    print(f"Real part: {num.real}")
else:
    print(f"Invalid number:{type(num)}")
```

    10.22
    Invalid number:<class 'str'>
    
