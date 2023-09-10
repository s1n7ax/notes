# Creating Tensors

1. tf.constant()
   - Once created, cannot be changed
2. tf.Variable()
   - Can be mutated

## Constant function

Once created, the value cannot be changed

```python
tf.constant([1, 2, 3])
# <tf.Tensor: shape=(3,), dtype=int32, numpy=array([1, 2, 3], dtype=int32)>
```

## Variable function

After created, the values can be changed using `tf.assign` or other operations

NOTE: New value should also be in the same shape and `dtype`

```python
vector = tf.Variable([1, 2, 3])
# <tf.Variable 'Variable:0' shape=(3,) dtype=int32, numpy=array([1, 2, 3], dtype=int32)>

vector.assign([4, 5, 6])
vector
# <tf.Variable 'Variable:0' shape=(3,) dtype=int32, numpy=array([4, 5, 6], dtype=int32)>
```

# Tensor Types

Mainly, we will talk about following data types

- Scalar
- Vector
- Multi-Dimensional (Matrix)

## Scalar

- Creating a scalar

```python
tf.constant(7)
# <tf.Tensor: shape=(), dtype=int32, numpy=7>
```

## Vector

- Creating a vector

```python
tf.constant([1, 2, 3])
# <tf.Tensor: shape=(3,), dtype=int32, numpy=array([1, 2, 3], dtype=int32)>
```

## Matrix

- Creating a matrix

```python
tf.constant([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
])
''
<tf.Tensor: shape=(3, 3), dtype=int32, numpy=
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]], dtype=int32)>
''
```

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

# Tensor Data Types (dtype)

## Auto dtype

Type will be determined based on the value being passed

```python
tf.contant(7)
# <tf.Tensor: shape=(), dtype=int32, numpy=7>
```

```python
tf.constant(7.)
# <tf.Tensor: shape=(), dtype=float32, numpy=1.0>
```

## Specify the type

`dtype` keyword argument can be used to specify the type of the parameter

```python
tf.constant([1, 2, 3])
# <tf.Tensor: shape=(3,), dtype=int32, numpy=array([1, 2, 3], dtype=int32)>
```

```python
tf.constant([1, 2, 3], dtype=tf.float32)
# <tf.Tensor: shape=(3,), dtype=float32, numpy=array([1., 2., 3.], dtype=float32)>
```
