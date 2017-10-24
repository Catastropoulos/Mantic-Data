# Mantic-Data

prediction.py permet de prédire le parti politique du maire d'une commune francaise. 

Le code comporte trois parties essentielles:

Première partie: scraping des données nécessaires au training
Le scraping se fait sur les pages wikipédia des maires des grandes villes francaises.
Le nombre de maires dont le code extrait les données est: 98
Les données sont présentées dans un premier temps en un array "data" qui comporte le nom de la commune, nom et prénom du maire, parti politique et lien wikipedia de la page du maire.
"Data" est utilisée pour construire le training set qui comporte les 98 maires, leurs partis politiques et les inputs choisis pour prédire ces partis.
Les inputs que j'ai choisi sont des occurences de mots qui se rapporte au contexte politique comme gauche, droite, radical, social,etc ou se rapporte au contexte geographique comme maurice, guyane,...

Deuxième partie: quatre méthodes de classification supervisé
Il existe plusieurs méthodes de classification supervisé. Ce code utilise: logical regression, MLP Classification, RandomForestClassifier et DecisionTreeClassifier.
Il suffit d'exécuter la partie du code concernée pour obtenir l'accuracy pour la validation et pour le test.
La plupart des accuracy sont entre 0.7 et 0.85.
Notons cependant que cette accuracy varie fortement suivant le set choisi pour faire le test. Vous pouvez choisir de fixer le test set en ajoutant un random_state à la ligne 134. Sinon à chaque execution vous aurez un test set et un training différents.

Troisième partie: une méthode ensembliste
Pour les méthodes précedentes, certains parties sont prédits mieux pour une methode qu'une autre. Les méthodes ensemblistes permettent de combiner ces méthodes pour avoir la meilleur prédiction possible parmi ceux donnés par ces méthodes.
Ce code utlise Voting Classifier qui permet de réaliser ceux-là. Vous pouvez executer plusieurs fois cette partie du code sur des test sets différents. L'accuracy est généralement compris entre 0.8 et 0.95. Vous obtiendrez en plus de l'accuracy, la liste des partis prédis avec la probabilité associée à cette prédiction.

