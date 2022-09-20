# Introduction

## comparing with float

float 0.1

- infinite binary expansion

$$
\cfrac{1}{16} + \cfrac{1}{32} + \cfrac{1}{256} + \cfrac{1}{512} + \cfrac{1}{4096} + \cfrac{1}{8192} + \cdot\cdot\cdot
$$

- finite decimal expansion

$$
\cfrac{1}{10}
$$

## why use

- avoids the approximation issues
    - finite number of significant digits → rational number ❓
- why not just use the `Fraction` class?
    - complex, requires extra memory

<aside>
☑️ 1/10 + 2/5를 계산한다고 했을 때, 내부에서는 common denominator를 찾아서 1/10 + 4/10 과 같이 변경하여 계산하고 그 결과인 5/10을 1/2로 simplify 하여 저장한다.

</aside>

# Context

- controls certain aspects of working with decimals
- context is composed of
    - precision during arithmetic operations
        - how far does it maintain certain precision during operation
    - rounding alorithm
- scope
    - **global**(default context)
        - `decimal.getcontext()`
    - **local**(temporary)
        - sets temporary settings without affecting the global settings
        - `decimal.localcontext(ctx=None)`
            - creates a new context, copied from ctx or from default if ctx not specified
            - returns a **context manager**

## Precision and Rounding

- `ctx.prec`
    - get or set the precision(value is an int)
- `ctx.rounding`
    - get or set the rounding mechanism(value is a string)

<aside>
📎 from python 3.10 doc

`decimal.**ROUND_CEILING**`Round towards `Infinity`.

`decimal.**ROUND_DOWN**`[¶](https://docs.python.org/3/library/decimal.html#decimal.ROUND_DOWN)Round towards zero.

`decimal.**ROUND_FLOOR**`Round towards `-Infinity`.

`decimal.**ROUND_HALF_DOWN**`Round to nearest with ties going towards zero.

`decimal.**ROUND_HALF_EVEN**`Round to nearest with ties going to nearest even integer.

`decimal.**ROUND_HALF_UP**`Round to nearest with ties going away from zero.

`decimal.**ROUND_UP**`Round away from zero.

`decimal.**ROUND_05UP**`Round away from zero if last digit after rounding towards zero would have been 0 or 5; otherwise round towards zero.

</aside>

# Local context

```python
import decimal

with decimal.localcontext() as ctx:
	ctx.prec = 6
	ctx.rounding = decimal.ROUND_HALF_UP
	ctx.getcontext() # will return local context within with block
```

# Constructor

```jsx
from decimal import Decimal

Decimal('0.1')
Decimal(10)
Decimal((1, (3,1,4,1,5), -4)) # arg as tuple
Decimal(0.1) # floats can be used but not recommended
```

s: sign, d: digit, exp: exponent

Decimal((s, (d1, d2, d3,…), exp))

```jsx
decimal.getcontext().prec = 6
a = Decimal('0.12345')
b = Decimal('0.12345')
print(a+b) # 0.24690

with decimal.localcontext() as ctx:
	ctx.prec = 2
	c = a + b
	print(c) # 0.25

print(c) # 0.25 
# does not magically change precision 
# if the variable is outside the scope of 
# the local context
```

<aside>
📎 Context doesn’t affect the value stored in Decimal instance. Otherwise, arithmetic operation DOES have effects.

</aside>

```python
import decimal
from decimal import Decimal

a = Decimal('0.12345')
b = Decimal('0.12345')

decimal.getcontext().prec = 2

a,b
> Decimal('0.12345'), Decimal('0.12345')
a + b
> Decimal('0.25')

with decimal.localcontext() as ctx:
	ctx.prec = 2
	c = a + b
	> Decimal('0.25')
c
> Decimal('0.25') 
# global context doesn't affect the decimal value 
# as calculation is done within local context.
```

# Math Operation

This equation holds for both integers and decimals.

```python
n = d * (n // d) + (n % d)
```

but, separate operations may differ.

```python
10 // 3
> 3
Decimal(10) // Decimal(3)
> Decimal(3)

-10 // 3
> -4
Decimal(-10) // Decimal(3)
> Decimal(-3)
```

## why differ?

Division in Decimal is defined differently compared to Integer.

Agorithm

1. Figure out the sign of the result
2. use absolute values for divisor and divident
3. keep subtracting divisor from dividend while dividend > divisor
4. return the signed number of times this was perfored

## mathematical operations

- some operations like sqrt, logs, etc are defined in the Decimal class.
- also, the math module can be used
    - But, arguments will first be cast to **Floats**