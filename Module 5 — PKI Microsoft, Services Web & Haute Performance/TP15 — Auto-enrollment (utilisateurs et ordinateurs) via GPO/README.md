# TP15 — Auto-enrollment (utilisateurs et ordinateurs) via GPO

## Scénario

Afin de simplifier l'administration et de garantir que l'ensemble du parc informatique de **FABRICOOL** dispose de connexions sécurisées, l'attribution des certificats numériques aux postes de travail et aux collaborateurs doit être entièrement automatisée et transparente, sans intervention manuelle du support informatique.

## Objectifs

-   Configurer et publier des modèles de certificats (Templates) compatibles avec l'inscription automatique.
    
-   Déployer des stratégies de groupe (GPO) pour automatiser la distribution et le renouvellement des certificats ordinateurs et utilisateurs.
    
-   Valider la présence et la conformité des certificats délivrés dans les magasins de clés locaux.
    

## Travaux réalisés

-   **Configuration des modèles (AD CS) :** Duplication du modèle *Ordinateur* (Computer) et *Utilisateur* (User). Activation de l'autorisation d'inscription automatique (Auto-enroll).
    
-   **Création de la GPO d'Auto-enrollment :** Configuration de la stratégie de groupe au niveau du domaine.
    
-   **Déclenchement côté client :** Forçage de l'application des stratégies de groupe et déclenchement du cycle d'inscription sur une machine cliente du domaine.
    

## Validation

Exécution des commandes de vérification sur une station de travail cliente :

DOS

```
gpupdate /force
certmgr.msc
```

*(Vérifier dans la console utilisateur que le certificat personnel délivré par l'autorité FABRICOOL est présent).*

DOS

```
certlm.msc
```

*(Vérifier dans la console ordinateur local que le certificat machine est bien présent et valide).*
