## Unsupervised learning
K-means and his close-friends 
## Méthode
* Utiliser PCA pour réduire la dimensionnalité des données tout en préservant le maximum d'informations.
* K-means \
  * Principe : K-means partitionne les données en k clusters en minimisant la variance intra-cluster.
  * Paramètres : Nombre de clusters k à définir à l'avance.
  * Avantages :
     * Simple et rapide.
     * +Efficace pour des clusters sphériques et de taille similaire.
  * Inconvénients :
     * Sensible aux valeurs aberrantes.
     * Nécessite de connaître k à l'avance.
     * Ne fonctionne pas bien avec des clusters de formes variées.
* DBSCAN (Density-Based Spatial Clustering of Applications with Noise)
  * Principe : DBSCAN identifie des clusters basés sur la densité des points, en marquant les points isolés comme du bruit.
  * Paramètres : Distance maximale \epsilon et nombre minimum de points *MinPts*
  * Avantages :
     * Identifie des clusters de formes variées.
     * Gère bien les valeurs aberrantes.
     * Ne nécessite pas de connaître le nombre de clusters à l'avance.
  * Inconvénients :
     * Sensible au choix des paramètres \epsilon et *MinPts*
     *  Moins efficace pour des données de haute dimension.
