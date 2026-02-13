# Projet-Cible-D-tection-d-activit-s-maritimes-AIS-
Détection d'Activités Maritimes par Analyse de Flux AIS

Ce projet vise à résoudre un défi majeur de l'intelligence de marché maritime : caractériser les activités des navires (sondage, maintenance, transit) à partir de données brutes AIS (Automatic Identification System).

L'enjeu est de distinguer des activités à forte variabilité (sondage des fonds marins) des phases de transit standard, en utilisant des techniques de Feature Engineering et de Machine Learning.

🚀 Fonctionnalités du Projet

Le pipeline implémenté dans le fichier projet_ais_spinergie.py effectue les étapes suivantes :

Simulation de données AIS réalistes : Création de datasets simulant le comportement de navires en route (vitesse élevée, cap stable) et en opération (vitesse faible, trajectoire complexe).

Feature Engineering Avancé :

Gestion du cap (COG) : Calcul de la variation de cap avec gestion du passage critique 359° -> 0°.

Indicateurs de stabilité : Calcul de l'écart-type glissant (Rolling Std) du cap et de la vitesse.

Efficiency Index : Création d'un ratio métier reliant vitesse et stabilité directionnelle.

Classification : Entraînement d'un modèle Random Forest pour identifier le type d'activité avec une précision élevée.

Analyse de l'importance des variables : Visualisation des paramètres les plus discriminants pour la décision du modèle.

🛠️ Installation et Utilisation

Prérequis

Python 3.8+

Bibliothèques : pandas, numpy, scikit-learn, matplotlib, seaborn

Lancement

python projet_ais_spinergie.py


📊 Sources de Données Réelles

Pour tester ce projet sur des données réelles (ce qui est fortement recommandé pour votre candidature chez Spinergie), vous pouvez consulter les sources suivantes :

MarineCadastre.gov (États-Unis) : Fournit des archives massives de données AIS par zone et par année. C'est la référence pour les jeux de données d'entraînement.

Danish Maritime Authority (DMA) : Propose des données AIS historiques gratuites couvrant les eaux danoises et la Mer du Nord (zone clé pour l'éolien offshore).

EMODnet (Europe) : Le portail européen de données maritimes propose des couches de densité de trafic et des extraits de données AIS.

Global Fishing Watch : Bien que focalisé sur la pêche, ils mettent à disposition des datasets publics sur les mouvements de navires et les activités de transbordement.

Kaggle : Recherchez "AIS Data" pour trouver des extraits pré-nettoyés par la communauté.

🎯 Objectif Métier 

Ce projet démontre une capacité à traiter des flux de données en temps réel et à transformer des coordonnées géographiques en indicateurs de marché actionnables pour les armateurs et les développeurs de parcs éoliens.