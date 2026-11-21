---
name: bitwarden
description: Accéder, stocker et retirer des secrets via Bitwarden CLI pour Agent 4 — login API, unlock, sync, conventions de nommage, soft-delete/trash. Utiliser dès qu’un secret Bitwarden est lu ou écrit.
---

# Bitwarden — Agent 4

Collection unique : **`Agent 4`**. Serveur : vault EU (`https://vault.bitwarden.eu`).

## Variables d’environnement

| Variable | Rôle |
|----------|------|
| `BW_CLIENTID` | Clé API (client_id) |
| `BW_CLIENTSECRET` | Clé API (client_secret) |
| `BW_PASSWORD` | Mot de passe vault (unlock) |

Jamais dans git, PRs, issues, rapports ou transcripts. Un `.env` local (gitignoré) peut les porter — **sans** contenu d’items wallet.

## Unlock sûr (session locale)

```bash
# 1. Login API (idempotent si déjà authentifié)
bw login --apikey

# 2. Unlock → session en mémoire uniquement
export BW_SESSION="$(bw unlock --passwordenv BW_PASSWORD --raw)"

# 3. Sync
bw sync

# 4. Vérifier
bw status   # doit afficher "unlocked"
```

Règles :

- Ne **jamais** echo / log `BW_SESSION`, `BW_PASSWORD`, ni la sortie brute de `bw unlock` / `bw get`.
- Préférer `--raw` + variable d’environnement à un fichier session versionné.
- Après usage : `bw lock` (ou fin de shell) ; ne pas committer de session.

## Lire un item (sans fuite)

```bash
# Lister la collection
COL_ID="$(bw list collections | jq -r '.[] | select(.name=="Agent 4") | .id')"
bw list items --collectionid "$COL_ID" | jq -r '.[].name'

# Champs publics seulement (ex. adresse)
bw get item "WALLET-01 Wallet de départ L1" | jq '{
  name, id,
  username: .login.username,
  password_present: (.login.password != null and .login.password != ""),
  fields: [.fields[]? | {name, type, has_value: (.value != null and .value != "")}]
}'
```

Interdit : coller seeds, clés privées, mots de passe ou exports JSON complets dans fichiers suivis, PRs, commentaires ou rapports.

## Stocker / mettre à jour

Conventions de nommage :

| Préfixe | Usage | Exemple |
|---------|--------|---------|
| `WALLET-NN` | Portefeuille on-chain | `WALLET-01 Wallet de départ L1` |
| `ACCT-…` | Compte service / exchange | `ACCT-binance-read` |
| `API-…` | Clé API | `API-etherscan` |
| `TMP-…` | Secret temporaire à retirer vite | `TMP-onboarding-xyz` |

Champs recommandés pour un wallet :

- **Nom** : `WALLET-NN` + libellé court
- **login.username** : adresse publique (`0x…`) — safe à citer dans les rapports
- **login.password** : clé privée **ou** seed (jamais les deux mélangés sans libellé)
- **notes** : métadonnées non secrètes (réseau L1, usage) — pas de seed en clair si déjà dans password
- **Collection** : toujours `Agent 4`

Création / édition via CLI interactive ou `bw create` / `bw edit` avec JSON généré en mémoire — **pas** de fichiers secrets laissés sur disque suivis par git.

Après écriture : `bw sync`.

## Soft-delete / trash (obligatoire)

1. **Retrait** = `bw delete item <id>` → l’item va à la **corbeille** (soft-delete). C’est le chemin normal.
2. **Ne pas** `bw delete … --permanent` ni vider la trash sans motif écrit (rapport quotidien ou note ops) et validation opérateur.
3. Avant soft-delete d’un wallet : noter dans le rapport l’**adresse publique** et la raison (rotation, abandon) — jamais la clé.
4. Restauration : depuis l’UI Bitwarden (Trash) ou procédure opérateur ; documenter la restauration.
5. Secrets compromis : soft-delete l’item, **faire tourner** la clé/seed hors bande, créer un nouvel item nommé clairement (`WALLET-02 …`) — ne pas « corriger » en commitant le secret.

## Checklist anti-fuite

- [ ] Aucun secret dans diff / commit / PR
- [ ] Adresses publiques OK ; clés / seeds / `BW_*` non
- [ ] Soft-delete utilisé ; pas de purge définitive improvisée
- [ ] Item dans la collection `Agent 4`
- [ ] Nom respectant les préfixes ci-dessus

## Liens

- Vue opérateur : [`docs/secrets.md`](../docs/secrets.md)
- Règles dures : [`AGENTS.md`](../AGENTS.md)
