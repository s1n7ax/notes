# Dimensions

- Get the number of dimensions of a tensor

```python
scalar = tf.constant(7)
scalar.ndim
# 0
```

```python
vec = tf.constant([1, 2, 3])
vec.ndim
# 1
```

```python
matrix1 = tf.constant([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
])
matrix1.ndim
# 2

matrix2 = tf.constant([
    [[1, 2, 3]],
    [[4, 5, 6]],
    [[7, 8, 9]],
])
matrix2.ndim
# 3
```

