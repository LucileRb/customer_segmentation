# customer_segmentation

Olist -> e-commerce
Segmentation clients pour campagnes de com
comprendre les différents types d'utilisateurs grace à :
- comportement
- données perso

fournir une description actionable de la segmentation + analyse de la stabilité des segments au cours du tps

but

1) segmentation
différencier les bons et moins bons clients en termes de commandes et de satisfaction
segmentation sur l'ensemble des clients

2) recommandation de fréquence de maj de la segmentation


-> norme PEP8

RANDOM STATE -> 42

# données
historique de commandes, les produits achetés, les commentaires de satisfaction, et la
localisation des clients depuis janvier 2017

3% des clients du fichier ont réalisé plusieurs commandes

# méthode

méthodes non supervisées
regrouper clients de profils similaires

# fichier requireements
pip freeze > requirements.txt 

# Notebooks : 
1) Data exploration
Exploration de chaque dataset et nettoyage (duplicats, outliers...)

Merge

Data engineering - création de nouvelles features

Imputation des valeurs manquantes :
- variables qualitatives : remplacer les NaN par la modalité la plus fréquente
- variables quantitatives : imputation KNN

Analyse univariée

Analyse bivariée/multivariée

Export des données


2) Segmentation RFM

Sources : 
https://www.datacamp.com/tutorial/introduction-customer-segmentation-python
https://medium.com/@ugursavci/customer-segmentation-using-rfm-analysis-in-python-218a3255f714
https://guillaume-martin.github.io/rfm-segmentation-with-python.html

RFM stands for recency, frequency, and monetary value. A method used to segment customers based on when their
last purchase was(recency), how often they’ve purchased in the past (frequency), and how much they’ve spent
overall (monetary). The output can be used to increase customer retention, customer engagement and targeted
marketing.

R - date de la dernière commande (Récence) = number of days since last purchase
F - fréquence des commandes = number of purchases during the studied period
M - montant de la dernière commande ou sur une période donnée = total amount of purchases made during the studied period

but = établir des segments de clients homogènes
The purpose of RFM analysis is to form segments and, depending on the segment, influence them in a certain way.

3) Clustering - dataset total
4) Clustering - dataset RFM
5) Clustering - dataset réduit

### Encoding

encoding -> autre solution (pour catégories):
- encoding numérique
- encoding nlp (cf embedding)

3 façons d'encoder variables catégorielles :

- integer encoding -> OrdinalEncoder() ou LabelEncoder() ?
- one hot encoding -> OneHotEncoder()
- learned embedding

Ordinal encoding vs Label encoding

Ordinal encoding should be used for ordinal variables (where order matters, like cold, warm, hot)
Label encoding should be used for non-ordinal (aka nominal) variables (where order doesn't matter, like blonde, brunette)

ici ordre compte pour order_status mais pas pour payment type et product category
-> faire ordinal encoding pour order_status et label encoding pour les deux autres

### Scaling

https://forecastegy.com/posts/standardscaler-vs-minmaxscaler-difference/

scaling sur données numériques uniquement (exclure données encodées du scaling)
standardscaler

### Clustering

Modèles à tester :

- Kmeans
- Agglomerative clustering
- DBSCAN
- Spectral clustering

Evaluation du clustering

- forme des clusters (cf silhouette score)
- stabilité des clusters (ARI score)

Métriques d'évalutation :

- Silhouette score/coefficient
- Davies-Bouldin Index
- Calinski-Harabasz Index
- Adjusted Rand Index

ne choisir qu'une métrique et se baser dessus
si j'en prends trop, peuvent dire des choses différentes et ne va m'avancer à rien

### ARI score

https://amueller.github.io/aml/04-model-evaluation/17-cluster-evaluation.html
https://reval.readthedocs.io/en/latest/
https://github.com/FlorentF9/skstab




### presentation

https://www.slideshare.net/MichaelFUMERY1/segmentation-dun-fichier-client-machine-learning ### idées pour présentation


# A FAIRE

- renommer order time et shipping machin truc
-> delai de livraison, 