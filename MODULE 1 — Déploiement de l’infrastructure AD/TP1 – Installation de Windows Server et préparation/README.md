# TP1 — Installation de Windows Server et préparation du serveur

## Objectif

Ce premier TP a pour objectif de **préparer un serveur Windows avant le déploiement d’Active Directory**.

Dans une infrastructure d’entreprise, un contrôleur de domaine doit être installé sur un système correctement configuré et prêt à recevoir les services de domaine. Avant toute installation d’Active Directory, plusieurs étapes de préparation sont nécessaires afin d'assurer la stabilité et la cohérence de l’infrastructure.

Ce TP constitue donc **la base technique sur laquelle reposera toute l’infrastructure du projet Fabricool**.

---

# Contexte

Dans le scénario de l'entreprise **Fabricool**, le service informatique commence par déployer l'infrastructure serveur du siège.

Le premier serveur installé deviendra par la suite **le premier contrôleur de domaine du domaine** :

```
ad.fabricool.com
```

Avant de pouvoir installer les services Active Directory, le serveur doit être :

* correctement installé
* configuré avec une adresse réseau fixe
* nommé selon la convention de nommage de l'entreprise
* accessible à distance pour l'administration
* sauvegardé dans un état initial stable

---

# Travaux réalisés dans ce TP

Dans ce TP, nous allons effectuer les opérations suivantes :

* installation du système Windows Server
* configuration d'une adresse IP statique
* application de la convention de nommage du serveur
* activation de l’administration à distance (RDP)
* création d’un snapshot de sécurité dans l’environnement de virtualisation

Ces opérations permettent de préparer un serveur qui pourra ensuite recevoir les rôles nécessaires à l’infrastructure Active Directory.

---

# Environnement utilisé

Le laboratoire est réalisé dans un environnement virtualisé.

Configuration de la machine virtuelle :

Nom du serveur :

```
DC-S-01
```

Réseau :

```
LAN-SIEGE
```

Adresse IP prévue :

```
192.168.100.2
```

Ce serveur fera partie du réseau du **siège de l'entreprise Fabricool**.

---

# Résultat attendu

À la fin de ce TP, le serveur doit être :

* installé et fonctionnel
* configuré avec une adresse IP statique
* renommé selon la convention de l’infrastructure
* accessible via le protocole RDP
* sauvegardé via un snapshot VMware

Ce serveur sera utilisé dans le TP suivant pour **installer et configurer Active Directory**.

---

# Compétences développées

Ce TP permet de développer les compétences fondamentales suivantes :

* installation d’un système Windows Server
* préparation d’un serveur pour un rôle d’infrastructure
* configuration réseau de base
* application d’une convention de nommage
* utilisation des snapshots dans un environnement virtualisé

Ces compétences constituent **les bases de l’administration d’un environnement Windows Server**.

---

# Guide pratique

Les instructions détaillées pas à pas pour réaliser ce TP sont disponibles dans le document suivant :

```
manuel-tp1-installation-windows-server.pdf
```

Ce document contient :

* les procédures complètes
* les captures d’écran
* les configurations à appliquer
* les vérifications à effectuer

