# Lab Microsoft Intune — Administration et gestion des postes Windows

Ce laboratoire présente la configuration et l'utilisation de **Microsoft Intune** dans l'environnement Microsoft 365 de NovaTech.

L'objectif est de découvrir les principales fonctionnalités de gestion des terminaux (MDM) : enrôlement des appareils, déploiement de stratégies de configuration, contrôle de conformité, installation d'applications et administration à distance.

## Environnement technique

- **Microsoft Intune** : administration des terminaux
- **Microsoft Entra ID** : gestion des identités et jonction des appareils
- **Windows 11 Pro** : poste client de laboratoire
- **Oracle VirtualBox** : environnement de virtualisation
- **Tenant Microsoft 365** : NovaTech
- **Utilisateur de test** : Sophie Martin
- **Appareil administré** : WINDOWS11PRO-UN

---

## 11.1 — Enrôlement du poste Windows 11 Pro

Enrôlement d'une machine virtuelle Windows 11 Pro dans Microsoft Intune.

Le poste **WINDOWS11PRO-UN** apparaît dans le centre d'administration Intune et est associé à l'utilisatrice Sophie Martin.

La console permet de consulter :

- L'état de gestion de l'appareil
- L'utilisateur principal
- La conformité du poste
- Les stratégies appliquées
- Les informations matérielles et système

**Résultat :** le poste est enregistré et administrable depuis Microsoft Intune.

![Enrôlement Windows 11 dans Intune](images/11.1.png)

---

## 11.2 — Vérification de la jonction Microsoft Entra ID

Vérification de la jonction du poste Windows 11 Pro à Microsoft Entra ID.

La commande suivante est exécutée sur le poste :

`dsregcmd /status`

Les informations obtenues confirment :

- `AzureAdJoined : YES`
- `DomainJoined : NO`
- `DeviceAuthStatus : SUCCESS`

**Résultat :** le poste est joint à Microsoft Entra ID, sans être joint à un domaine Active Directory local.

![Vérification de la jonction Microsoft Entra](images/11.2.png)

---

## 11.3 — Déploiement d'une stratégie de configuration

Création d'une stratégie **NovaTech - Configuration Windows** depuis le catalogue des paramètres Microsoft Intune.

L'objectif est de restreindre l'accès au Panneau de configuration et aux paramètres Windows pour les utilisateurs concernés.

Configuration utilisée :

- Catégorie : Control Panel
- Paramètre : Prohibit access to Control Panel and PC settings (User)
- Valeur : Enabled

Cette stratégie permet de centraliser l'application de restrictions sur les postes Windows gérés.

![Déploiement d'une stratégie de configuration](images/11.3.png)

---

## 11.4 — Vérification de l'application de la stratégie

Après la synchronisation du poste, un test est réalisé depuis la session Windows.

L'utilisateur tente d'accéder au Panneau de configuration.

Windows affiche un message indiquant que l'opération est annulée en raison de restrictions définies sur l'ordinateur.

**Résultat :** l'accès au Panneau de configuration est bloqué, confirmant le fonctionnement de la restriction testée.

![Vérification du blocage du Panneau de configuration](images/11.4.png)

---

## 11.5 — Stratégie de conformité Windows

Création d'une stratégie **NovaTech - Conformité Windows** pour vérifier le respect des exigences de sécurité.

Le contrôle configuré porte sur le pare-feu Windows.

Paramètres :

- Plateforme : Windows 10 et versions ultérieures
- Exigence : pare-feu obligatoire
- Action en cas de non-conformité : marquer immédiatement l'appareil comme non conforme

Après évaluation, le poste WINDOWS11PRO-UN apparaît avec l'état **Conforme**.

**Résultat :** l'appareil satisfait à l'exigence de conformité configurée.

![Stratégie de conformité Windows](images/11.5.png)

---

## 11.6 — Déploiement d'une application avec Intune

Déploiement du lecteur multimédia **VLC** sur le poste Windows 11 Pro.

L'application est ajoutée dans Microsoft Intune en tant qu'application Microsoft Store (nouvelle expérience), puis affectée au poste concerné.

Les vérifications réalisées comprennent :

1. Consultation de l'application VLC dans Intune.
2. Vérification de l'état d'installation sur l'appareil.
3. Contrôle de la présence de VLC sur Windows 11.
4. Ouverture de l'application pour vérifier son fonctionnement.

**Résultat :** Intune indique que VLC est installé et l'application fonctionne sur le poste.

![Déploiement de VLC avec Intune](images/11.6.png)

---

## 11.7 — Redémarrage à distance d'un poste

Test d'une action d'administration à distance depuis Microsoft Intune.

Depuis la fiche de l'appareil WINDOWS11PRO-UN, la commande **Redémarrer** est envoyée.

Le déroulement observé :

1. Envoi de la commande depuis Intune.
2. Affichage d'une notification sur le poste utilisateur.
3. Redémarrage automatique de Windows.

**Résultat :** le redémarrage à distance est exécuté avec succès.

![Redémarrage à distance avec Intune](images/11.7.png)

---

## 11.8 — Synchronisation à distance du poste

Déclenchement manuel d'une synchronisation depuis Microsoft Intune.

Cette opération permet de demander au poste de contacter le service Intune afin de vérifier les stratégies, les applications et les scripts qui lui sont affectés.

Depuis la fiche de l'appareil, l'action **Synchroniser** est exécutée.

Le suivi de synchronisation confirme le traitement des éléments suivants :

- Notification de l'appareil
- Stratégies
- Applications
- Scripts

**Résultat :** la synchronisation est effectuée avec succès. Aucune nouvelle mise à jour de stratégie, d'application ou de script n'est signalée lors du contrôle.

![Synchronisation à distance du poste](images/11.8.png)

---

## Compétences mises en pratique

Ce laboratoire m'a permis de développer des compétences en :

- Administration Microsoft Intune
- Gestion des terminaux Windows (MDM)
- Enrôlement et gestion des appareils
- Jonction Microsoft Entra ID
- Vérification technique avec `dsregcmd`
- Création et déploiement de stratégies de configuration
- Gestion des restrictions utilisateur
- Configuration et suivi des stratégies de conformité
- Déploiement d'applications Microsoft Store
- Suivi des installations sur les appareils
- Redémarrage à distance
- Synchronisation et actualisation des stratégies
- Diagnostic et vérification des opérations d'administration

---

## Objectif professionnel

Ce laboratoire s'inscrit dans ma reconversion vers les métiers de **Technicien Support IT et Technicien Systèmes & Réseaux**.

Il m'a permis de découvrir concrètement l'administration des postes Windows depuis une plateforme centralisée, ainsi que les fonctionnalités de gestion et de sécurisation des terminaux utilisées en environnement professionnel.

Ces travaux complètent mes laboratoires **Active Directory, GLPI, Microsoft Entra ID, Teams, SharePoint et OneDrive**.

*Laboratoire réalisé dans un environnement Microsoft 365 de test à des fins d'apprentissage.*
