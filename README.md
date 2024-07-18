# TrabalhoBraida
## Guia para o model based: 
###Attributes

avaliacoes_treino:
Type: List
Description: Stores the training evaluations as a list of Avaliacao objects.
Purpose: To hold the training dataset in a specific format required for the SVD computations.
----------------------------------------------------------------------------
avaliacoes_teste:
Type: List
Description: Stores the test evaluations as a list of Avaliacao objects.
Purpose: To hold the test dataset for evaluation purposes after training.
----------------------------------------------------------------------------
num_usuarios:
Type: Integer
Description: The number of unique users in the dataset.
Purpose: To define the dimensions of the user feature matrix U.
----------------------------------------------------------------------------
num_filmes:
Type: Integer
Description: The number of unique items (movies) in the dataset.
Purpose: To define the dimensions of the item feature matrix V.
----------------------------------------------------------------------------
U:
Type: List of lists (2D List)
Description: The user feature matrix, initialized with values.
Purpose: To represent the latent features of users. Each row corresponds to a user, and each column corresponds to a latent feature.
----------------------------------------------------------------------------
V:
Type: List of lists (2D List)
Description: The item feature matrix, initialized with values.
Purpose: To represent the latent features of items. Each row corresponds to an item, and each column corresponds to a latent feature.
----------------------------------------------------------------------------
rank:
Type: Integer
Description: The number of latent factors or features.
Purpose: To determine the dimensionality of the latent feature space for both users and items.
----------------------------------------------------------------------------
taxa_aprendizado:
Type: Float
Description: The learning rate for the gradient descent optimization.
Purpose: To control the step size during the optimization process, affecting the speed and convergence of training.
----------------------------------------------------------------------------
regularizador(lambda):
Type: Float
Description: The regularization parameter for preventing overfitting.
Purpose: To penalize large weights in the feature matrices, encouraging simpler models.
----------------------------------------------------------------------------
minimo_melhoria:
Type: Float
Description: The minimum improvement in training error required to continue training.
Purpose: To determine the stopping criterion for training based on improvement in RMSE.
----------------------------------------------------------------------------
max_epocas:
Type: Integer
Description: The maximum number of epochs (iterations) for training.
Purpose: To limit the number of iterations in the training process, providing a stopping criterion.
----------------------------------------------------------------------------
### Methods (Partially shown in the code)
produto_escalar(self, v1, v2):
Computes the dot product of two vectors.
----------------------------------------------------------------------------
calcular_avaliacao(self, usuario, filme):
Predicts the rating for a given user and item pair based on the latent features.
----------------------------------------------------------------------------
treinar_avaliacoes(self):
Trains the SVD model using the training dataset.
----------------------------------------------------------------------------
calcular_rmse(self, avaliacoes):
Calculates the Root Mean Square Error (RMSE) for a set of evaluations.
----------------------------------------------------------------------------
calcular_mae(self, avaliacoes):
Calculates the Mean Absolute Error (MAE) for a set of evaluations.
----------------------------------------------------------------------------
ler_avaliacoes(self, nome_arquivo, avaliacoes, delimitador="\t"):
Reads evaluations from a file and appends them to the provided list.
----------------------------------------------------------------------------
ler_treino_pequeno(self, dados_treino):
Loads the training data from a small dataset.
----------------------------------------------------------------------------
ler_teste(self, dados_teste):
Loads the test data.
