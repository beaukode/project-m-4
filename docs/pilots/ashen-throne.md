# Pilote — Ashen Throne MCP / Cup (Day-0)

**Date :** 2026-11-21 · **Vecteur :** V-13 (jeux assist / API autorisée) · **Source :** [`game-deep-study-top5.md`](../game-deep-study-top5.md) §5  
**Autorité caps :** [`risk-limits.md`](../risk-limits.md) · Ledger : [`ops/ledgers/V-13.md`](../../ops/ledgers/V-13.md)  
**Identité :** [`identities/noe-marlin.md`](../../identities/noe-marlin.md)

**Verdict Phase 1 (docs + smoke free) :** **GO** — MCP officiel live, OAuth/DCR OK, payouts on-chain vérifiables, Cup F2P active.  
**Verdict Phase 2 (compte + MCP tools + earn) :** **NO** aujourd’hui — **compte jeu + consent OAuth browser** (§8).  
**Spend :** **0 €** réalisé et **0 €** recommandé pour Day-0 (VIP non requis ; pas d’achat $THRONE ; EV prize faible / illiquide).

---

## 1. Pourquoi Ashen (pilote #1 jeux)

| Critère | Ashen Throne | Autres top-5 |
|---------|--------------|--------------|
| Bot / API | **MCP officiel** OAuth (`game:read` / `game:act`) | MoltStation API OK mais économie ghost ; Olderfall/Cambria/RQ bots **NO** |
| Capital entrée | **F2P** Cup | Cambria Energy / RQ pass / Olderfall NFT |
| Cashout | Logs publics + tx hash (USDC Base historique → USDG Robinhood → **$THRONE Prize Lock**) | Variable / illiquide / Risk Pool |
| Fit Agent 4 | Track B + MCP read ; act seulement confirmé | Voir deep-study |

**Pas un moteur 2×/30 j** (pools ~$50–centaines $/sem) — vecteur **lent / ranking** (prefs) + contenu V-07 possible (Creator Program).

---

## 2. Qu’est-ce que c’est (résumé opérateur)

4X / war strategy MMO **browser F2P** (alpha) : Crawler, extractions, sièges Citadel. **Alliance Siege Cup** hebdo. Studio indie ; MCP first-party pour ChatGPT / Claude / clients OAuth.

| Concept | Rôle |
|---------|------|
| **MCP** | `https://mcp.ashenthr.one/mcp` — lecture compte live ; **act** = permission séparée + confirm stakes ; STOP in-game ; **pas** unattended server bot |
| **Cup** | Alliances capturent/hold districts → score → split base % + contribution |
| **Payout** | Serveur ne custody pas ; batch signé treasury ; log public + explorer |
| **Wallet vérifié** | Requis pour recevoir ; 1 wallet = 1 share / event |

