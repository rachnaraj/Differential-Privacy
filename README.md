# Differential-Privacy

Differential Privacy introduces noise or redundant data in the actual dataset to preserve users' confidential and private information. At the same time, the differential privacy technique also ensures adding noise so that the data is still statistically observable.
We are using IBM's differential privacy library, a lightweight and user-friendly tool for data analytics and machine learning. In our paper, we have picked up the Linear Regression model of IBM's DiffPrivLib library to compare the results.
The implementation goes as below:
regr_pri = LinearRegression(epsilon=epsilons[epsilon_idx], bounds_X=(0, 1), bounds_y=(0, 6257.0), random_state =1)

here,
epsilon is a privacy parameter which is of type float. The lower the value of epsilon, the better the Privacy, which means more noise is added to the data. Epsilon can take a deal from 0 to infinity.
Bound_x defines the minimum or maximum bound of a dataset. In our dataset, the minimum value is 0, and the maximum is 1 (due to using a min-max scaler).
Bound_y is similar to bound_x. We took the maximum value for the available columns in the dataset.
Random_state is chosen one or any value greater than 0 if we want to obtain the same result in any system.

We have implemented differential Privacy using varying epsilons ranging from 0.1 to 100. In our implementation, we compare the models (i.e., linear regression without Privacy using Python's sklearn library and LR with Privacy using NMAE (Normalised Mean Absolute Error) using IBM's diffPrivLib library). The graph shows that for the lower value of epsilon (epsilon- 2.3), the Normalised mean absolute error is higher than what we obtain in normal linear regression without Privacy. As with diff privacy, extra noise is added to the dataset to hide critical information.

One can download the dataset from https://drive.google.com/drive/folders/1engcykpGeXHyWK5gGLc6S5VTpZrs0HX_.
