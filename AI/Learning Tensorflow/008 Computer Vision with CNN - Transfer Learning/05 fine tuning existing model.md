# Fine Tuning Existing Model

## Summary

- Steps of fine tuning
- Fine Tuning

## Content

### Steps of Fine Tuning

- Usually before we fine-tune the existing model, we train the output layer
  after freezing the existing model.
- After that, we can activate some layers of the backbone and start training
- Usually, with the part of backbone is activated, we lower the learning rate of
  the model to avoid drastic changes

### Fine Tuning

```python

```
