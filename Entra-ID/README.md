# Lab Microsoft Entra ID — Gestion des identités et sécurisation des accès

Ce laboratoire présente l'administration de **Microsoft Entra ID** dans l'environnement Microsoft 365 de NovaTech.

L'objectif est de reproduire différentes opérations rencontrées en **support informatique et administration systèmes** : gestion des utilisateurs, authentification multifacteur (MFA), groupes de sécurité, attribution de rôles administratifs, gestion des appareils et configuration de stratégies d'accès conditionnel.

## Environnement

- Microsoft 365
- Microsoft Entra ID
- Microsoft Entra ID P1
- Microsoft Authenticator
- Windows 11 Professionnel
- Active Directory Domain Services (AD DS)
- Tenant de laboratoire : NovaTech

---

## 5 — Administration Microsoft Entra ID

Découverte du centre d'administration Microsoft Entra et des fonctionnalités de gestion des identités.

### 5.1 — Présentation du tenant NovaTech

Consultation des principales informations du tenant :

- Nom de l'organisation et domaine principal
- Nombre d'utilisateurs, de groupes et d'appareils
- Compte administrateur connecté
- Licence Microsoft Entra ID Premium P1

### 5.2 — Gestion des utilisateurs

Consultation des comptes utilisateurs du tenant, notamment Sophie Martin et Lucas Bernard.

Découverte des opérations d'administration : création et modification de comptes, gestion des propriétés et réinitialisation des mots de passe.

![Administration Microsoft Entra ID](images/5.png)

---

## 6 — Authentification multifacteur (MFA)

Configuration et vérification de l'authentification multifacteur avec Microsoft Authenticator.

### 6.1 — Vérification des méthodes MFA

Consultation des méthodes d'authentification enregistrées pour Sophie Martin.

Vérification de la présence de Microsoft Authenticator et de son état d'activation.

### 6.2 — Réinitialisation MFA

Simulation d'un changement ou d'une perte de téléphone.

Depuis Microsoft Entra, utilisation de l'option **Exiger une réinscription de l'authentification multifacteur**.

### 6.3 — Réenregistrement Microsoft Authenticator

Configuration d'une nouvelle méthode d'authentification à l'aide d'un QR code.

![Configuration et réinitialisation MFA](images/6.1.png)

### 6.4 — Validation de l'authentification

Test du mécanisme **Number Matching** : l'utilisateur saisit dans Microsoft Authenticator le numéro affiché lors de la connexion.

### 6.5 — Vérification finale

Contrôle du réenregistrement de Microsoft Authenticator et de la disponibilité de la méthode MFA pour Sophie Martin.

![Validation et vérification MFA](images/6.2.png)

---

## 7 — Groupes et contrôle des accès

Création et administration de groupes de sécurité dans Microsoft Entra ID.

### 7.1 — Gestion des groupes

Création de deux groupes :

- **Support IT** : groupe de sécurité à attribution manuelle.
- **Support IT - Dynamique** : groupe de sécurité à appartenance dynamique.

### 7.2 — Groupe à attribution manuelle

Ajout manuel de Sophie Martin au groupe Support IT.

Cette méthode permet à l'administrateur de contrôler directement les membres du groupe.

### 7.3 — Groupe à appartenance dynamique

Configuration d'une règle basée sur l'attribut `department` :

`(user.department -eq "Support")`

Cette règle permet d'ajouter automatiquement les utilisateurs dont le département correspond à Support.

![Groupes et contrôle des accès](images/7.png)

---

## 8 — Rôles administratifs et principe du moindre privilège

Mise en pratique du **principe du moindre privilège**, qui consiste à accorder uniquement les autorisations nécessaires aux missions d'un utilisateur.

### 8.1 — Attribution d'un rôle administratif

Attribution du rôle **Administrateur de support technique** à Sophie Martin.

Ce rôle permet notamment de réaliser certaines opérations de support sur des comptes utilisateurs standards.

### 8.2 — Test sur un compte administrateur

Tentative de réinitialisation du mot de passe d'un compte disposant du rôle Administrateur général.

**Résultat :** l'opération est refusée en raison du niveau de privilège insuffisant.

![Principe du moindre privilège](images/8.png)

### 8.3 — Test sur un utilisateur standard

Tentative de réinitialisation du mot de passe de Lucas Bernard, utilisateur standard.

**Résultat :** l'opération est autorisée et l'interface permet de générer un mot de passe temporaire.

Ce test illustre la différence entre les droits d'un administrateur de support technique et ceux d'un administrateur général.

