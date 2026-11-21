# Secrets — Bitwarden (Agent 4)

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

## Discipline

1. **Ne jamais** écrire seeds, clés privées, mots de passe ou tokens dans le dépôt, les PRs, les issues ou les rapports.
2. Lire les secrets via Bitwarden CLI / session locale uniquement.
3. **Soft-delete / trash** obligatoire pour les retraits ; pas de purge définitive sans motif documenté.
4. Si un secret fuit dans un fichier local : le traiter comme compromis, le faire tourner, et ne **pas** le committer « pour corriger ».
5. `.gitignore` couvre `.env`, clés, keystores, sessions BW — ne pas contourner.

## Exemple local (non versionné)

Un fichier `.env` (ignoré) peut contenir uniquement les variables BW listées ci-dessus. Aucun contenu d’item wallet ne doit y figurer.
