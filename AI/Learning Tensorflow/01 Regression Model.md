# First regression model

```python
import tensorflow as tf

X = tf.constant([-7.0, -4.0, -1.0, 3, 7, 11, 15])
y = tf.constant([3, 6, 9, 13, 17, 21, 25])

model = tf.keras.Sequential([
    tf.keras.layers.Input(shape=1),
    tf.keras.layers.Dense(1)
])

model.compile(loss=tf.keras.losses.mae, optimizer=tf.keras.optimizers.SGD())

model.fit(X, y, epochs=100)

value = model.predict([39.0])
print(value)
```
