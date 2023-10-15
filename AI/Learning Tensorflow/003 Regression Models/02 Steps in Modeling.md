# Steps in Modeling

## Summary

1. Creating a model (Define the structure)
2. Compiling a model (Create the model)
3. Fitting a model (Train)
4. Evaluate

## Content

1. Creating a model

```python
model = tf.keras.Sequential([
    tf.keras.layers.Input(1),
    tf.keras.layers.Dense(1)
])
```

2. Compiling a model

```python
model.compile(
    loss=tf.keras.losses.mae,
    optimizer=tf.keras.optimizers.SGD(),
    metrics=[ tf.keras.losses.mae ]
)
```

3. Fitting a model

```python
model.fit(X, y, epochs=5)
```

4. Evaluate

```python
model.predict([7])
# array([[-6.81166]], dtype=float32)
# it's incorrect but it's fine
```
