# Integer Overflow / Wraparound

## Description

> The product performs a calculation that can produce an integer overflow or wraparound when the logic assumes that the resulting value will always be larger than the original value. This occurs when an integer value is incremented to a value that is too large to store in the associated representation. When this occurs, the value may become a very small or negative number. <sup>[1]</sup>

## Other Names

- Overflow
- Wraparound
- wrap, wrap-around, wrap around

## References

1. [CWE-190: Integer Overflow or Wraparound](https://cwe.mitre.org/data/definitions/190.html)