![Réinitialisation d'un compte standard](images/8.1.png)

---

## 9 — Gestion des appareils Microsoft Entra

Étude de l'enregistrement d'un poste Windows 11 dans Microsoft Entra ID.

### 9.1 — Consultation des appareils

Vérification de la présence du poste `SophieMartin` dans la liste des appareils Microsoft Entra.

Type de jonction observé : **Microsoft Entra registered**.

### 9.2 — Configuration Windows 11

Vérification des connexions du poste :

- Domaine Active Directory local : `novatech.local`
- Compte professionnel Microsoft Entra : Sophie Martin

### 9.3 — Vérification avec dsregcmd

Exécution de la commande :

`dsregcmd /status`

Résultats observés :

- `AzureAdJoined : NO`
- `DomainJoined : YES`
- `DomainName : NOVATECH`

Le poste est joint au domaine Active Directory local et enregistré dans Microsoft Entra ID.

Il ne s'agit pas d'une jonction hybride Microsoft Entra, car `AzureAdJoined` est à `NO`.

![Gestion des appareils Microsoft Entra](images/9.png)

---

## 10 — Stratégies d'accès conditionnel

Configuration et évaluation de stratégies d'accès conditionnel visant à renforcer la sécurité des connexions Microsoft 365.

### 10.1 — Création des stratégies

Création de deux stratégies :

- **LAB - MFA Sophie Martin** : demande de MFA pour l'utilisatrice Sophie Martin.
- **LAB - MFA hors réseau NovaTech** : demande de MFA pour les connexions réalisées en dehors du réseau NovaTech.

Les deux stratégies sont initialement configurées en mode **Rapport uniquement**, afin d'évaluer leur comportement sans appliquer les contrôles d'accès.

### 10.2 — Configuration des conditions

Configuration de la stratégie hors réseau :

- Utilisateurs ciblés : tous les utilisateurs
- Ressource cible : Office 365
- Emplacement exclu : Réseau NovaTech
- Contrôle d'accès : exiger une authentification multifacteur

![Stratégies d'accès conditionnel](images/10.1.png)

### 10.3 — Simulation avec What If

Utilisation de l'outil **What If** pour simuler une connexion de Sophie Martin depuis un réseau mobile extérieur à NovaTech.

Paramètres utilisés :

- Utilisateur : Sophie Martin
- Application : Office 365 Exchange Online
- Plateforme : iOS
- Application cliente : navigateur
- Adresse IP : réseau mobile externe

### 10.4 — Résultat de la simulation

Les deux stratégies sont identifiées comme applicables à la connexion simulée.

Le contrôle MFA est bien présent dans les résultats d'évaluation.

Les stratégies étant en mode Rapport uniquement, cette simulation ne constitue pas une preuve de blocage effectif.

![Simulation et résultats What If](images/10.2.png)

### 10.5 — Vérification des journaux de connexion

Consultation des journaux Microsoft Entra après une tentative de connexion de Sophie Martin depuis un réseau mobile.

Les informations consultées comprennent :

- Utilisateur et application
- Adresse IP
- État de connexion
- Exigence d'authentification
- Code d'erreur

### 10.6 — Analyse de l'authentification

Analyse de la tentative de connexion en échec et des informations relatives à l'authentification multifacteur.

Le journal indique notamment qu'aucune méthode MFA valide n'a été fournie.

Les deux stratégies apparaissent dans l'onglet des stratégies appliquées, avec un résultat en mode Rapport uniquement.

![Journaux de connexion et MFA](images/10.3.png)

---

## Compétences mises en pratique

Ce laboratoire m'a permis de travailler sur :

- Administration de Microsoft Entra ID
- Gestion des utilisateurs et des identités cloud
- Configuration et réinitialisation MFA
- Microsoft Authenticator et Number Matching
- Création de groupes de sécurité
- Gestion des appartenances manuelles et dynamiques
- Attribution de rôles administratifs
- Principe du moindre privilège
- Enregistrement des appareils Windows
- Vérification technique avec `dsregcmd`
- Configuration de stratégies d'accès conditionnel
- Gestion des emplacements réseau
- Simulation de connexions avec What If
- Analyse des journaux de connexion
- Diagnostic des échecs d'authentification

---

## Objectif professionnel

Ce laboratoire s'inscrit dans ma montée en compétences vers les métiers de **Technicien Support IT / Technicien Systèmes et Réseaux**.

Il m'a permis de développer une première expérience pratique de l'administration des identités cloud et de la sécurisation des accès Microsoft 365.

Ces travaux complètent mes laboratoires Active Directory, GLPI, Microsoft Intune, Teams, SharePoint et OneDrive.

*Laboratoire réalisé dans un environnement Microsoft 365 de test à des fins d'apprentissage.*
