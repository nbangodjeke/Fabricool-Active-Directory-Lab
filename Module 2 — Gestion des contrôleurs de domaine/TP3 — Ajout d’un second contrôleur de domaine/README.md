TP3 — Ajout d’un second contrôleur de domaine

## Présentation

Dans une infrastructure Active Directory, il est fortement recommandé de disposer de **plusieurs contrôleurs de domaine** afin d’assurer la **disponibilité et la continuité des services d’authentification**.

Ce TP a pour objectif de déployer un **second contrôleur de domaine (DC-S-02)** dans le domaine existant afin de mettre en place une **redondance Active Directory** et d’observer le fonctionnement de la **réplication entre contrôleurs de domaine**.

Le serveur DC-S-02 est déployé à partir d’un **clone de machine virtuelle** créé avec VMware, après préparation du système avec **Sysprep**.

* * *

## Objectifs

À l’issue de ce TP, les objectifs suivants doivent être atteints :

-   créer un serveur à partir d’un **clone de machine virtuelle**
    
-   préparer un système Windows avec **Sysprep**
    
-   configurer un nouveau serveur dans l’infrastructure
    
-   promouvoir un serveur en **contrôleur de domaine supplémentaire**
    
-   activer le **catalogue global**
    
-   vérifier la **réplication Active Directory**
    

* * *

## Infrastructure initiale

À la fin du module précédent, l’infrastructure Active Directory se compose d’un seul contrôleur de domaine.

```
Domaine : ad.fabricool.com

DC-S-01
│
├── Active Directory
├── DNS
├── Catalogue global
└── 5 rôles FSMO
```

Cette architecture fonctionne correctement mais présente un **point de défaillance unique**.

* * *

## Architecture cible

L’objectif du TP est d’obtenir une infrastructure comportant **deux contrôleurs de domaine répliqués**.

```
        ad.fabricool.com
               │
        ┌──────┴──────┐
        │             │
     DC-S-01       DC-S-02
   (FSMO + GC)      (GC)
```

Dans cette configuration :

-   **DC-S-01** reste détenteur des rôles FSMO
    
-   **DC-S-02** agit comme contrôleur de domaine supplémentaire
    
-   les deux serveurs participent à la **réplication Active Directory**
    

* * *

## Résultat attendu

À la fin du TP, l’infrastructure Active Directory comporte **deux contrôleurs de domaine fonctionnels**.

Le domaine dispose désormais :

-   d’une **réplication Active Directory**
    
-   d’une **redondance des services d’authentification**
    
-   d’une **meilleure tolérance aux pannes**
    

* * *

## Compétences acquises

Ce TP permet de développer les compétences suivantes :

-   utilisation des **snapshots VMware**
    
-   déploiement de serveurs à partir de **clones liés**
    
-   préparation d’un système avec **Sysprep**
    
-   promotion d’un serveur en **contrôleur de domaine**
    
-   compréhension de la **réplication Active Directory**
