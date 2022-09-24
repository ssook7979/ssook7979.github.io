# Complex Class

uses `floats` for properties

## properties

- real
- imag

## methods

- conjugate

# Operation

## supported

- `==` and `!=`
- `cmath` module

## unsupported

- comparison operators(`<,>,≤,≥`)
- `math` module

# Applications

## Rect to Polar

```python
import cmath
cmath.phase(x)
abs(x)
```

## Polar to Rect

```python
import cmath

cmath.rect(math.sqrt(2), math.pi/4)
-> 1 + 1j
```

## Euler’s identity