# Analyse Vidéo Distribuée avec Accélération GPU

## Description

Ce projet implémente un système d'analyse vidéo distribuée pour la vidéosurveillance intelligente en utilisant une architecture inspirée de MPI (Message Passing Interface). L'objectif est de distribuer le traitement d'un flux vidéo entre plusieurs workers afin d'améliorer les performances grâce au parallélisme et à l'accélération GPU.

Le système utilise le modèle **YOLOv8** pour la détection d'objets et compare les performances entre une exécution sur CPU et une exécution sur GPU CUDA.

## Auteurs

- Nadia El Kasmi
- Zainab Rhouni
- Majda Chouiekh

## Contexte académique

**Université – Département Informatique**

**Module : Systèmes Répartis et Programmation Distribuée**

**TP N°10 : Analyse Vidéo Distribuée avec Accélération GPU**

## Objectifs

- Distribuer un flux vidéo entre plusieurs workers.
- Simuler les opérations MPI_Scatter et MPI_Gather.
- Effectuer la détection d'objets avec YOLOv8.
- Comparer les performances CPU et GPU.
- Mesurer l'accélération obtenue grâce à CUDA.
- Reconstruire une vidéo annotée finale.

## Architecture

```text
                Master Node
                     |
               MPI_Scatter
                     |
        -------------------------
        |                       |
    Worker 0               Worker 1
 Frames 0-74             Frames 75-149
        |                       |
 YOLOv8 CPU/GPU          YOLOv8 CPU/GPU
        |                       |
        --------MPI_Gather-------
                     |
          Vidéo finale annotée
