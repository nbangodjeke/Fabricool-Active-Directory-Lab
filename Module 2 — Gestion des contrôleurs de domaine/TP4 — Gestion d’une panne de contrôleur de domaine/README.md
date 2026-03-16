# TP4 — Gestion d’une panne de contrôleur de domaine

### Objectif

Ce TP a pour objectif de simuler la panne du contrôleur de domaine principal et de le restaurer dans le domaine Active Directory.

Les opérations réalisées permettent de comprendre les procédures utilisées pour **restaurer une infrastructure Active Directory après la perte d’un contrôleur de domaine**.

---

### Infrastructure initiale

Le domaine **ad.fabricool.com** dispose de deux contrôleurs de domaine :

```

    ad.fabricool.com
           │
   ┌───────┴────────┐
   │                │
DC-S-01           DC-S-02
(FSMO + GC)        (GC)
```

* **DC-S-01** : contrôleur de domaine principal, détenteur des rôles FSMO
* **DC-S-02** : contrôleur de domaine secondaire

---

### Scénario du TP

Les étapes principales réalisées sont :

* simulation de la panne du contrôleur de domaine **DC-S-01**
* saisie des **rôles FSMO** par **DC-S-02**
* suppression du contrôleur de domaine défaillant dans Active Directory
* reconstruction du serveur **DC-S-01**
* promotion du serveur reconstruit en contrôleur de domaine secondaire
* transfert des rôles FSMO afin de rétablir l’architecture initiale

---

### Architecture finale

```
    ad.fabricool.com
           │
   ┌───────┴────────┐
   │                │
DC-S-01           DC-S-02
(FSMO + GC)        (GC)
```
---

### Compétences mises en œuvre

Ce TP permet de maîtriser les opérations suivantes :

* gestion d’une panne de contrôleur de domaine

* analyse de l’état d’une infrastructure Active Directory

* saisie des rôles FSMO

* nettoyage des métadonnées d’un contrôleur supprimé

* reconstruction et promotion d’un contrôleur de domaine
