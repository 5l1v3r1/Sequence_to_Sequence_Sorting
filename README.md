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
I changed the model architecture a bit, making it like the one used in [2].  

Below are some screenshots of the training. The first image shows the results after only a few hundred epochs.
![alt text](./images/01.png?raw=true "Output")  

After more training, we begin to see some correct predictions.  
![alt text](./images/02.png?raw=true "Output")  

Finally, after most predictions are correct, I test the accuracy with 1,000 test trials.  
![alt text](./images/03.png?raw=true "Output")  


#### Sequence Lengths and Test Accuracy  
| Sequence Length  | Training Epochs  | Test Accuracy  |
| -------------    |:-------------:   | ---------:     |
| 10 chars         | 4.3x10<sup>4</sup> | 98.40 % |
| 15 chars         | 1.0x10<sup>5</sup> | 98.40 % |
| 20 chars         | 1.2x10<sup>5</sup> | 98.20 % |

The Training Epochs values above do not necessarily reflect the minimum training iterations required to achieve the given Test Accuracies. For the length-10 sequence, for example, I trained the model for 40,000 epochs, saw that I was close to my goal of  98% accuracy, and continued training by 1,000 epochs until the desired accuracy was reached.  