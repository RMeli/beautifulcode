# Python

## FizzBuzz with Infinite Iterables

```python
import itertools

fizzes = itertools.cycle(['', '', 'fizz'])
buzzes = itertools.cycle(['', '', '', '', 'buzz'])
numbers = itertools.count(1)

fizz_buzzes = ((fizz + buzz) or str(n) for fizz, buzz, n in zip(fizzes, buzzes, numbers))

output = [next(fizz_buzzes) for _ in range(100)]
```

From [Ten Essays on Fizz Buzz](https://leanpub.com/fizzbuzz/) by [Joel Grus](https://github.com/joelgrus).
