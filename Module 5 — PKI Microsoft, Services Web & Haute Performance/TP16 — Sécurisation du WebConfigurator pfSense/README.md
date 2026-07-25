# TP16 — Sécurisation du WebConfigurator pfSense

## Scénario

L'accès à l'interface d'administration (WebConfigurator) du pare-feu de **FABRICOOL** s'effectue actuellement via un certificat auto-signé, générant des alertes de sécurité critiques sur les navigateurs des administrateurs. Pour s'aligner sur les normes de sécurité de l'entreprise, cette interface doit être sécurisée par un certificat de confiance émis et validé par la PKI interne.

## Objectifs

-   Générer une demande de signature de certificat (CSR) depuis pfSense.
    
-   Soumettre et signer la demande auprès de l'Autorité de Certification (AD CS) de FABRICOOL.
    
-   Installer le certificat signé et basculer l'interface WebConfigurator en HTTPS sécurisé et reconnu.
    

## Travaux réalisés

-   **Génération de la CSR (pfSense) :** Création d'une clé privée et d'une demande de certificat.
    
-   **Signature par l'AD CS :** Soumission de la CSR sur le serveur de certificat Windows via l'outil `certreq` . Signature du certificat à l'aide d'un modèle Web Server personnalisé.
    
-   **Importation et Activation :** Importation du certificat signé de pfSense et de la clé publique de l'autorité racine et de l'autorité intermédiaire dans le gestionnaire de certificats de pfSense.
    

## Validation

Depuis un poste client du domaine, ouverture d'un navigateur web et accès à l'interface d'administration :

Plaintext

```
URL : https://pfsense.ad.fabricool.com
```

> **Résultat attendu :** L'accès à l'interface s'effectue sans aucune alerte de sécurité ("cadenas vert" ou fermé).
