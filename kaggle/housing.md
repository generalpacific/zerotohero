v0.1
* Dense512 -> Dense 256 -> Dense10
* Epochs 100, Batch size 32
```
Epoch 100/100
46/46 [==============================] - 0s 5ms/step - loss: 592467008.0000 - mae: 15243.6689

```

v0.2
* Dense512 -> Dense256 -> Dense10
* Epochs 100, Batch size 32
```
Epoch 100/100
46/46 [==============================] - 0s 9ms/step - loss: 601020480.0000 - mae: 15334.3037
```

v0.21
* Dense512 -> Dense256 -> Dense10
* Epochs 1000, Batch size 32
```
Epoch 100/100
46/46 [==============================] - 0s 9ms/step - loss: 601020480.0000 - mae: 15334.3037
```

v0.3
* Fixed major bug where Y was part of the input too. So fixed it.
* Dense512 -> Dense256 -> Dense10
* Epochs 1000, Batch size 32
```
Epoch 1000/1000
46/46 [==============================] - 0s 8ms/step - loss: 1.9412e-06 - mae: 0.0011
```

v0.3.1
* Output probably needs to be 1 value.
* Dense512 -> Dense256 -> Dense10 -> Dense1
* Epochs 1000, Batch size 32
```
46/46 [==============================] - 0s 7ms/step - loss: 1.7336e-04 - mae: 0.0100

```
* Score on kaggle: 11.98479

