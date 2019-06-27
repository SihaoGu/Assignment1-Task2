## Task2: Estimate the rating given a user/item pair

In this task, I use the latent factor model and the equation is ![first equation](http://latex.codecogs.com/gif.latex?%24%24rating%3D%5Calpha%20&plus;%20%5Cbeta_i%20&plus;%20%5Cbeta_u%20&plus;%20%5Cgamma_i%20%5Ccdot%20%5Cgamma_u%24%24).

First, I set the initial value of alpha, beta_u, beta_i, gamma_u, gamma_i. Alpha, beta_u and beta_i are 0. Gamma_u ad gamma_i are two matrix randomly initialized by dimension K.

Then I use above formula to update alpha, beta_u, beta_i, gamma_u and gamma_i. I set K, lambda and iteration times before writing this function to update these variables.

After receive this variables from the above function, I add these variables together according to the latent factor model equation to get the predict rating of different user-item pairs and calculate MSE. Through testing different lambda, K and iteration times, I choose values that have lower MSE on the validation dataset and use these values to estimate the rating in the test dataset.
