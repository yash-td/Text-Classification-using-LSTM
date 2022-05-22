# Text-Classification-using-LSTM
Building an LSTM model to classify movie reviews as either positive or negative

Radying the inputs for the LSTM:-

Performing pre-padding to our train data.
We prefer pre-padding over post-padding as post-padding seems to add noise to what has been learned from the sequence through time.
With pre-padding, however, the RNN is better able to adjust to the added noise of zeros at the beginning as it learns from the sequence through time.
Hence we use pre-padding where the meaningful information is stored in the later bits.

After creating 3 different models with different activation functions namely relu, softmax and sigmoid, the best accuracy was obtained with the model
that had the sigmoid activation function.

The optimal stopping point for this model is the point where the loss curve starts increasing. In the loss vs epochs graph, the loss curve keeps on decreasing
till the 4th epoch (loss is minimum at 4th epoch). Thereafter, in the 5th and the 6th epochs the loss starts increasing hence the optimal point for the model to stop is the 4th epoch
(denoted by 3 on the x axis) or the point marked in the graph above. This can also be validated by the value of loss from the model training part that is shown in the picture above.
Loss at epoch 4 is 0.2849 which is minimum.

The accuracy of the model seems to have increased by a small margin after adding the two dropout layers. (85→86%).
Moreover the optimal point of training is now the 3rd epoch instead of the 4th epoch that we observed in the previous model.

Experimenting the model with three different batch sizes on a subset of data (300), 
●	batch_size = 1 → execution_time = very large
The model fits perfectly +(high training accuracy in the first epoch but a lesser validation accuracy which means the validation loss is high)
●	batch_size = 32 → execution_time =  2min 41 secs
The model seems to perform decently with the batch size of 32. It has an accuracy of 73% with our subset of data.
●	batch_size = len(train_data)  → execution_time = 12s
When the model is trained on the batch size of len(train_data) the loss observed is similar to what is observed in batch size = 32. The accuracy is
72.67% whereas the execution time is significantly decreased.
