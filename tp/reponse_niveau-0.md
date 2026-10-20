**1) Schéma relationnel**:

- categorie(**id**, libelle)
- plat(**id**, nom, prix #id)
- commande(**id**, date_commande, numero_table)
- commande_ligne(**id**, #id_commande, #id_plat, quantite, prix_unitaire)

**2**) commande_ligne contient prix_unitaire pour l'historique car si un jour le prix des plats changes alors commande_ligne contiendra toujours le prix des anciennes plats

**3**) lorsqu'on supprime une commande alors, toutes les lignes de commandes seront supprimé à cause de l'instruction **ON DELETE CASCADE** de la table commande

**4**)

- a: 200 OK
- b: 201 Created
- c: 422 Unprocessable Content
- d: 409 Conflict (Ce plat figure déjà dans des commandes, il ne peut pas être supprimé.)
- e: 404 Not Found (Commande 999 introuvable.)

**5**)
- J'ai obtenu le code 201 car la requête était pour une création.

**6**)

- PostgreSQL bloque la suppression
- Ligne de code:

```php
    return $this->erreur('Ce plat figure déjà dans des commandes, il ne peut pas être supprimé.', 409);
```

**7**)

Je travaille sur windows alors j'ai du utiliser un fichier.json pour les données à cause du formatage de powershell provoquand une exception

```powershell
    cd tp;
    curl.exe -X POST "http://localhost:8080/api/commandes" -H "Content-Type: application/json" -d "@niveau_0.json"
```
