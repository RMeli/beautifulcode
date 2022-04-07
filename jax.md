# [JAX](https://jax.readthedocs.io/en/latest/)

```python
import jax
import jax.numpy as jnp
```

## Pairwise Distances

```python
# pairwise function
def distance(a, b):
    return jnp.linalg.norm(a - b)

# vmap-based combinator to operate on all pairs
def all_pairs(f):
    f = jax.vmap(f, in_axes=(None, 0))
    f = jax.vmap(f, in_axes=(0, None))
    return f

# transform to operate over sets
distances = all_pairs(distance)
```

[Showcased on Twitter](https://twitter.com/cgarciae88/status/1511763733676277766?s=20&t=ly0nolWLQaqCHrmKJ8ikbA) by [Cristian Garcia](https://twitter.com/cgarciae88).
