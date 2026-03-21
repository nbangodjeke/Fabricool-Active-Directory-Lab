# TP7 — Déploiement et audition de GPO 

---

## Objectif

Ce TP a pour objectif de mettre en place une **stratégie de groupe centralisée** permettant de :

* afficher une **bannière légale à la connexion**
* définir un **fond d’écran standardisé**
* **vérifier l’application des stratégies** côté client

---

## Contexte / Scénario

Dans le cadre de son développement, l’entreprise **FABRICOOL** souhaite :

* renforcer la **sécurité des accès** via un message d’avertissement
* harmoniser l’**identité visuelle** sur tous les postes
* empêcher les utilisateurs de modifier leur environnement

L’administrateur système doit donc déployer ces paramètres **via GPO**, de manière centralisée et contrôlée.

---

## Environnement

* Domaine Active Directory fonctionnel
* Une OU contenant les postes clients
* Un serveur (contrôleur de domaine)
* Un poste client joint au domaine

---

## Travaux réalisés

* Création et liaison de **GPO de personnalisation**
* Configuration d’une **bannière légale de connexion**
* Configuration d’un **fond d’écran utilisateur**
* Utilisation d’un **partage réseau** pour centraliser les ressources
* Application des stratégies sur un poste client
* Vérification via outils d’audit

---

## Résultats attendus

Après application des stratégies :

* une **bannière légale** s’affiche avant la connexion
* le **fond d’écran utilisateur est imposé**
* aucune configuration manuelle n’est nécessaire côté client

---

## Compétences acquises

* Déploiement de GPO en environnement Active Directory
* Différenciation des stratégies **Computer** et **User**
* Centralisation des ressources via partage réseau
* Vérification et diagnostic des GPO
* Compréhension du processus d’application des stratégies
