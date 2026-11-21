# Infra — hooks (pas de déploiement pour l’instant)

Ce document réserve les points d’accroche. **Aucun** VPS, Docker live, AWS CDK déployé ou SSH n’est provisionné dans le bootstrap.

## Hooks prévus

| Hook | Intention future | État |
|------|------------------|------|
| VPS + Docker | Runtime agent / jobs planifiés | documenté seulement |
| AWS CDK | Infra déclarative (si besoin cloud) | documenté seulement |
| SSH (optionnel) | Accès opérateur au VPS | documenté seulement |
| Cron rapport | 07:00 Europe/Paris (≈ 06:00 UTC hiver) | à brancher plus tard |

## Contraintes

- Secrets (SSH keys, AWS keys, tokens) → Bitwarden collection `Agent 4` uniquement.
- Pas de `*.tfstate`, `cdk.out`, clés SSH ou `.env` dans git (voir `.gitignore`).
- Toute mise en prod future = décision à sens unique → validation opérateur.

## Checklist plus tard (ne pas exécuter maintenant)

1. Choisir hébergeur / région.
2. Stocker credentials dans Bitwarden.
3. Décrire stack Docker / CDK dans `ops/` (sans secrets).
4. Brancher le cron de rapport quotidien.
5. Smoke test non destructif avant tout capital.
