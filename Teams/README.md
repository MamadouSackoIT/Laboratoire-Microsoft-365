Laboratoire pratique consacré à l’administration de **Microsoft Teams** dans un environnement Microsoft 365 de test.

L’objectif de ce projet est de mettre en pratique des tâches proches de celles rencontrées en **support IT / administration Microsoft 365** : gestion des équipes et des canaux, contrôle des fonctionnalités utilisateurs, accès invité, politiques de réunion, gestion des applications et consultation des rapports d’utilisation.

## Environnement

- Microsoft 365
- Microsoft Teams
- Centre d’administration Microsoft Teams
- Microsoft Entra ID
- Tenant de laboratoire : NovaTech

## Travaux réalisés

### 12.1 — Création et gestion d’une équipe Teams

Création de l’équipe privée **Support NovaTech**, destinée à la collaboration du service Support IT.

Mise en place des rôles :
- propriétaire de l’équipe ;
- membre interne ;
- utilisateur invité.

![Création et gestion de l'équipe Teams](images/12.1.png)

### 12.2 — Gestion des canaux

Configuration de deux niveaux de collaboration :

- **Général** : canal standard de l’équipe ;
- **Incidents sensibles** : canal privé réservé aux utilisateurs autorisés.

Cette configuration permet de séparer les échanges courants des informations nécessitant un accès plus restreint.

![Gestion des canaux Teams](images/12.2.png)

### 12.3 — Stratégie de messagerie

Création d’une stratégie de messagerie dédiée au Support IT.

Le paramètre **Modifier des messages envoyés** a été désactivé, puis le comportement a été vérifié avec le compte de test Sophie Martin : l’option de modification n’est plus proposée dans le menu du message.

![Stratégie de messagerie Teams](images/12.3.png)

### 12.4 — Stratégie de réunion

Configuration d’une stratégie de réunion afin d’encadrer le partage de contenu.

Le partage d’écran a été limité à **Application unique**, et la possibilité pour les participants externes de donner ou demander le contrôle a été désactivée.

![Stratégie de réunion Teams](images/12.4.png)

### 12.5 — Accès invité

Invitation d’un utilisateur externe dans l’environnement NovaTech et ajout à l’équipe **Support NovaTech**.

Le test permet de vérifier la séparation des accès : l’invité peut accéder au canal standard **Général**, tandis que le canal privé **Incidents sensibles** ne lui est pas présenté puisqu’il n’en est pas membre.

![Accès invité Teams](images/12.5.png)

### 12.6 — Gestion des applications Teams

Administration de la disponibilité de l’application **Trello** depuis le Teams Admin Center.

L’application a été limitée au groupe **Support IT**, afin que seuls les utilisateurs ou groupes autorisés puissent l’installer et l’utiliser.

![Gestion des applications Teams](images/12.6.png)

### 12.7 — Analyse et rapports Teams

Consultation des rapports d’utilisation Teams et génération du rapport **Activité utilisateur Teams** sur une période de 7 jours.

L’environnement étant un laboratoire avec une activité limitée, le rapport ne contient que peu ou pas de données, mais l’exercice permet de pratiquer l’accès et l’exploitation de l’interface de reporting.

![Analyse et rapports Teams](images/12.7.png)

## Compétences mises en pratique

- Administration du Microsoft Teams Admin Center
- Création et gestion d’équipes Teams
- Gestion des membres, propriétaires et invités
- Configuration de canaux standards et privés
- Création et affectation de stratégies de messagerie
- Configuration des stratégies de réunion
- Gestion du partage de contenu
- Administration des accès invités
- Gestion de la disponibilité des applications Teams
- Utilisation des groupes pour cibler des configurations
- Consultation des rapports d’utilisation Teams
- Contrôle des accès et application du principe du moindre privilège

## Objectif professionnel

Ce laboratoire s’inscrit dans une montée en compétences orientée **Technicien Support IT / Systèmes & Réseaux**, avec une pratique concrète de l’écosystème Microsoft 365 et de l’administration des services collaboratifs.
