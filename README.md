# Fabricool Active Directory Lab

## Présentation du projet

Ce dépôt documente la mise en place progressive d’une **infrastructure Active Directory complète** dans un environnement virtualisé.

L’objectif de ce projet est de permettre à un étudiant ou un administrateur système débutant de **comprendre et maîtriser les bases de l’administration Windows Server** en reproduisant une infrastructure d’entreprise réaliste.

À travers une série de modules pratiques, nous allons construire progressivement l’infrastructure informatique d’une entreprise fictive appelée **Fabricool**.

Chaque module représente une étape de l’évolution de l’infrastructure.

---

# Scénario de l'entreprise

**Fabricool** est une entreprise spécialisée dans le **e-commerce**.
Elle compte environ **100 collaborateurs** répartis entre deux sites :

* le **siège**
* une **agence distante**

Afin de centraliser la gestion des utilisateurs, sécuriser les accès et faciliter l’administration du système d’information, l’entreprise décide de déployer une infrastructure basée sur **Active Directory**.

L’objectif est de mettre en place une architecture permettant :

* la gestion centralisée des utilisateurs et des ordinateurs
* l’application de politiques de sécurité
* le déploiement d’applications
* la gestion des certificats
* la haute disponibilité des services critiques
* la communication sécurisée entre plusieurs sites

---

# Architecture de l'infrastructure

L’infrastructure finale comprendra plusieurs machines virtuelles réparties entre deux réseaux :

### Siège

Réseau :

```
192.168.100.0/24
```

Serveurs :

```
DC-S-01   192.168.100.2
DC-S-02   192.168.100.3
```

---

### Agence

Réseau :

```
192.168.200.0/24
```

Serveurs :

```
DC-A-01   192.168.200.2
DC-A-02   192.168.200.3
```

---

### Postes clients

Les postes clients suivent la convention de nommage suivante :

```
PC-DEPARTEMENT-XX
```

Exemples :

```
PC-IT-01
PC-RH-01
PC-COMMERCE-01
```

---

### Firewall

Un firewall basé sur **pfSense** sera utilisé pour :

* le routage entre les réseaux
* la translation d’adresses (NAT)
* la sécurisation du réseau
* l’intégration future avec l’infrastructure de certificats (ADCS)

Nom du firewall :

```
pfsense.ad.fabricool.com
```

---

# Domaine Active Directory

Le domaine utilisé dans ce laboratoire est :

```
ad.fabricool.com
```

Deux sites Active Directory seront utilisés :

```
SIEGE
AGENCE
```

Chaque site disposera de **deux contrôleurs de domaine** afin d'assurer la haute disponibilité des services d’authentification.

---

# Objectifs pédagogiques

Ce projet a pour objectif de permettre aux apprenants de :

* comprendre le fonctionnement d’Active Directory
* apprendre à déployer une infrastructure Windows Server
* gérer des utilisateurs et des ordinateurs dans un domaine
* configurer des stratégies de groupe (GPO)
* mettre en place des services réseau comme DNS ou DHCP
* déployer une infrastructure multi-sites
* comprendre les bases de la sécurité dans un environnement Active Directory

À la fin de ce parcours, l’apprenant sera capable de **concevoir et administrer une infrastructure Active Directory de niveau débutant à intermédiaire**.

---

# Prérequis

Pour reproduire ce laboratoire, il est recommandé de disposer des éléments suivants :

### Hyperviseur

Un hyperviseur est nécessaire pour exécuter les machines virtuelles.

Exemple :

* VMware Workstation
* VirtualBox
* Proxmox

Ce projet a été réalisé avec **VMware Workstation Pro 17**, mais d'autres hyperviseurs peuvent être utilisés.

---

### Configuration matérielle recommandée

Configuration minimale :

```
RAM : 16 GB
CPU : 4 à 8 cœurs
Stockage : 50 GB minimum
```

---

### Systèmes d'exploitation utilisés

Serveurs :

```
Windows Server 2022
```

Windows Server 2019 peut également être utilisé.

Postes clients :

```
Windows 10 Pro
```

---

# Structure du projet

Le projet est organisé sous forme de **modules progressifs**.

Chaque module introduit de nouveaux concepts et fait évoluer l’infrastructure.

Les modules couvrent notamment :

* l'installation de Windows Server
* la mise en place d'Active Directory
* la gestion des utilisateurs et des ordinateurs
* les stratégies de groupe (GPO)
* la gestion des services réseau
* la haute disponibilité avec plusieurs contrôleurs de domaine
* la gestion des certificats
* la sécurisation de l’infrastructure

---

# Public cible

Ce projet est destiné aux personnes qui souhaitent :

* apprendre l’administration système Windows
* comprendre le fonctionnement d’Active Directory
* se préparer à des postes d’administrateur systèmes ou réseaux
* construire un **homelab pédagogique**

Le niveau visé est :

```
Débutant → Intermédiaire
```

---

# Licence

Ce projet est distribué sous licence **MIT**.

---

# Avertissement

Ce laboratoire est destiné à un **environnement d’apprentissage**.
Il ne doit pas être utilisé tel quel dans un environnement de production.

---

# Auteur

ODJEKE N'bango Thiery

Administrateur systèmes et réseaux en formation.

- GitHub : https://github.com/nbangodjeke
- LinkedIn : www.linkedin.com/in/n-bango-thiery-odjeke-644ba8310