Sources : [mcp](https://ashenthrone.com/mcp) · [guide MCP](https://ashenthrone.com/guides/ashen-throne-mcp) · [payouts](https://ashenthrone.com/docs/events/payouts) · [event-rules](https://ashenthrone.com/event-rules) · [play](https://play.ashenthr.one/).

---

## 3. ToS vs MCP (Track A / B)

| Source | Règle | Lecture Agent 4 |
|--------|-------|-----------------|
| [ToS 2026-05-05](https://ashenthrone.com/terms) | Interdit bots, macros, *unauthorized* scripts, unfair automation | Track A **non officiel** = **NO** |
| [MCP officiel](https://ashenthrone.com/mcp) | OAuth ; read default ; act nommé ; confirm ; STOP ; pas de standing orders | Track A via MCP = **WATCH** ; Track B = **WATCH→GO** |
| Guide MCP | *not an unattended server bot* | Pas de bot headless 24/7 |

**Règle pilote :** MCP **read** d’abord ; **act** seulement avec confirmation humaine explicite ; jamais d’injection d’inputs hors MCP.

---

## 4. Smoke tests Day-0 (0 spend) — résultats 2026-11-21

| Test | Résultat | Preuve |
|------|----------|--------|
| Site / docs / ToS / MCP pages | HTTP **200** | `ashenthrone.com`, `/mcp`, `/terms`, `/event-rules`, `/docs/events/payouts` |
| MCP endpoint sans auth | HTTP **401** `invalid_token` / Missing Authorization | Attendu |
| OAuth AS metadata | **200** issuer `https://mcp.ashenthr.one` ; scopes `game:read`, `game:act` ; PKCE S256 ; DCR `/oauth/register` | `/.well-known/oauth-authorization-server` |
| Protected resource | **200** resource `…/mcp` ; scopes idem | `/.well-known/oauth-protected-resource` |
| DCR (client public) | HTTP **201** ; `token_endpoint_auth_method=none` ; **pas** de `client_secret` | Smoke éphémère — **ne pas** committer d’ids |
| Authorize → consent | **302** vers `/oauth/consent?txn=…` | Login jeu **requis** ensuite |
| API publique payouts | **200** ; **139** lignes ; chaque entrée a `txHash` + `txUrl` | `GET /api/portal/events/payouts` |
| API publique Cup | **200** ; event **active** ; pool **$50** | `GET /api/portal/events/alliance-siege` |
| Explorer tx récent | HTTP **200** Blockscout Robinhood | Ex. batch USDG 2026-11-12 |

### Snapshot Cup (live au smoke)

| Champ | Valeur |
|-------|--------|
| Event | `alliance_cup_2026_11_16` · **active** · 2026-11-16 → 2026-11-23 UTC |
| Pool | **$50** (guarantee) · asset prize **THRONE** · network **Robinhood Chain** |
| `weekly.prizeToken` | `$THRONE` (Prize Lock 90 j ; exit early j30 / haircut 50 % ; unbond 7 j) |
| `weekly.payoutToken` (historique doc) | USDG — semaines passées encore en stablecoin |
| Min payout (balance USDG) | **$5** |
| Leaderboard | 2 alliances ; #1 **CZX** (score 42000, 7 participants) · #2 **NPA** (3000, 4) |
| Citadel | 4/4 districts tenus par CZX (Market contested au moment du smoke) |

### Payouts historiques (API publique)

| Token / chaîne | n | Σ (champ `amountUsdc`) | Max unitaire |
|----------------|---|------------------------|--------------|
| USDC / Base | 74 | ~1045 | ~199 |
| USDG / Robinhood | 65 | ~482 | ~24.6 |
| **Total lignes** | **139** | — | — |

Dernier batch visible : **2026-11-12** (USDG, event `alliance_cup_2026_11_02`, top share ~23 USDG). Preseason + cups août–nov documentés.

**Anti-scam :** triangulation docs officiels + PlayToEarn + **139 tx** publiques. Risque restant = alpha wipe, petite économie, **migration $THRONE** + liquidité DEX fine (~quelques k$ — DexScreener / DexPaprika nov. 2026).

---

## 5. Frais / capital / spend judgment

| Poste | Coût | Décision Day-0 |
|-------|------|----------------|
| Play + Cup + MCP free tier | **0 €** (100 reads / 60 acts / jour UTC) | **GO** |
| VIP Growth Status | Payant (limites MCP ↑) | **NO** — free suffit pour overview/plan |
| Achat $THRONE / stake | Illiquidité + pas d’avantage Cup | **NO** (interdit « payer pour éligibilité » + EV) |
| Bridge / gas Robinhood pour wallet vérifié | Gas multi-chaîne sous cap V-13 (≤ ~10 € outils) | **Différé** jusqu’à compte + share crédible ≥ min / Prize Lock |
| Creator Program | Temps + YouTube ; USDG Robinhood | Option V-07 / Track B contenu — pas Day-0 capital |

**Juge agent :** 0 spend. Réouvrir micro-gas wallet **seulement** si (1) compte + alliance + éligibilité Cup prouvés, (2) triangulation chaîne Robinhood OK, (3) floor L1 0,01 ETH conservé, (4) ledger V-13 mis à jour.

---

## 6. Parcours registration → MCP → earn (checklist)

### 6.1 Prérequis

| Élément | Exigence | État Agent 4 (2026-11-21) |
|---------|----------|---------------------------|
| Compte F2P | [play.ashenthr.one](https://play.ashenthr.one/) (captcha / login Google possibles) | **Absent** |
| Secrets | Bitwarden `Agent 4` — `ACCT-ashen-01` (login) ; wallet payout `WALLET-NN` séparé de WALLET-01 si besoin | Collection OK ; **pas encore d’items Ashen** |
| Client MCP OAuth | Claude / ChatGPT / Codex / tout client OAuth + PKCE | Runner : DCR smoke OK ; **consent bloqué** sans compte |
| Alliance ≥ 3 participants | Pour placer Cup | Pas rejoint |
| Wallet vérifié | Robinhood (USDG / $THRONE) ; historique Base USDC | Pas lié |

### 6.2 Étapes (ordre)

1. Créer compte F2P → stocker credentials dans Bitwarden `ACCT-ashen-01` (jamais git).
2. Progression solo jusqu’à pouvoir **rejoindre / créer alliance** (≥ 3 membres pour placer).
3. Connecter MCP **read-only** (`game:read`) via client OAuth officiel ; prompts overview / bottleneck / extraction plan (**Do not act**).
4. Si act utile : approuver `game:act` **nommé** ; une opération à la fois ; STOP in-game prêt.
5. Cup : ≥ 1 siège **ou** ≥ 60 min garrison ; viser alliance compétitive (CZX domine — évaluer join vs alliance mid).
6. Quand share / balance approche seuil : vérifier wallet (adresse **publique** seule dans ledger) ; claim auto (pas de bouton claim hebdo USDG).
7. Si semaine **$THRONE Prize Lock** : documenter vesting + plan exit (haircut) **avant** de compter l’€ dans le NAV ; ne pas oversize.

### 6.3 Secrets Bitwarden (conventions)

| Item | Contenu | Notes |
|------|---------|-------|
| `ACCT-ashen-01` | login jeu | Soft-delete si abandon |
| `WALLET-NN Ashen payout Robinhood` | clé / seed payout | **Séparé** de WALLET-01 L1 ; username = adresse publique |
| `TMP-ashen-oauth-*` | tokens OAuth si un client les matérialise hors keychain | TTL court ; trash après revoke |

---

## 7. Chemins earn (priorisés)

| Rang | Path | Rail | Effort | EV attendue | Statut |
|------|------|------|--------|-------------|--------|
| **1** | Alliance Cup (play + MCP assist) | USDG historique → **$THRONE lock** actuel | Temps siege/alliance | Faible €/sem ; lente | **Next** post-compte |
| **2** | Creator Program | ASH + USDG Robinhood (vues / refs) | Contenu V-07 | Incertain | WATCH |
| **3** | VIP / token | Payant | — | Négatif / hors thèse | **Kill spend** |

**Kill earn :** fin cash prizes **ou** MCP retiré / ToS restreint act **ou** prize 100 % $THRONE illiquide sans exit documenté **ou** 21 j sans livrable post-compte.

---

## 8. Blocages Phase 2

1. **Compte jeu** : signup browser + captcha / Google — pas automatisable proprement depuis ce runner sans humain.
2. **OAuth MCP** : consent page exige session jeu ; tools MCP non testables sans token.
3. **Temps play** : Cup = alliance + sièges/garrison ; pas de payout passif.
4. **Wallet multi-chaîne** : Robinhood pour USDG/$THRONE ; friction bridge (OK prefs, pas free).
5. **Prize Lock** : semaine live en **THRONE** — cashout ≠ USDC immédiat.

Escalade humaine **seulement** si : (a) captcha/KYC Google **exige** une personne **et** (b) on valide encore le path Cup/MCP (potentiel documenté). Sinon documenter et garder smoke APIs / Track B plans.

---

## 9. Kill criteria (pilote)

| Déclencheur | Action |
|-------------|--------|
| Automation hors MCP / overlay compétitif | Kill V-13 Ashen |
| Demande seed / signature hors scope | Kill + isolation |
| Spend VIP / $THRONE sans EV | Refus |
| Gas wallet > cap V-13 ou > 5 % allocation | Stop |
| 21 j post-compte sans éligibilité Cup ni livrable assist | Pause Ashen ; temps → MoltStation smoke / Track B sample |
| Soft jour −2 % NAV sur ops capital | Stop engages (risk-limits) |

---

## 10. Journal de recherche (externe)

| Hypothèse | Sources (≥2) | Verdict |
|-----------|--------------|---------|
| « MCP officiel agent-friendly » | ashenthrone.com/mcp · guide MCP · OAuth metadata live | **Confirmé** |
| « Payouts on-chain vérifiables » | `/api/portal/events/payouts` (139) · Blockscout tx 200 · docs payouts | **Confirmé** (USDC+USDG) |
| « Cup live F2P cette semaine » | `/api/portal/events/alliance-siege` · event-rules · events page | **Confirmé** ; prize **THRONE** |
| « $THRONE liquide pour cashout rapide » | DexScreener Robinhood · DexPaprika pool · docs Prize Lock | **Faible** — TVL fine + vesting 90 j |
| « On peut smoke tools MCP sans humain » | 401 MCP · consent 302 | **Faux** → Phase 2 NO |

---

## 11. Prochaines actions

1. **Humain / opérateur (si prioritaire) :** créer compte F2P + Bitwarden `ACCT-ashen-01` ; OAuth MCP read.
2. **Agent :** continuer lecture APIs publiques Cup/payouts (0 spend) ; préparer prompts Track B ; **ne pas** acheter VIP/$THRONE.
3. Post-compte : rejoindre alliance ≥3 → 1 semaine éligible → décider wallet Robinhood sous caps.
4. Pilote #2 jeux (parallèle docs) : MoltStation smoke API — hors ce PR si non demandé.

## Hors scope (ce livrable)

Spend on-chain · VIP · trading $THRONE · bots non MCP · merge · dump clés.
