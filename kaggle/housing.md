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

v0.3.2
* Dense1024 -> Dense512 -> Dense256 -> Dense1
* Epochs 100, Batch size 4
* changed metric to rmse
* reduced epochs since training is slow.
```
365/365 [==============================] - 6s 16ms/step - loss: 17447032.0000 - rmse: 4176.9644

```
* Score on kaggle: 2.68224


v0.3.3
* Dense1024 -> Dense512 -> Dense256 -> Dense1
* Epochs 100, Batch size 4
* added validation split
```
329/329 [==============================] - 6s 17ms/step - loss: 18926792.0000 - rmse: 4350.4932 - val_loss: 39332612.0000 - val_rmse: 6271.5718
```
* Score on kaggle: 11.32143

v0.3.4
* Dense2024 -> Dense1024 -> Dense 512 -> Dense256 -> Dense1
* Epochs 1000, Batch size 4
* REMOVED  validation split
```
Epoch 1000/1000
365/365 [==============================] - 21s 58ms/step - loss: 0.0063 - rmse: 0.0793

```
* Score on kaggle: 11.92316

v0.3.5
* Dense2024 -> Dense1024 -> Dense 512 -> Dense256 -> Dense1
* Epochs 100, Batch size 4
```
365/365 [==============================] - 23s 63ms/step - loss: 0.0100 - rmse: 0.0998

```
* Score on kaggle: 12.00103 

v0.3.6
* Dense2024 -> Dense1024 -> Dense 512 -> Dense256 -> Dense1
* Epochs 100, Batch size 4
* Use standardScalar in preprocessing.
```
365/365 [==============================] - 23s 64ms/step - loss: 0.0219 - rmse: 0.1480
```
* Score on kaggle:11:84059 
