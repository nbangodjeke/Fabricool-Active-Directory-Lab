# TP11 - Déploiement de l'Infrastructure PKI Hiérarchique

## Scénario

L'entreprise **FABRICOOL** souhaite mettre en place une infrastructure de gestion de clés (PKI) conforme aux bonnes pratiques. L'objectif est de sécuriser ses services internes, ses clients multi-OS et ses équipements réseau en s'appuyant sur une architecture étanche, performante et hautement disponible.

## Objectifs

2.  **Root CA Offline :** Déployer une autorité racine isolée du domaine pour protéger la clé privée principale.
3.  **Distribution HTTP :** Centraliser la publication des certificats et des CRL sur un serveur IIS unique (`pki.ad.fabricool.com`).
4.  **Sub CA d'Entreprise :** Déployer une autorité subordonnée intégrée à Active Directory pour la délivrance automatisée.

* * *

## Travaux Réalisés

### 1. Point de Distribution HTTP (IIS sur DC-S-01)

-   Création du dossier local `C:\PKI_Data` associé au partage masqué `PKI_Data$`.
-   Configuration du répertoire virtuel IIS `/CertEnroll` avec activation de l'*Exploration de répertoires*.
-   Activation du **double échappement** pour supporter les caractères spéciaux (comme le `+` des CRL Delta).
-   Validation réussie de l'accès via le fichier de test `[http://pki.ad.fabricool.com/CertEnroll/test_pki+.txt](http://pki.ad.fabricool.com/CertEnroll/test_pki+.txt)`.

### 2. Root CA Autonome (ROOT)

-   Installation du rôle AD CS en mode *Autorité autonome racine* sur une machine en groupe de travail.
-   Augmentation de la validité de la CRL pour permettre l'extinction prolongée de la machine.
-   Purge complète des chemins par défaut (`LDAP://` et `file://`) et configuration d'extensions CDP et AIA exclusivement HTTP.
-   Publication et transfert manuel des fichiers (`ROOT_ROOT-CA.crt` et `ROOT-CA.crl`) vers le serveur IIS.

### 3. Subordinate CA d'Entreprise (DC-S-01)

-   Installation d'AD CS en mode *Autorité d'entreprise subordonnée* et génération de la CSR.
-   Signature de la CSR par la Root CA via un partage temporaire sécurisé (`Partage_PKI$`).

* * *

## Mécanique de Confiance Validée

-   **AIA HTTP (Transport) :** Permet à tous les clients (Windows, Linux, macOS) de télécharger dynamiquement les certificats intermédiaires manquants pour reconstruire la chaîne de certification lors des renouvellements.
-   **GPO (Approbation) :** L'AIA fournit le fichier, mais seule la GPO (ou un import manuel) ordonne au système de faire confiance à la racine. Le déploiement du certificat de la `ROOT-CA` dans les *Autorités racines de confiance* par GPO reste **strictement obligatoire** pour effacer l'alerte de sécurité.

* * *

## Validation Finale

Le diagnostic via la console **`pkiview.msc`** sur `DC-S-01` confirme la réussite du déploiement :

-   **100 % des voyants CDP et AIA sont au Statut OK**.
-   Les anciens chemins locaux résiduels ont été purgés.
-   La machine **Root CA a pu être officiellement éteinte** ; le point de distribution HTTP assure désormais seul la distribution de la chaîne de confiance de manière autonome.
