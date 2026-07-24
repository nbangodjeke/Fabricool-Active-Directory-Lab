# TP13 — Gestion du cycle de vie des certificats

## Scénario

FABRICOOL doit être capable de retirer la confiance accordée à un certificat compromis ou devenu obsolète.

## Objectifs

-   Gérer la compromission d'un certificat d'infrastructure.
    
-   Maîtriser la publication et la vérification des listes de révocation de base et Delta.
    

## Travaux réalisés

-   **Simulation de compromission :** Révocation du certificat du site `web.ad.fabricool.com` avec le motif "Key Compromise".
    
-   **Publication :** Génération et publication forcée d'une nouvelle Base CRL et Delta CRL sur le point de distribution IIS.
    

## Validation

-   Exécution de la commande de validation sur le poste client :
    
    DOS
    
    ```
    certutil -urlfetch -verify web.ad.fabricool.com.cer
    ```
    
-   Le certificat doit être explicitement détecté et marqué comme **Révoqué (Revoked)**.
