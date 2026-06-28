# TP6 — Configuration et redondance DNS dans Active Directory

## Contexte

L'entreprise FABRICOOL poursuit le développement de son infrastructure Active Directory en préparant le déploiement de futurs services critiques tels qu'ADCS et IIS.

Afin de garantir une résolution de noms fiable et une continuité de service en cas d'indisponibilité d'un contrôleur de domaine, l'infrastructure DNS doit être correctement configurée et répliquée entre les serveurs du domaine.

L'objectif de ce TP est de vérifier le fonctionnement du service DNS intégré à Active Directory, de mettre en place une résolution directe et inverse des noms, et de préparer l'environnement pour les futurs services web et de certification.

---

## Objectifs

Ce TP a pour objectif de :

* Vérifier le fonctionnement du service DNS intégré à Active Directory
* Contrôler la réplication des données DNS entre les contrôleurs de domaine
* Mettre en place une zone de recherche inversée
* Ajouter des enregistrements DNS nécessaires à l'infrastructure
* Configurer un alias DNS pour faciliter l'accès aux futurs services
* Valider la résolution directe et inverse des noms
* Préparer l'infrastructure DNS pour les futurs déploiements IIS et ADCS

---

## Environnement

* Domaine Active Directory : `ad.fabricool.com`
* Contrôleur de domaine principal : `DC-S-01`
* Contrôleur de domaine secondaire : `DC-S-02`
* Service DNS intégré à Active Directory
* Réplication Active Directory entre les deux contrôleurs de domaine

---

## Déploiement réalisé et tests

Le service DNS étant intégré à Active Directory, les zones DNS ont été automatiquement créées lors de l'installation des contrôleurs de domaine.

Une zone de recherche inversée a été configurée afin de permettre la résolution des adresses IP vers les noms d'hôtes.

Un enregistrement de type A a été ajouté pour le serveur `DC-S-02` afin de vérifier la réplication des données DNS entre les deux contrôleurs de domaine.

Un alias DNS a également été créé pour préparer l'accès simplifié aux futurs services hébergés sur `DC-S-01`.

Les vérifications suivantes ont été réalisées :

* Vérification de la présence des zones DNS intégrées à Active Directory
* Création et validation de la zone de recherche inversée
* Création d'un enregistrement DNS de type A
* Création d'un alias DNS (CNAME)
* Vérification de la réplication DNS entre `DC-S-01` et `DC-S-02`
* Tests de résolution directe des noms
* Tests de résolution inverse des adresses IP
* Validation des résultats à l'aide de l'outil `nslookup`

---

## Résultats

* Le service DNS fonctionne correctement sur les deux contrôleurs de domaine
* Les données DNS sont répliquées entre `DC-S-01` et `DC-S-02`
* La résolution directe des noms est opérationnelle
* La résolution inverse des adresses IP est fonctionnelle
* Les alias DNS sont correctement interprétés
* L'infrastructure DNS est prête pour le déploiement des services IIS et ADCS
* La redondance DNS améliore la disponibilité des services du domaine

---

## Conclusion

Ce TP a permis de valider le bon fonctionnement du service DNS intégré à Active Directory ainsi que la réplication des informations entre les contrôleurs de domaine.

La mise en place de la résolution inverse et la création des enregistrements nécessaires préparent l'infrastructure aux futurs services de certification et de publication web. Cette étape constitue un élément essentiel pour garantir la fiabilité et la disponibilité des services du domaine FABRICOOL.
