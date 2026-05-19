# 🔥 Analyse des Feux de Forêt aux États-Unis (1992–2015)

Projet Data complet utilisant **Python (Google Colab)** et **Power BI** pour analyser les feux de forêt aux USA entre 1992 et 2015.
---

## 🎯 Objectifs du projet

- Identifier les zones les plus touchées  
- Analyser les causes principales  
- Étudier l’évolution temporelle  
- Construire un dashboard interactif
- Apporter des préconisations afin de faire de la prévention dans les zones le plus touchées

## 📊 1. Analyse & Visualisations (Google Colab)

### Prétraitement des données

🔧Avant l’analyse, j’ai évalué la qualité du dataset.  
Le calcul des doublons par colonne montre que certaines variables contiennent plus de 1,8 million de valeurs répétées, ce qui indique :

- des colonnes peu informatives  
- des identifiants redondants  
- des champs administratifs inutiles pour l’analyse  

Cela m’a permis de sélectionner uniquement les colonnes pertinentes pour la suite du projet.

![Prétraitement](images/Preprocessing_doublons.png)

🔧Amélioration de la qualité du dataset en supprimant les colonnes qui n'apportent pas de valeurs mais et au contraire de la confusion. Cet étape permet d'harmoniser et de facilité le travail pour le chargement du dataset dans PowerBI en réduisant le nombre d'ID.

![Prétraitement](images/Preprocessing_suppression_Colonnes_inutiles.png)

🔧Nettoyage et standardisation des types de données.

Conversion de DISCOVERY_TIME (ex: 1345 → 13:45) :
- conversion en string
- remplissage des zéros (zfill)
- transformation en format horaire avec pd.to_datetime
- extraction de .dt.time

![Visualisations](images/Preprocessing_Changement_types_info.png)


### Visualisation des tendances

Diagramme circulaire

Après avoir apporter toutes les modifications, nettoyé les données, cela a permis d'effectuer des premiers essais de graphiques avec les bibliothèques de graphiques Matplotlib et Seaborn.
Dans ce cas précis le diagramme circulaire nous donne un bref apérçu des causes provoquant des feux de forêt.

![Visualisations](images/Visualisations_Matplotlib_Pie_Python.png)

![Visualisations](images/Visualisations_Matplotlib_pie_graphique.png)

Diagramme en barres empilées (Stacked bar plot)

Ce graphique met en évidence l’évolution du nombre de feux de forêt aux États-Unis entre 1992 et 2015 selon les différentes régions.  
Les régions du Southeast et du Southwest apparaissent comme les plus touchées sur l’ensemble de la période.  
On observe également une augmentation significative du nombre d’incendies autour des années 2000–2007 avant une légère baisse sur les années suivantes.

![Visualisations](images/Visualisations_BAR_Python.png) 

![Visualisations](images/Visualisations_BAR_graphique.png) 

---

## 📈 2. Dashboard Power BI


### Vue du schéma en étoile

Le modèle en étoile avec la table de faits (df_clean) et les tables de dimensions qui ont été créées permettent d'exploiter les données concernant les populations, les données métérologiques ainsi que les lieux principalement concernés etc...
Ce modèle a été choisi pour optimiser la performance des requêtes et également faciliter l'analyse.

![Dashboard Power BI](images/PowerBI_Modèle_Etoile.png)

### Vue générale du dashboard

Le dashboard met en évidence la forte proportion des incendies d’origine humaine par rapport aux causes naturelles.  
Les causes les plus fréquentes sont notamment le Debris Burning et les incendies divers (Miscellaneous).  
L’analyse temporelle révèle également des pics saisonniers importants durant les mois d’été.

![Dashboard Power BI](images/Dashboard_powerbi.png)

### KPIs & insights

Top 3 Causes d'incendie (DAX)

Cette mesure identifie les trois causes d'incendie les plus fréquentes en utilisant "TOPN" et "SUMMARIZE".
Dans PowerBI, "CONCATENATEX" va permettre d'afficher un KPI dynamique (A contrario, en remplacant "DESC" par "ASC" on obtiendra les causes les moins fréquentes).

  ![KPIs](images/Mesure_visu_top3_causes.png) 
  
![KPIs](images/Mesure_dax_top3_causes.png)


Treemap, pourcentage des causes d'incendie (DAX)

![KPIs](images/Mesure_visu_treemap.png)

![KPIs](images/Mesure_dax_treemap.png)


---

## 📂 Ressources

- 📘 Notebook Colab : *à ajouter*  
- 📊 Dashboard Power BI : *à ajouter*  

---

## 👨‍💻 Auteur

Antonio — Data Analyst  
