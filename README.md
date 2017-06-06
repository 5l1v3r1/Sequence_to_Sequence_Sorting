# **LSTM Sort with Keras + TensorFlow**
*A sequence to sequence learning implementation for sorting a list of numbers*

I spent much of a Sunday afternoon trying to figure out what architecture could be used to produce an artificial neural network to sort a list. I began with a reinforcement learning implementation, but soon abandoned it. Then I began learning about sequence to sequence networks, first through this blog entry, which describes just what I wanted to do:  
http://shashankg7.github.io/2016/07/22/learning-to-sort-using-seq2seq.html [1]  
Then I remembered having played with a sequence to sequence model in a Keras example:  
https://github.com/fchollet/keras/blob/master/examples/addition_rnn.py [2]  
Then, to get a better understanding of how RNNs / LSTMs work, I read:  
http://karpathy.github.io/2015/05/21/rnn-effectiveness [3]  
Then I read this:  
http://www.wildml.com/2015/09/recurrent-neural-networks-tutorial-part-1-introduction-to-rnns/ [4]  
Then this:  
http://colah.github.io/posts/2015-08-Understanding-LSTMs [5]  


In my code, I use the one-hot encoding and the batch-generating methods from reference [1]. At first I was creating a large training .npz file, but I much prefer generating the training and testing data on-the-fly with batch_gen().   
I changed the model architecture a bit, making like the one used in [2].  


work in progress...  
***sequence lengths and test accuracy...***