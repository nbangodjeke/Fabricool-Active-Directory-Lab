Module 2 — Gestion des contrôleurs de domaine

## Présentation

Ce module aborde les mécanismes fondamentaux permettant d’assurer la **disponibilité et la continuité de service d’une infrastructure Active Directory**.

Dans un environnement de production, un domaine ne doit jamais dépendre d’un seul contrôleur de domaine.
 La mise en place de **plusieurs contrôleurs de domaine** permet :

-   d’assurer la **redondance des services d’authentification**
    
-   de garantir la **réplication des données du domaine**
    
-   de maintenir les services critiques en cas de **panne d’un serveur**
    

Ce module introduit également la gestion des **rôles FSMO (Flexible Single Master Operations)**, qui sont des rôles critiques attribués à un contrôleur de domaine spécifique.

Les travaux pratiques de ce module permettent de comprendre :

-   le fonctionnement de la **réplication Active Directory**
    
-   l’importance des **rôles FSMO**
    
-   les procédures à appliquer lors de la **perte d’un contrôleur de domaine**
    

* * *

## Objectifs pédagogiques

À l’issue de ce module, les compétences suivantes seront acquises :

-   déployer un **contrôleur de domaine supplémentaire**
    
-   comprendre et vérifier la **réplication Active Directory**
    
-   identifier les **rôles FSMO**
    
-   gérer la perte d’un contrôleur de domaine
    
-   effectuer une **saisie des rôles FSMO**
    
-   réintégrer un serveur dans l’infrastructure Active Directory
    

* * *

## Architecture cible du module

L’infrastructure mise en place dans ce module repose sur un domaine Active Directory composé de deux contrôleurs de domaine.

```
          ad.fabricool.com
               │
        ┌──────┴──────┐
        │             │
     DC-S-01       DC-S-02
   (FSMO + GC)      (GC)
```

Dans cette architecture :

-   **DC-S-01** détient initialement les **5 rôles FSMO**
    
-   **DC-S-02** est ajouté comme contrôleur de domaine secondaire
    
-   les deux serveurs participent à la **réplication Active Directory**
    

* * *

## Travaux pratiques du module

### TP3 — Ajout d’un second contrôleur de domaine

Ce TP consiste à déployer un second contrôleur de domaine afin de mettre en place la **redondance Active Directory**.

À l’issue de ce TP, l’infrastructure dispose de **deux contrôleurs de domaine synchronisés**.

* * *

### TP4 — Simulation de panne et gestion des rôles FSMO

Dans ce TP, une panne du contrôleur principal est simulée afin d’observer son impact sur le domaine.

Ce TP permet de comprendre les procédures de **reprise après incident dans un environnement Active Directory**.

* * *

## Compétences acquises

Ce module permet de maîtriser les notions suivantes :

-   architecture **multi-contrôleurs de domaine**
    
-   **réplication Active Directory**
    
-   gestion des **rôles FSMO**
    
-   procédures de **reprise après incident**
    
-   réintégration d’un **contrôleur de domaine**
    

Ces compétences sont essentielles pour l’administration d’une infrastructure **Active Directory en environnement professionnel**.
