# TP 5 — Mise en place du service DHCP avec haute disponibilité

---

## Objectif

Ce TP a pour objectif de mettre en place un service **Windows Server DHCP** au sein du domaine **ad.fabricool.com**, puis d’assurer sa **haute disponibilité** grâce à un mécanisme de basculement entre deux serveurs.

---

## Contexte

L’infrastructure repose sur deux contrôleurs de domaine exécutant **Active Directory Domain Services** :

* DC-S-01
* DC-S-02

Les deux serveurs seront utilisés pour :

* distribuer des adresses IP automatiquement
* garantir la continuité du service DHCP en cas de panne

---

## Haute disponibilité

La redondance du service DHCP est assurée grâce au mécanisme de **failover DHCP**, permettant :

* le partage des baux entre les deux serveurs
* la continuité du service en cas d’indisponibilité d’un serveur
* une distribution des adresses IP sans interruption

---

## Résultat attendu

À l’issue de ce TP :

* les postes clients reçoivent automatiquement une adresse IP
* les deux serveurs DHCP sont opérationnels
* le basculement fonctionne correctement en cas de panne
* le service reste disponible en permanence
