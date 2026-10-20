**1) Schéma relationnel**:

- categorie(**id**, libelle)
- plat(**id**, nom, prix #id)
- commande(**id**, date_commande, numero_table)
- commande_ligne(**id**, #id_commande, #id_plat, quantite, prix_unitaire)

**2**) commande_ligne contient prix_unitaire pour l'historique car si un jour le prix des plats changes alors commande_ligne contiendra toujours le prix des anciennes plats

**3**) lorsqu'on supprime une commande alors, toutes les lignes de commandes seront supprimé à cause de l'instruction **ON DELETE CASCADE** de la table commande
