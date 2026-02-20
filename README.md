# 🍋 La Citronnade - L'application qui presse des citrons

Bienvenue dans le dépôt de l'application **La Citronnade** ! Cette application Android est un petit jeu interactif et amusant. Son but ? Vous permettre de vivre l'expérience complète de la création d'une citronnade, de l'arbre au verre, simplement en touchant votre écran. Considérez cela comme une métaphore relaxante ou un moyen simple et satisfaisant de passer le temps.

## ✨ Principe du jeu

L'application vous guide à travers un cycle simple en 5 étapes pour préparer votre boisson virtuelle :

1.  **La Récolte :** L'utilisateur démarre devant un **citronnier**. Une invite textuelle lui demande d'appuyer sur l'image pour "sélectionner" un citron.
2.  **Le Pressage :** Un **citron** apparaît. L'utilisateur doit appuyer plusieurs fois dessus pour le presser. Le nombre de pressions nécessaires est aléatoire (entre 2 et 4) pour simuler la différence entre les citrons.
3.  **La Dégustation :** Une fois le citron pressé, un **verre de citronnade fraîche** s'affiche. L'utilisateur est invité à appuyer dessus pour le "boire".
4.  **Le Remerciement :** Après avoir bu, un **verre vide** s'affiche. Un simple appui permet de signifier que l'on est prêt à recommencer.
5.  **Le Cycle :** L'application revient à l'écran du citronnier, prête pour une nouvelle tournée !

## 📸 Aperçu de l'application

Voici à quoi ressemble l'application à ses différentes étapes :

| Étape 1 : Le Citronnier | Étape 2 : Le Citron à presser | Étape 3 : La Citronnade ! |
| :---------------------: | :---------------------------: | :------------------------: |
| *Image d'un citronnier*   |      *Image d'un citron*        |   *Image d'un verre plein*   |
 
1<img width="263" height="521" alt="image" src="https://github.com/user-attachments/assets/e83db9c4-3cd0-4605-bad6-394938d375af" />
2<img width="209" height="480" alt="image" src="https://github.com/user-attachments/assets/b7213804-d826-4e12-8db5-6ea344c40e39" />
3<img width="228" height="499" alt="image" src="https://github.com/user-attachments/assets/947e48ff-cdb1-4702-a193-ac79a29d742b" />


 Étape 4 : Le Verre vide | Étape 5 : Prêt à recommencer |
| :---------------------: | :--------------------------: |
|   *Image d'un verre vide*  |     *Image du citronnier*      |


1<img width="198" height="335" alt="image" src="https://github.com/user-attachments/assets/840375a1-f809-44e8-bc4c-c75f8bc97ea6" />
2<img width="173" height="390" alt="image" src="https://github.com/user-attachments/assets/f58d23e2-1359-4144-aba7-c632004f9c7f" />













*(Les captures d'écran originales du projet sont disponibles dans les ressources.)*

## 🛠️ Fonctionnalités et Logique

L'application est construite autour des principes suivants :

*   **Interface Simple :** Une seule activité principale qui change d'aspect en fonction de l'étape.
*   **Images Contextuelles :** L'image centrale change pour refléter l'étape courante (Citronnier, Citron, Verre plein, Verre vide).
*   **Instructions Dynamiques :** Un texte guide l'utilisateur sur l'action à effectuer.
*   **Logique État/Machine à états :** Le comportement de l'application (ce qui se passe lors d'un clic) dépend entièrement de l'étape en cours.
*   **Aléatoire :** L'effort nécessaire pour presser un citron est différent à chaque fois (entre 2 et 4 pressions), ajoutant une petite touche de variété.

## 🚀 Comment ça marche ? (Pour les développeurs)

L'application est structurée autour d'un `State` (état) qui régit l'interface et les interactions. Le flux est contrôlé par un gestionnaire de clics unique qui agit différemment selon l'état :

*   **`STATE_TREE`** : Un clic fait passer à `STATE_LEMON` (le citron est cueilli).
*   **`STATE_LEMON`** : Un compteur interne s'incrémente. Lorsqu'il atteint le nombre aléatoire (`squeezeCount` entre 2 et 4), on passe à `STATE_DRINK`.
*   **`STATE_DRINK`** : Un clic fait passer à `STATE_EMPTY_GLASS` (le verre est bu).
*   **`STATE_EMPTY_GLASS`** : Un clic remet le compteur à zéro, génère un nouveau `squeezeCount` aléatoire, et repasse à `STATE_TREE` pour un nouveau cycle.

## 🎯 Objectif du projet

Ce projet a été conçu comme un exercice pour :
*   Pratiquer la gestion d'une **interface utilisateur dynamique** (changement d'images et de textes).
*   Implémenter une **machine à états simple** dans une application Android.
*   Gérer les **interactions utilisateur** de manière contextuelle.
*   Introduire un élément de **génération aléatoire** pour varier l'expérience.

Amusez-vous bien à presser des citrons ! 🍋🧃
