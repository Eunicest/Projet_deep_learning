# 🛣️ Segmentation de fissures par réseau U-Net (PyTorch)

## 🎯 Résultats et Étapes du Projet

| Étape / Question | Description / Résultats clés |
| :--- | :--- |
| **1. Pipeline d'entraînement** | Analyse du dataset CRACK500 (répartition train/val/test), des dataloaders, de l'équation exacte de la fonction de perte (*loss*) et des scores d'évaluation[cite: 1]. |
| **2. Entraînement & Early Stopping** | Implémentation d'une fonction d'entraînement sur 25 epochs, sauvegarde et rechargement des poids du modèle (`unet_ref`) basé sur le meilleur score F1 de validation. |
| **3. Efficacité de l'architecture U-Net** | Création et entraînement de `Unet_without_connection` (sans connexions sautées ou *skip connections*) et comparaison des performances avec le U-Net de référence. |
| **4. Augmentation des données** | Conception d'une stratégie d'augmentation des données intégrée dans la classe `Dataset`, réentraînement sur 25 epochs (`unet_data_aug`) et comparaison des pertes et scores sur le jeu de test. |

**Conclusion du projet :** Implémentation complète d'un pipeline de segmentation sémantique en Deep Learning sous PyTorch pour la détection automatique de fissures, mettant en évidence l'apport indispensable des *skip connections* et de l'augmentation des données.

## 📝 Contexte et Objectif

* Programme réalisé dans le cadre du Master 2 M2MAS (*Réseaux de Neurones profonds pour l'Apprentissage*), encadré par Bruno Galerne à l'Université d'Orléans.
* **Objectif :** Concevoir, entraîner et évaluer un réseau de neurones U-Net pour la segmentation automatique de fissures de voirie en utilisant la base de données CRACK500.

**Démarche :**
1. Exploration des données et analyse théorique du pipeline (tailles des tenseurs, équations de loss, contraintes de dimensions multiples de 32 pour les images).
2. Premier entraînement avec suivi des métriques (temps d'exécution, loss, score F1 sur validation) et sauvegarde des poids sur disque/Google Drive.
3. Étude d'ablation : impact de la suppression des *skip connections* sur l'architecture U-Net.
4. Amélioration de la robustesse via l'intégration de techniques d'augmentation des données.

## 🛠️ Outils et Technologies
- **Langage :** Python
- **Framework Deep Learning :** PyTorch
- **Traitement d'images & Calcul :** PIL, NumPy
- **Environnement :** Google Colab (avec accélération GPU T4)
- **Jeu de données :** CRACK500 (téléchargement automatisé via des liens `gdown`)

## 📂 Contenu du Dépôt
- `Projet_M2MAS_Unet_segmentation.ipynb` : Le notebook Jupyter complet contenant les réponses documentées, le code commenté et les discussions de résultats.

## ▶️ Utilisation
1. Ouvrir le notebook sur **Google Colab** en s'assurant d'activer un runtime muni d'un GPU (ex: T4).
2. Exécuter les cellules de téléchargement et d'extraction des archives du dataset CRACK500 (`traincrop`, `testcrop`, `valcrop` et fichiers `.txt` descriptifs).
3. Exécuter séquentiellement les blocs de code pour relancer l'entraînement, évaluer les modèles ou recharger les poids de référence.

⚠️ **Remarque :** L'entraînement de chaque modèle (limité à 25 epochs) prend environ 50 minutes sur un GPU T4.

---

<details>
<summary>🇬🇧 <b>English version</b></summary>

# 🛣️ Crack Segmentation using U-Net (PyTorch)

## 🎯 Results and Project Steps

| Step / Question | Description / Key Results |
| :--- | :--- |
| **1. Training Pipeline** | Analysis of the CRACK500 dataset splits (train, val, test), dataloaders, loss function equations, and performance evaluation metrics. |
| **2. Training & Early Stopping** | Implementation of a training loop for 25 epochs, saving/loading the best model (`unet_ref`) based on the validation F1-score. |
| **3. U-Net Architecture Efficiency** | Definition and training of `Unet_without_connection` (without skip connections) and performance comparison with `unet_ref`. |
| **4. Data Augmentation Training** | Implementation of a data augmentation strategy within the custom Dataset class, training (`unet_data_aug`), and comparison with the reference model. |

## 📝 Context and Goal

* Assignment for the M2MAS Master's degree ("Deep Neural Networks for Learning"), supervised by Bruno Galerne at the University of Orléans.
* **Goal:** Build, train, and evaluate a U-Net architecture for semantic segmentation of pavement cracks using the CRACK500 dataset.

## 🛠️ Tools
- Python, PyTorch, PIL, Google Colab (GPU T4), CRACK500 Dataset

## 📂 Repository Content
- Jupyter notebook containing the fully commented code, theoretical answers, and discussion of results.

</details>
