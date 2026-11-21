# Secrets — Bitwarden (Agent 4)

Procédure CLI complète (unlock, store, naming, soft-delete) : [`skills/bitwarden.md`](../skills/bitwarden.md).

## Collection

- Nom : **`Agent 4`**
- Variables d’environnement (jamais commités) :
  - `BW_CLIENTID`
  - `BW_CLIENTSECRET`
  - `BW_PASSWORD`

## Items connus

| Item | Usage |
|------|--------|
| `WALLET-01 Wallet de départ L1` | Portefeuille ETH L1 de départ (~200 € dédiés) |

Pour un wallet : mettre l’**adresse publique** dans `login.username` (citable) ; la clé / seed uniquement dans `login.password` (jamais citée).

## Discipline

1. **Ne jamais** écrire seeds, clés privées, mots de passe ou tokens dans le dépôt, les PRs, les issues ou les rapports.
2. Lire les secrets via Bitwarden CLI / session locale uniquement.
3. **Soft-delete / trash** obligatoire pour les retraits (`bw delete item`) ; **pas** de purge définitive (`--permanent` / vider la trash) sans motif documenté et validation opérateur.
4. Si un secret fuit dans un fichier local : le traiter comme compromis, le faire tourner, et ne **pas** le committer « pour corriger ».
5. `.gitignore` couvre `.env`, clés, keystores, sessions BW — ne pas contourner.

## Exemple local (non versionné)

Un fichier `.env` (ignoré) peut contenir uniquement les variables BW listées ci-dessus. Aucun contenu d’item wallet ne doit y figurer.
