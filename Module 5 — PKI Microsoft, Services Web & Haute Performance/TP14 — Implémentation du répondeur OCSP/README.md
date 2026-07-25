# TP14 — Implémentation du répondeur OCSP

## Scénario

FABRICOOL souhaite renforcer la fiabilité de son infrastructure PKI en intégrant un répondeur en ligne. L’objectif est de permettre aux clients et services du domaine de vérifier en temps réel la validité des certificats, sans dépendre du téléchargement périodique de listes de révocation volumineuses. Cette approche garantit une meilleure performance réseau et une continuité de service sécurisée.

## Objectifs

-   **Optimisation des performances réseau :** Soulager la bande passante en substituant le téléchargement périodique de CRLs volumineuses par des requêtes de vérification ciblées de quelques octets.
    
-   **Continuité d'infrastructure :** Configurer, interconnecter et valider de bout en bout le rôle *Online Responder* (AD CS) au sein du domaine `ad.fabricool.com`.
    
-   **Maîtrise des cycles de rafraîchissement :** Analyser le comportement dynamique du cache du répondeur face aux événements de révocation.
    

## Travaux réalisés

-   **Préparation de l'Autorité :** Modification de l'extension **AIA** de la SubCA afin d'injecter l'URI du répondeur et conditionner la structure des futurs certificats émis.
    
-   **Modèle de Certificat de Signature :** Duplication du modèle natif *OCSP Response Signing* et affectation des droits d'inscription (Enroll) au seul compte de machine du répondeur (`DC-S-01$`).
    
-   **Déploiement du rôle et Intégration IIS :** Installation de la fonctionnalité *Online Responder* sur `DC-S-01`.
    

## Validation

-   **Vérification de la chaîne d'infrastructure :** Constat visuel de l'intégration de la méthode d'accès OCSP au sein des extensions d'un nouveau certificat de Serveur Web Fabricool émis pour `web.ad.fabricool.com`.
    
-   **Persistance et Révocation temporelle :** Révocation du certificat de test sur la CA. Constat du maintien temporaire de la validité par le répondeur, puis du blocage de sécurité immédiat et automatique du client web à l'expiration stricte du délai de cache de 10 minutes, validant la parfaite autonomie de l'infrastructure.
