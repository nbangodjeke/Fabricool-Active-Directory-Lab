# Module 5 — PKI Microsoft, Services Web & Haute Performance

## Présentation

Après la mise en place de l'infrastructure Active Directory et de son administration centralisée via les stratégies de groupe, ce module introduit les services de certification Microsoft (AD CS).

L'objectif est de construire une **infrastructure PKI complète**, conforme aux bonnes pratiques, afin de sécuriser les services internes, les postes clients et certains équipements réseau grâce à l'utilisation des certificats numériques.

Au fil des travaux pratiques, une architecture hiérarchique est déployée avec une **Root CA hors domaine**, une **Enterprise Subordinate CA**, un **point de distribution HTTP**, ainsi qu'un **répondeur OCSP** permettant une validation performante de l'état des certificats. Les mécanismes de confiance, de révocation, d'inscription automatique et de sécurisation des services HTTPS sont ensuite mis en œuvre dans l'ensemble du laboratoire.

---

## Architecture du module

L'infrastructure PKI repose sur les éléments suivants :

* Une **Root CA autonome** conservée hors domaine et destinée uniquement à signer l'autorité subordonnée.
* Une **Enterprise Subordinate CA** intégrée à Active Directory pour l'émission automatique des certificats.
* Un serveur **IIS** assurant la publication des certificats, des listes de révocation (CRL) et des informations AIA.
* Un **Online Responder (OCSP)** pour accélérer la vérification de l'état des certificats.
* Des postes Windows utilisant l'**Auto-enrollment** via les GPO.
* Des équipements tiers (Linux et pfSense) intégrés à l'infrastructure de confiance.

---

## Objectifs pédagogiques

À l'issue de ce module, vous serez capable de :

* Concevoir une architecture PKI hiérarchique Microsoft.
* Déployer une Root CA Offline et une Enterprise Subordinate CA.
* Publier les certificats et les CRL via IIS.
* Comprendre le fonctionnement des extensions **AIA** et **CDP**.
* Déployer la confiance dans Active Directory à l'aide des GPO.
* Sécuriser un site IIS avec un certificat délivré par l'AD CS.
* Gérer le cycle de vie des certificats (émission, renouvellement et révocation).
* Comprendre le fonctionnement des CRL et des Delta CRL.
* Déployer et valider un répondeur **OCSP**.
* Automatiser l'inscription des certificats utilisateurs et ordinateurs.
* Intégrer un équipement tiers (pfSense) à une PKI Microsoft.

---

## Technologies utilisées

* Windows Server 2022
* Active Directory Certificate Services (AD CS)
* Active Directory Domain Services
* IIS
* Online Responder (OCSP)
* Group Policy (GPO)
* PowerShell
* Certutil
* Certreq
* Microsoft Management Console (MMC)
* pfSense CE 2.8.1

---

## Prérequis

Avant de commencer ce module, il est recommandé d'avoir terminé les modules précédents :

* Module 1 — Déploiement de l'Active Directory
* Module 2 — Gestion des contrôleurs de domaine
* Module 3 — Services d'infrastructure (DNS, DHCP)
* Module 4 — Administration via les stratégies de groupe (GPO)

Une bonne compréhension du fonctionnement d'Active Directory et des GPO est nécessaire pour exploiter pleinement les services de certification.

---

## Compétences développées

* Administration d'une PKI Microsoft
* Gestion des certificats numériques
* Déploiement d'une chaîne de confiance
* Sécurisation des services Web
* Gestion des révocations
* Déploiement d'OCSP
* Auto-enrollment via GPO
* Intégration de systèmes Windows et non-Windows dans une PKI
* Diagnostic et résolution de problèmes liés aux certificats

---

Ce module constitue une étape majeure du laboratoire **FABRICOOL**. Il transforme une infrastructure Active Directory classique en une plateforme sécurisée capable de délivrer, gérer et révoquer des certificats numériques selon les bonnes pratiques utilisées dans les environnements professionnels Microsoft.
