# Basilic Detector

Système de détection de plants de basilic utilisant YOLOv8, développé pour le cours 8INF804 - Vision artificielle et traitement des images (Hiver 2025).

## Description

Ce projet implémente un détecteur de plants de basilic basé sur l'algorithme de détection d'objets YOLOv8. Le système est capable d'identifier et de localiser des plants de basilic dans des images et des vidéos en temps réel.

Le détecteur a été entraîné sur un ensemble de données personnalisé d'images de basilic, annotées manuellement, et utilise l'approche de transfert d'apprentissage (fine-tuning) à partir des poids pré-entraînés de YOLOv8.

## Fonctionnalités

- Détection de plants de basilic dans des images statiques
- Détection en temps réel dans des flux vidéo
- Interface simple pour l'analyse de nouvelles images/vidéos

## Installation

### Prérequis

- Python 3.8 ou supérieur
- CUDA (recommandé pour l'accélération GPU)

### Installation des dépendances

```bash
# Cloner le dépôt
git clone https://github.com/votre-username/basilic-detector.git
cd basilic-detector

# Installer les dépendances
pip install -r local_env/requirements.txt
```

## Structure du projet

```
basilic-detector/
├── google_colab/              # Scripts et configurations pour Google Colab
│   ├── TrainYolov8CustomDataset.ipynb
│   ├── google_colab_config.yaml
│   └── runs/                  # Résultats d'entraînement Colab
├── local_env/                 # Environnement local
│   ├── config.yaml            # Configuration pour l'entraînement local
│   ├── data/                  # Dataset
│   │   ├── images/
│   │   └── labels/
│   ├── predict_video.py       # Script de prédiction sur vidéo
│   ├── requirements.txt       # Dépendances
│   ├── runs/                  # Résultats d'entraînement local
│   └── train.py               # Script d'entraînement
└── videos/                    # Vidéos de test
```

## Utilisation

### Prédiction sur vidéo

Pour détecter des plants de basilic dans une vidéo :

```bash
cd local_env
python predict_video.py
```

Par défaut, le script utilise la vidéo "basilic2.mp4" située dans le dossier `videos/`. Vous pouvez modifier le chemin dans le script pour utiliser une autre vidéo.

### Entraînement du modèle

Pour entraîner le modèle sur votre propre dataset :

```bash
cd local_env
python train.py
```

Vous pouvez modifier le fichier `config.yaml` pour ajuster les paramètres d'entraînement.

## Résultats

Le modèle a été entraîné sur 100 epochs et a atteint les performances suivantes :
- mAP50 : 0.688
- mAP50-95 : 0.457
- Precision : 0.71
- Recall : 0.617

## Améliorations futures

- Augmentation du dataset avec plus d'images et de contextes variés
- Extension à d'autres plantes aromatiques (détection multi-classes)
- Optimisation du modèle pour les appareils mobiles
- Développement d'une interface utilisateur conviviale

## Auteur

Eloi SEIDLITZ

## Remerciements

- Julien Maitre, enseignant du cours 8INF804
- Ultralytics pour la bibliothèque YOLOv8