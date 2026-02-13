Détection d'Activités Maritimes par Analyse de Flux AIS

Ce projet vise à caractériser les activités des navires à partir de données AIS. Il démontre une capacité à traiter des signaux spatio-temporels complexes pour isoler des comportements métiers spécifiques (ex: sondage vs transit).

🚀 Fonctionnalités Clés

Simulation Dynamique : Génération de trajectoires GPS réalistes (Lat/Lon) basées sur la physique du mouvement naval.

Carte Interactive (Folium) : Génération d'un fichier trajectoire_ais.html permettant de visualiser les parcours sur un fond de carte réel (OpenStreetMap).

Bleu : Transit (vitesse élevée, cap stable).

Rouge : Sondage (vitesse faible, trajectoire sinueuse).

Feature Engineering Temporel : Utilisation de fenêtres glissantes pour capturer la signature statistique de chaque activité.

📈 Analyse de Performance

Le modèle de classification (Random Forest) a été évalué sur un jeu de test de 30% des données simulées.

Métriques Clés

Précision (Accuracy) : ~99% sur les données simulées.

F1-Score (Sondage) : 1.00 (Le modèle distingue parfaitement les phases de travail grâce à la variabilité du cap).

Importance des Variables : La variable SOG (vitesse) et COG_std_5m (stabilité du cap) sont les deux leviers de décision principaux.

Interprétation de la Matrice de Confusion

La matrice montre une séparation quasi-parfaite des classes. En contexte réel, la performance pourrait légèrement baisser face à des conditions météorologiques (dérive due au courant), mais l'utilisation de l'écart-type glissant du cap (COG_std_5m) reste le descripteur le plus robuste face au bruit.

🛠️ Installation et Utilisation

pip install pandas numpy scikit-learn matplotlib seaborn folium


Ouvrez ensuite le fichier trajectoire_ais.html dans votre navigateur pour explorer la carte.

🎯 Impact pour Spinergie

Cette méthodologie permet d'enrichir automatiquement la base de connaissances du produit Market Intelligence en qualifiant les opérations navales sans intervention manuelle, optimisant ainsi le suivi de la flotte offshore en temps réel.


📊 Sources de Données Réelles

Pour tester ce projet sur des données réelles (ce qui est fortement recommandé pour votre candidature chez Spinergie), vous pouvez consulter les sources suivantes :

MarineCadastre.gov (États-Unis) : Fournit des archives massives de données AIS par zone et par année. C'est la référence pour les jeux de données d'entraînement.

Danish Maritime Authority (DMA) : Propose des données AIS historiques gratuites couvrant les eaux danoises et la Mer du Nord (zone clé pour l'éolien offshore).

EMODnet (Europe) : Le portail européen de données maritimes propose des couches de densité de trafic et des extraits de données AIS.

Global Fishing Watch : Bien que focalisé sur la pêche, ils mettent à disposition des datasets publics sur les mouvements de navires et les activités de transbordement.

Kaggle : Recherchez "AIS Data" pour trouver des extraits pré-nettoyés par la communauté.

🎯 Objectif Métier 

Ce projet démontre une capacité à traiter des flux de données en temps réel et à transformer des coordonnées géographiques en indicateurs de marché actionnables pour les armateurs et les développeurs de parcs éoliens.