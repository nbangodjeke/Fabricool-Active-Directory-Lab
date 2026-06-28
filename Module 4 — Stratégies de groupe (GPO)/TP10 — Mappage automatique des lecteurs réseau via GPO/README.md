# TP10 — Mappage automatique des lecteurs réseau via GPO

## Contexte

L'entreprise FABRICOOL souhaite faciliter l'accès aux ressources partagées au sein des différents départements.

Afin d'améliorer l'organisation des données et de simplifier le travail collaboratif, des espaces de stockage réseau sont mis à disposition pour chaque service. Les utilisateurs doivent pouvoir accéder automatiquement aux ressources correspondant à leur département dès leur ouverture de session.

L'objectif est d'automatiser le mappage des lecteurs réseau tout en garantissant que seuls les utilisateurs autorisés puissent accéder aux partages qui leur sont destinés.

---

## Objectifs

Ce TP a pour objectif de :

* Mettre en place des lecteurs réseau partagés via les stratégies de groupe (GPO)
* Automatiser le mappage des lecteurs lors de l'ouverture de session
* Contrôler l'accès aux ressources à l'aide des groupes de sécurité Active Directory
* Simplifier l'accès aux documents communs des différents départements
* Vérifier le bon fonctionnement du ciblage des lecteurs réseau

---

## Environnement

* Domaine Active Directory : `ad.fabricool.com`
* Serveur hébergeant les partages : `DC-S-01`
* Utilisateurs répartis dans plusieurs unités d'organisation
* Groupes de sécurité associés à chaque département
* Ressources partagées hébergées sur le réseau

---

## Déploiement réalisé et tests

Des dossiers partagés ont été créés sur le serveur de fichiers afin de fournir un espace de travail dédié à chaque département.

Une stratégie de groupe a ensuite été configurée pour mapper automatiquement les lecteurs réseau correspondants lors de l'ouverture de session des utilisateurs.

Le ciblage est réalisé à l'aide des groupes de sécurité Active Directory. Ainsi, seuls les membres du groupe associé à un département voient apparaître le lecteur correspondant.

Les vérifications suivantes ont été réalisées :

* Connexion d'utilisateurs appartenant à différents départements
* Vérification de l'apparition automatique des lecteurs réseau
* Contrôle du ciblage basé sur les groupes de sécurité
* Validation de l'accès aux ressources partagées
* Vérification de l'absence des lecteurs non autorisés

---

## Résultats

* Les lecteurs réseau sont automatiquement mappés lors de l'ouverture de session
* Les utilisateurs accèdent directement aux ressources de leur département
* Le ciblage basé sur les groupes de sécurité fonctionne correctement
* Les ressources sont accessibles uniquement aux utilisateurs autorisés
* L'administration des partages est centralisée via les GPO

---

## Conclusion

Ce TP démontre l'intérêt du mappage automatique des lecteurs réseau dans un environnement Active Directory.

Il met en évidence la capacité des GPO à simplifier l'accès aux ressources partagées tout en assurant un contrôle précis des autorisations grâce aux groupes de sécurité.
