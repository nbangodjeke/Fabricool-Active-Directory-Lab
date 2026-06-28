# TP9 — Déploiement centralisé d'applications via GPO

## Contexte

L'entreprise FABRICOOL souhaite simplifier la gestion des logiciels au sein de son infrastructure informatique.

Afin d'améliorer la sécurité des comptes utilisateurs, la direction informatique décide de déployer un gestionnaire de mots de passe sur l'ensemble des postes du domaine. La solution retenue est **KeePass**, qui permet aux collaborateurs de stocker et gérer leurs identifiants de manière sécurisée.

L'objectif est de centraliser le déploiement et les mises à jour des applications sans intervention manuelle sur chaque poste.

---

## Objectifs

Ce TP a pour objectif de :

* Déployer une application sur plusieurs postes via les stratégies de groupe (GPO)
* Automatiser l'installation des logiciels au démarrage des ordinateurs
* Cibler un ensemble de postes à partir d'une unité d'organisation
* Mettre en œuvre un scénario de mise à jour applicative
* Vérifier le bon fonctionnement du déploiement centralisé

---

## Environnement

* Domaine Active Directory : `ad.fabricool.com`
* Unité d'organisation cible : `OU_ORDINATEURS`
* Déploiement basé sur les packages MSI
* Application principale : KeePass

---

## Déploiement réalisé et tests

Une stratégie de groupe a été créée afin de déployer automatiquement **KeePass** sur les postes de l'unité d'organisation cible à partir d'un package MSI partagé sur le réseau.

Après validation du déploiement initial, une version plus récente de l'application a été publiée via la même GPO afin de simuler un scénario de mise à jour logicielle centralisée.

Les vérifications suivantes ont été réalisées :

* Installation automatique de KeePass sur les postes ciblés
* Vérification de la présence du logiciel après redémarrage
* Validation du bon fonctionnement de l'application
* Déploiement d'une version plus récente de KeePass
* Vérification de la prise en compte de la mise à jour sur les postes clients
* Contrôle de la version installée après redémarrage

### Validation complémentaire

Des tests supplémentaires ont également été réalisés avec plusieurs versions de Mozilla Firefox ESR afin de confirmer le comportement du mécanisme de déploiement et de mise à jour des packages MSI.

---

## Résultats

* Les applications sont déployées automatiquement sur les postes du domaine
* Les installations sont réalisées sans intervention manuelle des utilisateurs
* Les mises à jour logicielles peuvent être centralisées via les GPO
* Les postes clients reçoivent correctement les versions attendues des applications

---

## Conclusion

Ce TP démontre l'intérêt du déploiement logiciel par GPO dans un environnement Active Directory.

Il met en évidence la capacité des administrateurs à distribuer et maintenir des applications de manière centralisée, tout en réduisant les opérations manuelles sur les postes de travail.
