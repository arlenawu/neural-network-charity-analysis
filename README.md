# neural-network-charity-analysis

# Overview
The purpose of this project is to develop a machine learning model for the investment company Alphabet Soup, to predict the likelihood of their applicants' success. The model is a neural network that uses the Tensorflow Keras library.

# Results
**Data Preprocessing**

Target Variable for this model:

	- Is Successful (describes which applications in the past were successful)

Features variables for this model:

	- Application Type
	- Affiliation
	- Classification
	- Use Case
	- Organization
	- Status
	- Income Amount
	- Special Considerations
	- Ask Amount

* Non-numerical feature variables were encoded into numerical datatypes using OneHotEncoder

Extra variables that were removed from the input data:

	- Ein
	- Name

**Compiling, Training, and Evaluating the Model**

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
- Were you able to achieve the target model performance?
- What steps did you take to try and increase model performance?

- Attempt 0

	- This attempt was made with the given default settings.


- Optimization Attempt 1

Loss: 0.729362964630127, Accuracy: 0.45201167464256287

- Optimization Attempt 2

Loss: 0.6907975077629089, Accuracy: 0.5343440175056458

- Optimization Attempt 3

Loss: 0.5789344906806946, Accuracy: 0.7276967763900757


# Summary
