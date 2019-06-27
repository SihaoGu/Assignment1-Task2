## Task2: Estimate the rating given a user/item pair

In this task, I use the latent factor model and the equation is 

![first equation](http://latex.codecogs.com/gif.latex?%24%24rating%3D%5Calpha%20&plus;%20%5Cbeta_i%20&plus;%20%5Cbeta_u%20&plus;%20%5Cgamma_i%20%5Ccdot%20%5Cgamma_u%24%24).

First, I set the initial value of alpha, beta_u, beta_i, gamma_u, gamma_i. Alpha, beta_u and beta_i are 0. Gamma_u ad gamma_i are two matrix randomly initialized by dimension K.

![second equation](http://latex.codecogs.com/gif.latex?%5Cunderset%7B%5Calpha%20%2C%5Cbeta%20%2C%5Cgamma%20%7D%7B%5Coperatorname%7Bargmax%7D%7D%20%7B%5Csum_%7Bu%2Ci%7D%7D%5Cleft%20%28%5Calpha&plus;%5Cbeta_u&plus;%5Cbeta_i&plus;%5Cgamma_i%20%5Ccdot%20%5Cgamma_u-R_%7Bui%7D%5Cright%29%5E%7B2%7D%20&plus;%20%5Clambda%5Cleft%20%5B%5Csum_%7Bu%7D%5Cbeta_u%5E%7B2%7D&plus;%5Csum_%7Bi%7D%5Cbeta_i%5E%7B2%7D&plus;%5Csum_%7Bi%7D%5Cleft%20%5C%7C%20%5Cgamma_i%20%5Cright%20%5C%7C_%7B2%7D%5E%7B2%7D%20&plus;%5Csum_%7Bu%7D%5Cleft%20%5C%7C%20%5Cgamma_u%20%5Cright%20%5C%7C_%7B2%7D%5E%7B2%7D%5Cright%20%5D)

Then I use above formula to update alpha, beta_u, beta_i, gamma_u and gamma_i. I set K, lambda and iteration times before writing this function to update these variables.

After receive this variables from the above function, I add these variables together according to the latent factor model equation to get the predict rating of different user-item pairs and calculate MSE. Through testing different lambda, K and iteration times, I choose values that have lower MSE on the validation dataset and use these values to estimate the rating in the test dataset.
