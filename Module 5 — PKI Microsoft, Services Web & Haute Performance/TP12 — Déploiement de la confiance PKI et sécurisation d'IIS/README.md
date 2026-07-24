# TP12 — Déploiement de la confiance PKI et sécurisation d'IIS

## Scénario

FABRICOOL souhaite automatiser la gestion des certificats pour les postes du domaine et sécuriser son portail web interne en HTTPS.

## Objectifs

-   Automatiser la distribution de la chaîne de confiance dans le domaine.
    
-   Sécuriser un site Web interne en HTTPS.
    

## Travaux réalisés

-   **Déploiement automatique de la confiance :** GPO pour propager le certificat de la Root CA dans le magasin "Autorités de certification racines de confiance" de tous les postes du domaine.
    
-   **Sécurisation Web (IIS) :** demande d'un certificat basé sur le modèle *Serveur Web Fabricool*, et configuration du binding HTTPS (Port 443) sur IIS.
    

## Validation

-   Accès à `https://web.ad.fabricool.com` depuis un poste client sans avertissement de sécurité.
