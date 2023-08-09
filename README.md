# Simple MNIST Neural Network Using Numpy

I implemented a simple two-layer neural network and trained it on the MNIST digit recognizer dataset. It's meant to be an instructional example, through which you can understand the underlying math of neural networks better.

Our NN will have a simple two-layer architecture. Input layer a<sup>[0]</sup> will have 784 units corresponding to the 784 pixels in each 28x28 input image. A hidden layer a<sup>[1]</sup> will have 10 units with ReLU activation, and finally our output layer a<sup>[2]</sup> will have 10 units corresponding to the ten digit classes with SoftMax activation.

**Forward propagation**

Z<sup>[1]</sup>=W<sup>[1]</sup>X + b<sup>[1]</sup>

A[1]=g<sub>ReLU</sub>(Z<sup>[1]</sup>))

Z[2]=W<sup>[2]</sup>A<sup>[1]</sup>+b<sup>[2]</sup>

A[2]=g<sub>softmax</sub>(Z<sup>[2]</sup>)

**Backward propagation**

dZ<sup>[2]</sup>=A<sup>[2]</sup>−Y

dW<sup>[2]</sup>=1/m \* dZ<sup>[2]</sup>A<sup>[1]T</sup>

dB<sup>[2]</sup>=1/m \* ΣdZ<sup>[2]</sup>

dZ<sup>[1]</sup>=W<sup>[2]T</sup>dZ<sup>[2]</sup>.∗g<sup>[1]’</sup>z<sup>[1]</sup>

dW<sup>[1]</sup>=1/m \* dZ<sup>[1]</sup>A<sup>[0]T</sup>

dB<sup>[1]</sup>=1/m \* ΣdZ<sup>[1]</sup> 1]

**Parameter updates**

W<sup>[2]</sup>:=W<sup>[2]</sup>−αdW<sup>[2]</sup>

b<sup>[2]</sup>:=b<sup>[2]</sup>−αdb<sup>[2]</sup>

W<sup>[1]</sup>:=W<sup>[1]</sup>−αdW<sup>[1]</sup>

b<sup>[1]</sup>:=b<sup>[1]</sup>−αdb<sup>[1]</sup>

**Vars and shapes**

Forward prop

- A<sup>[0]</sup>=X: <sub>784 x m</sub>
- Z<sup>[1]</sup> ∼ A<sup>[1]</sup>: <sub>10 x m</sub>
- W<sup>[1]</sup>: <sub>10 x 784</sub> (as W<sup>[1]</sup>A<sup>[0]</sup>∼Z<sup>[1]</sup>)
- B<sup>[1]</sup>: <sub>10 x 1</sub>
- Z<sup>[2]</sup>∼A<sup>[2]</sup>: <sub>10 x m</sub>
- W<sup>[1]</sup>: <sub>10 x 10</sub> (as W<sup>[2]</sup>A<sup>[1]</sup>∼Z<sup>[2]</sup>)
- B<sup>[2]</sup>: <sub>10 x 1</sub>

Backprop

- dZ<sup>[2]</sup>: <sub>10 x m</sub> ( A[2])
- dW<sup>[2]</sup>: <sub>10 x 10</sub>
- dB<sup>[2]</sup>: <sub>10 x 1</sub>
- dZ<sup>[1]</sup>: <sub>10 x m</sub> ( A<sup>[1]</sup>)
- dW<sup>[1]</sup>: <sub>10 x 10</sub>
- dB<sup>[1]</sup>: <sub>10 x 1</sub>

**Accuracy**:92.11%(for 500 epochs)

test\_prediction(9, W1, b1, W2, b2)

Prediction:  [5]

Label:  5
![image](https://github.com/PGuruAravindh/Digit_Recognizer/assets/122717548/2a1caff3-b4ff-4e81-86f9-9b7d08cf7f1f)

