# neural-network-charity-analysis

# Overview
The purpose of this project is to develop a machine learning model for the investment company Alphabet Soup, to predict the likelihood of their applicants' success. The model is a neural network that uses the Tensorflow Keras library. An ideal target performance for the model would be an accuracy score of at least 0.9.

The initial code and training attempt #0 can be found in this file linked here. [[Link to "AlphabetSoupCharity.ipynb"]](AlphabetSoupCharity.ipynb)

The three subsequent training attempts can be found here. [[Link to "AlphabetSoupCharity_Optimization_Attempts.ipynb"]](AlphabetSoupCharity_Optimization_Attempts.ipynb)

# Results
### Data Preprocessing

- Target variable for this model:
	- Is Successful (describes which applications in the past were successful)

- Features variables for this model:
	- Application Type
	- Affiliation
	- Classification
	- Use Case
	- Organization
	- Status
	- Income Amount
	- Special Considerations
	- Ask Amount

- Extra variables that were removed from the input data:
	- Ein
	- Name

*Non-numerical feature variables were encoded into numerical datatypes using OneHotEncoder*

### Compiling, Training, and Evaluating the Model

**Attempt 0**

This attempt was made with the given default settings. A callback was also created that saved the model's weights every 5 seconds.

Neural Network:

|      Layer     | Number of Nodes | Activation Function |
|:--------------:|:---------------:|:-------------------:|
| Hidden Layer 1 |        80       |         ReLu        |
| Hidden Layer 2 |        30       |         ReLu        |
|  Output Layer  |        1        |       Sigmoid       |

- Loss: 0.5649
- Accuracy: 0.7293

**Optimization Attempt 1**

The first attempt to optimize the model added additional nodes and layers to the neural network. The number of nodes were decided based on the powers of 2, for fun. The Special Considerations variable was also dropped to reduce noise in the input data. The new network is as shown in the table below.

Neural Network:

|      Layer     | Number of Nodes | Activation Function |
|:--------------:|:---------------:|:-------------------:|
| Hidden Layer 1 |       128       |         ReLu        |
| Hidden Layer 2 |        64       |         ReLu        |
| Hidden Layer 3 |        32       |         ReLu        |
|  Output Layer  |        1        |       Sigmoid       |

- Loss: 0.5797
- Accuracy: 0.7317

The model performed marginally better, but such a small increase is fairly insignificant.

**Optimization Attempt 2**

The second attempt to optimize the model changed the activation functions in the hidden layers from ReLu to Sigmoid to see if a different activation function would work better.

Neural Network:

|      Layer     | Number of Nodes | Activation Function |
|:--------------:|:---------------:|:-------------------:|
| Hidden Layer 1 |       128       |       Sigmoid       |
| Hidden Layer 2 |        64       |       Sigmoid       |
| Hidden Layer 3 |        32       |       Sigmoid       |
|  Output Layer  |        1        |       Sigmoid       |

- Loss: 0.5657
- Accuracy: 0.7284

The model performed slightly worse. It appears that the Sigmoid function was not a better fit for this data.

**Optimization Attempt 3**

The third attempt to optimize the model added a fourth hidden layer with 16 nodes. The activation functions of the hidden layers were also switched back to ReLu since the Sigmoid functions did not appear to help.

Neural Network:

|      Layer     | Number of Nodes | Activation Function |
|:--------------:|:---------------:|:-------------------:|
| Hidden Layer 1 |       128       |         ReLu        |
| Hidden Layer 2 |        64       |         ReLu        |
| Hidden Layer 3 |        32       |         ReLu        |
| Hidden Layer 4 |        16       |         ReLu        |
|  Output Layer  |        1        |       Sigmoid       |

- Loss: 0.5934
- Accuracy: 0.7276

Unfortunately the model performed even worse, which indicates that adding more neurons and layers may have overfit the model. Sadly the target performance of above 0.9 accuracy was not achieved.

# Summary
Overall, the deep learning model didn't perform poorly, but it was still less accurate that what would have been preferred. Adjusting the number of hidden layers, nodes, and activation functions in the neural network appeared to have little effect on the model's performance, and the model's accuracy remained steadily around 0.72 - 0.73.

It is recommended to try using a different model besides a neural network to fit this dataset. Since the target variable for the outcome is binary, a logarithmic regression model could be tested. Logarithmic regression models are also easier to interpret when analyzing which input variables more strongly influence the model, so it may be possible to gain additional insights into which applicants are more likely to spend their budgets successfully.
