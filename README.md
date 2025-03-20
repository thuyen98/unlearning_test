# Apprentissage non supervisé
## Méthode
* Utiliser **PCA** pour réduire la dimensionnalité des données tout en préservant le maximum d'informations.
* **K-means** 
  * Principe : K-means partitionne les données en k clusters en minimisant la variance intra-cluster.
  * Paramètres : Nombre de clusters k à définir à l'avance.
  * Avantages :
     * Simple et rapide.
     * Efficace pour des clusters sphériques et de taille similaire.
  * Inconvénients :
     * Sensible aux valeurs aberrantes.
     * Nécessite de connaître k à l'avance.
     * Ne fonctionne pas bien avec des clusters de formes variées.
* **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise)
  * Principe : DBSCAN identifie des clusters basés sur la densité des points, en marquant les points isolés comme du bruit.
  * Paramètres : Distance maximale $$\epsilon$$ et nombre minimum de points *MinPts*
  * Avantages :
     * Identifie des clusters de formes variées.
     * Gère bien les valeurs aberrantes.
     * Ne nécessite pas de connaître le nombre de clusters à l'avance.
  * Inconvénients :
     * Sensible au choix des paramètres $$\epsilon$$ et *MinPts*
     * Moins efficace pour des données de haute dimension.
* **Optimisation des Paramètres**:
   * **Méthode du Coude** (**Elbow Method**): est une technique heuristique utilisée pour déterminer le nombre de clusters dans un ensemble de données.
       1. Calcul du WCSS: On applique l'algorithme de clustering k-means pour différents nombres de clusters (k) et on calcule la somme des carrés des distances (WCSS) entre chaque point et le centre de son cluster.
       2. Tracé du graphique: On trace le WCSS en fonction du nombre de clusters.
       3. Détection du coude: Le nombre optimal de clusters est déterminé par l'endroit où la courbe forme un coude, indiquant que l'ajout de clusters supplémentaires n'améliore pas significativement la somme des carrés des distances
  => Simple à comprendre et à appliquer, mais peut être subjective dans la détection du coude.
   * **Indice de Silhouette**:  mesure la qualité de la séparation des clusters.
       1. Calcul de la silhouette: Pour chaque point, on calcule la distance moyenne entre ce point et les autres points de son cluster (a) et la distance moyenne entre ce point et les points du cluster le plus proche (b).
       2. Formule de la silhouette: L'indice de silhouette pour chaque point est donné par $$s = \frac{b - a}{\max(a, b)}$$
       3. Interprétation: La valeur de l'indice de silhouette varie de -1 à 1. Une valeur proche de 1 indique que les points sont bien regroupés dans leurs clusters respectifs, tandis qu'une valeur proche de -1 indique que les points sont mal regroupés.
   => Fournit une mesure quantitative de la qualité du clustering, mais peut être plus complexe à calculer et interpréter.

* **Autres Approches de Clustering**
  * **Agglomerative Clustering (Clustering Hiérarchique**): est une méthode de clustering qui construit une hiérarchie de clusters
     1. Approche Bottom-Up: Chaque observation commence dans son propre cluster, et les clusters sont fusionnés progressivement.
     2. Dendrogramme: Les résultats sont souvent présentés sous forme de dendrogramme, qui montre les relations hiérarchiques entre les clusters.
     3. Critères de Liaison: Différents critères de liaison peuvent être utilisés pour déterminer la distance entre les clusters, comme la liaison simple, complète ou moyenne (linkage).
  * **Gaussian Mixture Model (GMM)**: st une méthode probabiliste pour le clustering
     1. Distribution Probabiliste: Le GMM représente les données comme une somme pondérée de distributions gaussiennes.
     2. Classification Souple: Contrairement au k-means qui effectue une classification dure, le GMM permet une classification souple où chaque point peut appartenir à plusieurs clusters avec différentes probabilités.
     3. Algorithme EM: Les paramètres du GMM sont estimés à l'aide de l'algorithme Expectation-Maximization (EM), qui optimise les paramètres pour maximiser la probabilité des données.

    
