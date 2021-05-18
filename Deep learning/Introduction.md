### Introduction to Deep Learning
* AI is the new electricity, where one of the fields of AI is rising rapidly is deep learning.
***

## Course consists of 5 courses as sequence they are:
    1. Neural networks and Deep learning
    2. Improving Deep Neural network: Hyper parameter tuning, Regualarization, and optimization
    3. Structuring your machine learning project
    4. Convolutional Neural Networks (CNN)
    5. Sequence models (RNN, LSTM)

***
* In neural network where input data goes through hidden layer (function) and outputs the output, the common function is Relu (rectified linear unit).

* Relu - it is an activation function in neural networks, where it takes value and outputs max value from 0,z where if z is negative output is zero. (or) The rectified linear activation function or ReLU for short is a piecewise linear function that will output the input directly if it is positive,otherwise, it will output zero. [ReLU link @machinelearningmastery](https://machinelearningmastery.com/rectified-linear-activation-function-for-deep-learning-neural-networks/ "ReLU link")

* A neural network have a Input layer (where it takes inputs), hidden layer (where it does all the ocmputaitons and store weights) and output layer where the output is displayed. most of the neural network is used to solve supervised learning.

* Human's are great at understanding and recognizing the unstructured data, where on other hand neural networks are better at understanding unstructured data (such as images, music files, text data, etc.,)

* To get higher perfromance out of neural neural network we need to create larger neural network with more amount of layers and require very large amount of data andrew ng explains this in video called why deep learning is takin off, he also explains that using the smaller dataset it really odesnt matter if we use machine learning algorithms like SVM, Decision Tress, etc or any neural network it will overall yield similar results (limitation is smaller set of data). please find the belo graph whihc explains you clearly!

<br><br>
<img src="https://miro.medium.com/max/802/1*1ADLHcqXhmtgDBkMF7b2Hw.png" alt="Scale drives deep learning" />
<br><br>

<span style="color: red; font-size: 18px"><b>NOTE: Please study where the algorithm or logic will fail!!</b></span>

### Basics of Neural Network
* we have taken an example of Logistic regression (it is a binary classifier, please read more on [Logistic regression Link](https://machinelearningmastery.com/logistic-regression-for-machine-learning/ "Logistic regression")), where we are trying to develop a simple classifier where it will predict 1 if the given image contains cat else 0, even we will learn how to represent the data for training in deep learning (in general we will iter one training value at a time and we loop over whole dataset) but in deep learning its traditional practive that we will try to combine all training data to one and pass the whole data at once. for example consider the of cat image of width 64px and heigh 64px since we have three channels (RGB) we represent image in 64 X 64 X 3 (matrix), now for training purpose we try to stack them one over the other and we form 1 column with 12288 rows. consider there are m number of images so we create m number of columns and combine as one dataset the dimensions look lik (12288 X m) matrix and target data is of shape (1 X m). NOTE: in machine learning we used to take transpose of the above mentioned logic where the data will of shape (m X 12288), but in deep learning this approach is not easy to implement, so we adopt representing an image's pixels as 1 single column.
<br> 
* Logistic Regression is used in binary classification, it is simply the linear regression where apply sigmoid function to linear regression since in logistic regression we are calculating the probability of the y being 1 given x (where y is a target variable and x is a input feature). NOTE: resulted value of sigmoid function lie between 0 and 1. Please refer link for sigmoid function [Sigmoid function](https://machinelearningmastery.com/choose-an-activation-function-for-deep-learning/#:~:text=The%20sigmoid%20activation%20function%20is,the%20range%200%20to%201. "Sigmoid Function")
<br><br>
* ### what is a cost function or loss function?
* In mathematical optimization and decision theory, a loss function or cost function is nothing but when we map an event with algorithm current state we get a result which is actually comapred with the real world value which results in some loss or cost asscoaiated for the change in value with real world value. this is known as cost or loss function. 
* <b>NOTE:</b> The terms cost and loss functions almost refer to the same meaning. ... The cost function is calculated as an average of loss functions. The loss function is a value which is calculated at every instance. So, for a single training cycle loss is calculated numerous times, but the cost function is only calculated once.
<br><br>

***

* ### Derivatives from calculus:  
* Let us understand how the derivatives work later we will see how the gradient descent algorithm is implemented. condiser a function f(a) is 3a, here if we want to find the slope (we usually do it by dividing height with width) or derivative with respect to 'a'. before that let us talk about slope first, let us assume that a=2 which gives f = 6, now we want to increase the by 0.5 i.e., a=2.5 now f= 7.5, when we plot this on graph we get to form a triangle between 6 and 7.5 where we slope by dividing height with width i.e., 3. this slope is common across all the values of a irrespective of smaller increase or decrease, this slope of line f(a) is known as derivative of f wrt a. NOTE: Derivatives means slope of line. in case of functions which involves square, cubic notations the slope is also fixed for eg f(x) = x^2 then the slope or derivative is 2x.
<br><br>
***

* ### Gradient Descent: 
* Gradient descent is a first-order iterative optimization algorithm for finding a local minimum of a differentiable function. We hope to minimize the cost function, where we expect the minimal value would be global minima of the function we are trying to build.
* In Gradient Descent Alpha is the learning rate, where alpha helps us to control how big the step we take while conquering to reach global minima or while updating the parameters. If learning rate is too small it will fail to converge, if alpha is too large the gradient descent will overshoot and diverge from the global minima.
* In gradient descent when we are trying to compute the cost function we are looking at all the training examples, which is some times called as "Batch Gradient Descent"
* if the gradient descent looks at smaller number of training examples from total examples called as "Mini Batch Gradient Descent".
* Please read about Stochastic gradient descent.



