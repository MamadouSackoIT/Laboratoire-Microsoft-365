# 14 — OneDrive for Business

Cette partie du laboratoire est consacrée à l'utilisation et à l'administration de **OneDrive for Business** dans l'environnement Microsoft 365 de NovaTech.

L'objectif est de mettre en pratique les principales fonctionnalités rencontrées dans un contexte de support informatique : stockage cloud, synchronisation Windows, partage de fichiers, sauvegarde des dossiers utilisateurs et récupération de données.

---

## 14.1 — Accès à OneDrive for Business

Connexion à l'espace OneDrive professionnel de l'utilisateur et création d'un dossier dédié aux différents tests.

📁 Dossier utilisé : `Lab-OneDrive`

![14.1 - Accès à OneDrive](images/14.1.png)

---

## 14.2 — Synchronisation avec Windows 11

Configuration du client OneDrive sur une machine Windows 11 afin de synchroniser l'espace OneDrive professionnel avec l'Explorateur de fichiers.

Le dossier **OneDrive - NovaTech** devient directement accessible depuis Windows.

![14.2 - Synchronisation Windows 11](images/14.2.png)

---

## 14.3 — Test de synchronisation bidirectionnelle

Création et modification de fichiers afin de vérifier la synchronisation entre :

**Windows 11 ↔ OneDrive for Business**

Les fichiers créés localement apparaissent dans OneDrive Web et les fichiers présents dans le cloud sont accessibles depuis l'Explorateur Windows.

![14.3 - Synchronisation bidirectionnelle](images/14.3.png)

---

## 14.4 — Gestion des fichiers à la demande

Test de la fonctionnalité **Files On-Demand** de OneDrive.

Deux états ont notamment été testés :

- **Toujours conserver sur cet appareil** : le fichier reste disponible localement.
- **Libérer de l'espace** : le fichier reste dans OneDrive mais son contenu est stocké dans le cloud.

Les icônes d'état de Windows permettent d'identifier rapidement la disponibilité du fichier.

![14.4 - Files On-Demand](images/14.4.png)

---

## 14.5 — Partage et permissions

Test du partage d'un fichier OneDrive avec un utilisateur de l'organisation.

Deux niveaux d'autorisation peuvent être attribués :

- **Peut modifier**
- **Consultation possible**

Ce mécanisme permet de contrôler les droits accordés à chaque utilisateur lors du partage d'un document.

![14.5 - Partage et permissions](images/14.5.png)

---

## 14.6 — Sauvegarde du Bureau

Activation de la sauvegarde du dossier **Bureau** de Windows 11 avec OneDrive.

Après activation, le dossier Bureau est automatiquement synchronisé avec l'espace OneDrive professionnel et apparaît également dans OneDrive Web.

![14.6 - Sauvegarde du Bureau](images/14.6.png)

---

## 14.7 — Corbeille et restauration

Simulation de la suppression accidentelle d'un fichier utilisateur.

Le fichier `Test-Local-OneDrive.txt` a été :

1. supprimé depuis OneDrive ;
2. retrouvé dans la corbeille ;
3. restauré ;
4. récupéré dans son emplacement d'origine `Lab-OneDrive`.

![14.7 - Corbeille et restauration](images/14.7.png)

---

## 14.8 — Historique et restauration des versions

Modification volontaire du fichier `Test-Local-OneDrive.txt` afin de générer plusieurs versions.

L'historique OneDrive a permis d'identifier les versions :

`1.0` → `2.0` → `3.0` → `4.0`

La version **1.0** a ensuite été restaurée afin de récupérer le contenu original du fichier.

![14.8 - Historique des versions](images/14.8.png)

---

## Compétences mises en pratique

À travers ce laboratoire OneDrive, j'ai travaillé sur :

- OneDrive for Business
- synchronisation OneDrive sous Windows 11
- Files On-Demand
- gestion du stockage local et cloud
- partage de fichiers
- gestion des permissions
- sauvegarde des dossiers Windows
- restauration de fichiers supprimés
- historique des versions
- récupération d'une version antérieure
- diagnostic de la synchronisation OneDrive

---

## Environnement du laboratoire

| Élément | Configuration |
|---|---|
| Organisation | NovaTech |
| Service | OneDrive for Business |
| Poste client | Windows 11 Pro |
| Environnement | Microsoft 365 |
| Synchronisation | Client OneDrive Windows |
| Dossier de test | `Lab-OneDrive` |
| Fichiers de test | `Test-Local-OneDrive.txt` / `Test-Synchronisation-OneDrive.docx` |

---

> Ce laboratoire a été réalisé dans un environnement Microsoft 365 de test afin de reproduire des opérations courantes de support utilisateur et d'administration OneDrive.
