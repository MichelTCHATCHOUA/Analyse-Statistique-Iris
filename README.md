# 🌸 Analyse Statistique Descriptive : Jeu de données Iris

Ce projet présente une analyse statistique approfondie du célèbre jeu de données **Iris** de Fisher. L'objectif est d'explorer les caractéristiques morphologiques de trois espèces d'iris (**Setosa**, **Versicolor**, **Virginica**) à travers des analyses monodimensionnelles, conditionnelles et bidimensionnelles, afin d'évaluer leur pouvoir discriminant pour la classification.

---

## 🎯 Objectif

L'étude vise à caractériser les espèces d'iris en utilisant des outils statistiques descriptifs pour :

*   Calculer les statistiques globales (moyenne, variance) des descripteurs.
*   Analyser la distribution des données par classe (statistiques conditionnelles).
*   Appliquer le **théorème de la variance totale (Konig-Huygens)** pour distinguer les variances intra-classe et inter-classe.
*   Identifier les meilleurs descripteurs pour la classification automatique.
*   Modéliser les distributions à l'aide de **Modèles de Mélange Gaussien (GMM)**.

---

## 📊 Données

*   **Source** : Jeu de données Iris de `scikit-learn`.
*   **Échantillon** : 150 observations (50 par classe).
*   **Descripteurs** : 4 Variables
    *   $d_1$ : Longueur du sépale (cm)
    *   $d_2$ : Largeur du sépale (cm)
    *   $d_3$ : Longueur du pétale (cm)
    *   $d_4$ : Largeur du pétale (cm)
*   **Classes** : 3 espèces 
    *   Setosa
    *   Versicolor
    *   Virginica

---

## 🛠️ Outils utilisés

*   **Python 3**
*   **Bibliothèques** : Pandas, NumPy, Matplotlib, Scikit-learn (GMM, KNN)
*   **Environnement** : Jupyter Notebook

---

## 📂 Structure du projet

```text
TP1-Analyse-Statistique-Iris/
│
├── README.md                # Ce fichier
├── TP1_TCHATCHOUA.pdf       # Rapport complet d'analyse
├── TP1_TCHATCHOUA.ipynb     # Notebook avec tous les calculs et graphiques
└── images/                  # Visualisations générées
```

---

## 🔬 Méthodologie d'Analyse

L'analyse est structurée en quatre étapes clés :

1.  **Analyse Monodimensionnelle** : Calcul des moyennes et variances globales pour chaque caractéristique.
2.  **Analyse Conditionnelle** : Étude des statistiques par espèce et calcul du ratio de variance inter-classe ($Var_{inter} / Var_{totale}$).
3.  **Analyse Bidimensionnelle & GMM** : Visualisation des corrélations entre paires de descripteurs et estimation des densités de probabilité par GMM.
4.  **Validation** : Vérification de l'intuition statistique par un classifieur des **K-plus proches voisins (KNN)**.

---

## 💡 Résultats Clés

### 1. Pouvoir Discriminant
*   **Petal Length ($d_3$)** est le meilleur descripteur avec un ratio de variance inter-classe de **94%**, offrant une séparation quasi-parfaite des classes.
*   **Sepal Width ($d_2$)** est le moins performant (**38%**), présentant un fort chevauchement entre Versicolor et Virginica.

### 2. Séparabilité des Classes
*   L'espèce **Setosa** est systématiquement isolée et facilement identifiable sur tous les descripteurs.
*   **Versicolor** et **Virginica** présentent des distributions plus proches, nécessitant une analyse bidimensionnelle pour une meilleure distinction.

#### 3. Performance du Classifieur
* Le modèle KNN confirme ces résultats avec une précision élevée, validant l'approche statistique descriptive préalable.

---

## 📊 Visualisations

### Distribution des classes

<p align="center">
  <img src="Images/plot_1.png" alt="Distribution des classes selon les descripteurs" width="800">
</p>

**Figure 1 : Distribution des classes selon les descripteurs**

Ce graphique présente la répartition des trois espèces d'iris (*Setosa*, *Versicolor*, *Virginica*) pour chaque caractéristique morphologique. 

**Observations clés :**
- Séparation nette de l'espèce *Setosa* sur l'ensemble des descripteurs
- Chevauchement significatif entre *Versicolor* et *Virginica*, particulièrement visible sur la largeur des sépales
- Cette distribution justifie l'approche de classification multiclasse adoptée

---

### Modélisation par GMM

<p align="center">
  <img src="Images/plot_3.png" alt="Contours de densité GMM" width="800">
</p>

**Figure 2 : Contours de densité estimés par GMM (Longueur vs Largeur des sépales)**

Cette visualisation illustre l'estimation des densités de probabilité par modèles de mélange gaussien (GMM). 

**Éléments représentés :**
- Les ellipses délimitent les contours de densité pour chaque classe
- Chaque ellipse représente une région de probabilité constante
- La disposition spatiale confirme la structure statistique des données dans le plan bidimensionnel
- La taille et l'orientation des ellipses reflètent la variance et la covariance des caractéristiques pour chaque espèce

---

## 💻 Code Source et Fichiers

*   **Notebook** : Le code complet pour le traitement des données, les calculs de variance et la génération des graphiques est disponible dans [codeSource.ipynb](TP1_TCHATCHOUA.ipynb).
*   **Rapport** : Pour une interprétation détaillée des courbes de densité et des matrices de covariance, consultez le [Rapport PDF](TP1_TCHATCHOUA.pdf).

---

## 👤 Auteur

**Michel TCHATCHOUA** - Data Scientist
