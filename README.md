# 🧠 Fashion MNIST Deep Learning with TensorFlow & Keras

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

## 📖 Aperçu du Projet

Ce projet marque la transition du Machine Learning classique vers le **Deep Learning**. L'objectif est de construire, entraîner et optimiser des réseaux de neurones artificiels (ANN) pour classifier les images du dataset *Fashion MNIST*.

En utilisant la librairie **Keras** (surcouche de TensorFlow), ce projet explore comment l'architecture d'un réseau de neurones (nombre de couches, nombre de neurones) influence la capacité du modèle à apprendre des motifs complexes dans des images.


## 🛠️ Architecture du Modèle

Le modèle de base est un réseau de neurones dense (Fully Connected) défini avec l'API `Sequential` de Keras :

1.  **Input Layer :** Aplatissement de l'image 28x28 pixels (784 entrées).
2.  **Preprocessing :** Couche `Rescaling(1./255)` pour normaliser les pixels entre 0 et 1, facilitant la convergence du gradient.
3.  **Hidden Layers :** Couches `Dense` avec fonction d'activation **ReLU** pour introduire de la non-linéarité.
4.  **Output Layer :** Couche `Dense` de 10 neurones avec activation **Softmax** pour obtenir des probabilités par classe.

*Optimiseur utilisé : Adam (learning rate = 0.001).*
*Fonction de perte : Categorical Crossentropy.*

## 🧪 Expérimentations & Optimisation

Le projet ne se contente pas d'un seul modèle. Une approche rigoureuse de recherche d'hyperparamètres (Grid Search manuel) a été mise en place pour tester trois architectures distinctes :

* **Modèle A :** 2 couches cachées.
* **Modèle B :** 3 couches cachées.
* **Modèle C :** 1 couche cachée.

Pour chaque architecture, le notebook teste automatiquement toutes les combinaisons suivantes :
* **Neurones par couche :** `[32, 64, 128, 256, 512]`
* **Epochs (durée d'entraînement) :** `[30, 40, 50, 60, 70]`

### 📊 Résultats des tests

Les performances (Précision/Recall) sont stockées et comparées pour identifier la configuration optimale.

* **Meilleur Modèle A (2 couches) :** 256 neurones, 40 epochs → Précision ~89.9%.
* **Meilleur Modèle B (3 couches) :** 256 neurones, 50 epochs → Précision ~90.2%.
* **Meilleur Modèle C (1 couche) :** 512 neurones, 50 epochs → Précision ~90.2%.

## 🚀 Installation et Utilisation

1.  **Cloner le dépôt :**
    ```bash
    git clone [https://github.com/ton-user/fashion-mnist-deeplearning.git](https://github.com/ton-user/fashion-mnist-deeplearning.git)
    cd fashion-mnist-deeplearning
    ```

2.  **Installer les dépendances :**
    *Assurez-vous d'avoir TensorFlow installé.*
    ```bash
    pip install pandas numpy matplotlib seaborn tensorflow scikit-learn
    ```

3.  **Lancer le Notebook :**
    ```bash
    jupyter notebook deep_learning.ipynb
    ```

## 📈 Métriques d'Évaluation

Le projet génère un rapport complet pour le modèle final sur les données de test :
* **Matrice de Confusion :** Pour visualiser les erreurs spécifiques (ex: confusion entre "Shirt" et "T-shirt").
* **Classification Report :** Précision, Rappel et F1-Score pour chacune des 10 classes.

---
*Projet réalisé dans le cadre du module Deep Learning de la Coding Academy.*

## 🇬🇧 English Summary

**Project:** Fashion MNIST Classification using Deep Learning (TensorFlow/Keras)

**Goal:** Transition from classical ML to Deep Learning to classify clothing images using Artificial Neural Networks (ANN).

**Key Features:**
* **Deep Neural Network Architecture:** Implemented a Sequential model with Input, Rescaling (normalization), Dense (ReLU), and Output (Softmax) layers.
* **Hyperparameter Optimization:** Conducted a manual Grid Search to find the optimal architecture. Tested combinations of:
    * **Neurons:** `[32, 64, 128, 256, 512]`
    * **Epochs:** `[30, 40, 50, 60, 70]`
* **Model Comparison:** Evaluated three distinct model depths (1, 2, and 3 hidden layers) to analyze the impact of network depth on accuracy.
* **Performance:** Achieved ~90% precision with optimized configurations.

**Tech Stack:** Python, TensorFlow, Keras, Pandas, Scikit-Learn.
