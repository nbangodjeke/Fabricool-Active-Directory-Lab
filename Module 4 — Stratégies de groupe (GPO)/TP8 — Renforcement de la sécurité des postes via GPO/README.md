# TP8 — Renforcement de la sécurité des postes via GPO

## Contexte

L’entreprise FABRICOOL souhaite renforcer la sécurité de ses postes de travail afin de limiter les risques liés :

* à l’utilisation de supports amovibles (clé USB, disque externe…)
* aux mots de passe faibles
* à l’accès non contrôlé aux outils système sensibles

Cependant, les administrateurs IT doivent conserver certains privilèges pour assurer la gestion du système.

---

## Objectifs

Ce TP a pour objectif de :

* Mettre en place des **stratégies de sécurité globales** via les GPO
* Restreindre l’accès à certains outils système
* Appliquer une **politique de mot de passe sécurisée**
* Gérer des **exceptions via filtrage de sécurité**

---

## Environnement

* Domaine Active Directory : `ad.fabricoool.com`
* Utilisateurs et ordinateurs répartis dans des unités d’organisation
* Groupe IT : `g_it`

---

## Stratégies mises en place

* Blocage des périphériques amovibles
* Politique de mot de passe
* Blocage des outils d’administration

---

## Gestion des exceptions

Afin de permettre aux administrateurs d’exercer leurs fonctions :

* Un groupe **`g_it`** est utilisé
* Un **filtrage de sécurité** est appliqué sur la GPO de restriction des outils d'administration 

---

## Résultats

* Les postes utilisateurs sont sécurisés
* Les restrictions sont correctement appliquées
* Les administrateurs bénéficient d’un accès adapté à leurs besoins
* La politique de mot de passe est correctement appliquée et empêche l’utilisation de mots de passe faibles

---

## Compétences acquises

* Déployer et configurer des stratégies de groupe (GPO) dans un environnement Active Directory
* Renforcer la sécurité des postes utilisateurs via des politiques restrictives
* Mettre en place une politique de mot de passe conforme aux bonnes pratiques
* Restreindre l’accès aux outils système sensibles (CMD, panneau de configuration)
* Utiliser le filtrage de sécurité pour gérer des exceptions de manière propre et professionnelle
