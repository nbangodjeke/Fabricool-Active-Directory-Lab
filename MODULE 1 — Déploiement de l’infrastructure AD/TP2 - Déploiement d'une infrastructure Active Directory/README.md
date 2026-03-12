# TP2 — Déploiement d'une infrastructure Active Directory

## Projet : Fabricool Active Directory Lab

Ce TP fait partie du **module 1 : Déploiement de l’infrastructure Active Directory**.
L’objectif est de mettre en place les **fondations d’un domaine Active Directory** qui servira de base aux futurs travaux pratiques du laboratoire.

---

# Objectifs du TP

Ce TP a pour objectif de mettre en place une **première infrastructure Active Directory fonctionnelle**.

Les éléments suivants sont déployés :

* installation du rôle **Active Directory Domain Services (ADDS)**
* création de la **forêt Active Directory**
* création du **domaine**
* promotion du serveur en **contrôleur de domaine**
* structuration logique du domaine avec des **Unités Organisationnelles (OU)**
* gestion des **objets Active Directory**
* intégration d'un **poste client au domaine**
* activation de la **corbeille Active Directory**

---

# Entreprise simulée

Entreprise :

```
FABRICOOL
```

L'entreprise dispose de plusieurs sites :

* un **siège (S)**
* une **agence (A)**

Dans les modules suivants, chaque site disposera de **contrôleurs de domaine supplémentaires** afin d'assurer :

* la **haute disponibilité**
* la **réplication Active Directory**
* la **continuité de service**

---

# Architecture du domaine

Domaine Active Directory :

```
ad.fabricool.com
```

Nom NetBIOS :

```
FABRICOOL
```

Contrôleur de domaine principal :

```
DC-S-01.ad.fabricool.com
```

---

# Organisation logique du domaine

Une structure d'administration claire est mise en place grâce aux **Unités Organisationnelles (OU)**.

Structure utilisée :

<img width="565" height="271" alt="Org Chart (1)" src="https://github.com/user-attachments/assets/b0298550-ae6f-43ce-b366-e864904d802e" />

Cette organisation permet :

* une **administration plus claire**
* une **application ciblée des stratégies de groupe (GPO)**
* une **meilleure gestion des ressources**

---

# Infrastructure du laboratoire

| Machine  | Rôle                           |
| -------- | ------------------------------ |
| DC-S-01  | Contrôleur de domaine          |
| PC-IT-01 | Poste client membre du domaine |

---

# Fonctionnalités implémentées

Dans ce TP, les fonctionnalités suivantes sont opérationnelles :

* authentification centralisée des utilisateurs
* gestion des comptes utilisateurs
* gestion des groupes
* gestion des ordinateurs du domaine
* restauration d'objets supprimés via la **corbeille Active Directory**

---

# Documentation

Les **étapes complètes de déploiement et de configuration** sont disponibles dans le manuel suivant :

```
manuel-tp2-deploiement-AD.pdf
```

Ce document décrit :

* les procédures d'installation
* les configurations réalisées
* les captures d'écran du laboratoire

---

# Évolutions prévues

Les prochains modules de ce laboratoire incluront :

* l’ajout de **contrôleurs de domaine supplémentaires**
* l’étude de la **réplication Active Directory**
* la gestion des **rôles FSMO**
* la configuration des **sites Active Directory**
* le déploiement avancé des **stratégies de groupe (GPO)**
* l’ajout de services complémentaires dans l’infrastructure

---
