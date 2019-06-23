## Deep Neural Network for identifying the best quotation out of all the quotations submitted for a software project

### Bid selection process
Choosing among competitive bids is a challenging process. It can often involve a committee representing a variety of disciplines and agendas. A fair and impartial analysis that results in a consensus decision is the goal, but competing priorities and hidden biases often frustrates it. One way to achieve the desired results is to use a methodology based on selection criteria that are agreed to prior to receiving the first bid.

### Idea to build a deep neural network for identifying the probability of a bid being good or bad
In this effort we are trying to use deep learning techniques to select the best bid out of all the bids that are submitted for software projects.

As part of this effort we have generated huge number of examples of the bids and also defined a criterion to say whether a particular bid is a good bid or a bad bid. Once we generated such examples, we used deep learning techniques to train and build a model that learns from all these examples. We built 4 such models (with different values for hyperparameters) and evaluated them against new example bids to find out the accuracy of these 4 models.

### Defining features
##### SNO Feature Name
  1.  Company Name
  2.  Company Rating on 5 scale
  3.  Duration specified by owner
  4.  Duration specified by the bidder
  5.  Proposed cost
  6.  Number of projects completed
  7.  Relevance of the project in fraction
  8.  Success rate of past projects in fraction
  9.  No.of projects completed for this owner
  10. Plan of execution submitted
  11. Quality of plan of execution (categorical: Excellent, Good, Average)
  12. Skilled resources availability
  13. Equipment availability

### Defining label of dataset
Probability of completion

### The sequence of steps that we have followed for implementing this project
#### Note: We followed the supervised learning workflow for implementing this project
1. Generate the dataset
2. Preprocess the dataset
3. Splitting the dataset into train and test datasets
4. Define the architecture of the neural network
5. Build and train the model
6. Evaluate the model accuracy

### Architecure of the model
1. The model has ten layers
    1. One input layer
    2. Eight hidden layers and
    3. One output layer
2. In each layer we have different number of nodes (neurons)
3. In the last layer we only have 2 nodes (neurons)
4. In each of the hidden layers,
    1. RELU activation function is used
    2. DROPOUT regularization is applied
5. In the output layer,
    1. SOFTMAX activation function is used, as we want to predict the probability of the 2 classes, that is probability of 'Good Bid' and  probability of 'Bad Bid'

### Hyperparameters of the model
1. Number of epochs: 10
2. Batch size: 5000
