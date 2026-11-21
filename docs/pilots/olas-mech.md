# Pilote — Olas Mech Marketplace (Day-0)

**Date :** 2026-11-21 · **Vecteur :** V-04 (bounties / Mech) · **Canal :** top GO [`agent-markets.md`](../agent-markets.md)  
**Autorité caps :** [`risk-limits.md`](../risk-limits.md) · Plan : [`pilot-plan.md`](../pilot-plan.md) · Ledger : [`ops/ledgers/V-04.md`](../../ops/ledgers/V-04.md)

**Verdict Phase 1 :** **GO docs / dry-run** — canal crédible, triangulation OK.  
**Verdict Phase 2 (spend live) :** **NO** aujourd’hui — blocages durs listés §8.  
**0 spend on-chain réalisé** dans ce livrable.

---

## 1. Qu’est-ce qu’un Mech (résumé opérateur)

Un **Mech** est un agent Olas qui expose des **outils** (LLM, prédiction, recherche, etc.) à d’autres agents via une API commune. Les requêtes et paiements transitent par le **Mech Marketplace** (contrats + balance tracker). Olas **ne revue pas** les Mechs ; la confiance acheteur repose sur **KYA** (domaine prouvé, metadata, historique on-chain / Karma).

Sources officielles : [stack.olas.network/mech-server](https://stack.olas.network/mech-server/) · [build.olas.network/monetize](https://build.olas.network/monetize) · [olas.network/mech-marketplace](https://olas.network/mech-marketplace).

---

## 2. Comment s’enregistrer / tourner (parcours officiel)

### Prérequis runtime

| Élément | Exigence officielle | État Agent 4 (2026-11-21) |
|---------|---------------------|---------------------------|
| Python | `≥3.10, <3.12` (mech-server) ; build.olas cite parfois `<3.15` | Runner a 3.12.3 — **OK pour package**, vérifier pin exact avant install |
| Docker Engine + Compose | **Obligatoire** pour `mech run` | **Absent** sur ce runner |
| Poetry (chemin build.olas) | `≥1.4, <2` | n/a tant que Docker manquant |
| RPC chaîne | Fournisseur stable (docs recommandent Tenderly d’abord) | Non provisionné |
| Clés / wallets | Générés par `mech setup` ; **jamais** dans git | Bitwarden `Agent 4` prêt (discipline soft-delete) |

### Étapes (docs officielles)

1. `pip install mech-server` **ou** clone `valory-xyz/mech-server` + `uv sync`.
2. `mech setup -c <gnosis|base|polygon|optimism>` — workspace `~/.operate-mech/`, build agent, **déploie** un Mech on-chain, configure clés / env.
3. Éditer `~/.operate-mech/.env` (API keys outils si besoin).
4. Option outil custom : `mech add-tool AUTHOR TOOL -d "…"` → implémenter `run()` → `mech prepare-metadata --name … -c …` → `mech update-metadata -c …`.
5. KYA optionnel mais recommandé : `--operator-name` + `--operator-domain` + fichier `/.well-known/agent-registration.json` ; `--terms-url` ; off-chain URL si HTTP.
6. `mech run -c …` (Docker) ; `mech stop -c …`.
7. Test requester : `mechx request … --priority-mech <addr> --tools <tool> --chain-config …`.

Docs encouragent un **réseau virtuel Tenderly + faucet** avant mainnet.

### Chaînes supportées (mech-server)

| Chaîne | Native | OLAS | USDC | Nevermined |
|--------|--------|------|------|------------|
| **Gnosis** | ✅ (xDAI) | ✅ | ❌ | ✅ |
| Base | ✅ | ✅ | ✅ | ✅ |
| Polygon | ✅ | ✅ | ✅ | ✅ |
| Optimism | ✅ | ✅ | ✅ | ✅ |

Page marketplace / économie : turnover multi-chaîne aussi Ethereum, Arbitrum, Robinhood (périmètre plus large que le CLI `mech setup` ci-dessus).

**Chaîne cible pilote :** **Gnosis** (gas bas, xDAI ≈ €, docs testing ~0,02–0,05 xDAI).

---

## 3. Frais, paiements, minimum capital

### Frais protocole

| Poste | Montant | Source |
|-------|---------|--------|
| Fee DAO à **retrait** (claim) des paiements Mech | **15 %** | [Blog Olas 14-Aug-26](https://olas.network/blog/20-million-olas-agent-transactions) (fee live Q2 2026) |
| Frais Safe / registry | Gas réseau seulement (pas d’abo Safe) | Docs Safe + cycle de vie service Olas |
| Escrow acheteur | Deposit / prepaid dans balance tracker ; charge à livraison | [theagenteconomy.si compare](https://theagenteconomy.si/compare/agent-escrow-marketplaces) · docs mech-client |

**Litiges :** non documentés côté Olas (comparateur externe 2026-11-02) — kill si un client exige un rail hors contrat marketplace.

### Modèles de paiement Mech

- Native (prix fixe token natif / requête)
- Token ERC-20 (ex. OLAS / USDC selon chaîne)
- Nevermined subscription (native ou token)

Côté requester (tests) : NATIVE, OLAS, USDC, NVM ; prepaid `--use-prepaid` possible.

### Ordres de grandeur coût (Day-0) — prix spot 2026-11-21

Réf. prix : ETH ≈ **1 504 €** · xDAI ≈ **0,91 €** (CoinGecko API). NAV ≈ 0,136 ETH ≈ **204 €**.

| Poste | Estimation | ≈ € | ≈ ETH L1 équiv. | Notes |
|-------|------------|-----|-----------------|-------|
| Gas setup Mech Gnosis (EOA + Safe + registry + deploy Mech) | **0,05–0,15 xDAI** (hist. quickstart 0,05 ; buffer 2026) | **0,05–0,14 €** | négligeable | [mech-quickstart archivé](https://github.com/valory-xyz/mech-quickstart) ; à recalibrer au moment du setup |
| Buffer ops / tx metadata update / 1er claim | +0,5–2 xDAI | **0,5–2 €** | — | Marge anti gas-spike |
| Fond requester test (si on teste soi-même) | ≥ ~0,02 xDAI | ~0,02 € | — | [manual testing guide](https://stack.olas.network/mech-client/manual-testing-guide/) |
| Bridge L1 ETH → Gnosis | **variable + risque** | **interdit** sans auth | — | [`risk-limits.md`](../risk-limits.md) §5.3 |
| LLM / API keys outils | 0–quelques €/mois | ≤ outils V-04 | — | Préférer outils **sans** clé payante au départ |
| Hébergement Docker 24/7 | 0 aujourd’hui (non provisionné) | — | — | Blocage infra |

**Capital minimum théorique (Gnosis only, post-bridge) :** ≪ 1 € de gas + résiduel outil.  
**Capital minimum réaliste Agent 4 :** **0 €** tant que bridge + Docker non autorisés ; ensuite **≤ 5 €** proposés (§7).

### Time-to-first-earn (hypothèse)

| Étape | Durée indicative | Dépendance |
|-------|------------------|------------|
| Docs + outil stub | 0,5–1 j | Temps seulement |
| Infra Docker + RPC | bloqué | [`ops/infra-hooks.md`](../../ops/infra-hooks.md) |
| Bridge / fond Gnosis | bloqué | Auth spend + triangulation bridge |
| `mech setup` + metadata | 1–3 h une fois fondé | Gas |
| 1ère requête payante tierce | **inconnu** (jours–semaines) | Demande marketplace + différenciation outil + uptime |

Hypothèse challengée : « Mech = first earn en < 48 h après setup ».  
**Verdict :** **rejetée** sans preuve de demande pour *notre* outil ; le volume global (~111 k$ turnover marketplace, snapshot page) ne garantit pas le flux individuel.

---

## 4. Wallets & secrets

| Item | Règle |
|------|-------|
| WALLET-01 | Reste sur **ETH L1** ; floor gas 0,01 ETH ; **ne pas** y coller les clés agent Mech |
| Wallets Mech (`mech setup`) | EOA + Safe agent — stocker dans Bitwarden collection **`Agent 4`** : ex. `WALLET-02 Mech Gnosis EOA`, `WALLET-03 Mech Gnosis Safe` (adresses en username ; clés/seeds en password) |
| `.env` / `ethereum_private_key.txt` | Hors git ; workspace `~/.operate-mech/` local uniquement |
| Soft-delete | `bw delete` → trash ; jamais `--permanent` improvisé |
| Test wallets | Docs : **never use your main wallet for testing** |

---

## 5. Offre outil proposée (alignée identité / V-11)

**Nom de travail :** `noe-antiscam-brief` (lecture seule).  
**Thèse :** brève due-diligence / cartographie sources publiques pour un protocole ou un lien (pas de conseil financier, pas de shill, pas de garde de fonds).  
**Prix cible :** micropaiement native Gnosis (ordre 0,001–0,01 xDAI / requête une fois calibré) **ou** off-chain prepaid — à fixer après observation des Mechs comparables.  
**Hors scope outil :** fund-transfer, signing aveugle, exploit, KYC bypass.

---

## 6. Checklist Day-0 (exécutable)

### A — Docs / triangulation (fait dans ce PR)

- [x] Lire docs officielles mech-server + monetize + marketplace
- [x] Trianguler ≥ 2 sources indépendantes (blog fee 15 % ; theagenteconomy.si escrow ; GitHub mech-server / quickstart)
- [x] Probe HTTP : olas.network/mech-marketplace **200** · stack docs **200** · build monetize **200** · agent-economies/mech **200**
- [x] Consigner coûts / kills / anti-scam ici + ledger V-04
- [x] Proposer cap spend ≤ risk-limits (§7)
- [x] Confirmer **0 spend** réalisé

### B — Dry-run free (autorisé sans spend)

- [ ] Relire ce doc + `agent-markets.md` avant toute action
- [ ] (Option) `pip install mech-server` **sans** `mech setup` mainnet — smoke CLI `--help` seulement
- [ ] Inventorier 3 Mechs live (adresses publiques) via docs / Mech Hub ; noter outils + prix (lecture seule)
- [ ] Rédiger stub `run()` de l’outil anti-scam (hors dépôt secrets) — **pas** de deploy
- [ ] Lister RPC candidats + plan Tenderly (sans clé en git)

### C — Live (bloqué jusqu’à GO Phase 2)

- [ ] Autorisation explicite ops capital + bridge Gnosis (si besoin)
- [ ] Infra Docker provisionnée ([`ops/infra-hooks.md`](../../ops/infra-hooks.md))
- [ ] Wallet Mech créé → Bitwarden `Agent 4` (noms §4) ; **0** secret en git
- [ ] Fond ≤ cap §7 en xDAI (après bridge autorisé **ou** faucet Tenderly)
- [ ] `mech setup -c gnosis` sur Tenderly d’abord, puis mainnet si smoke OK
- [ ] Metadata + KYA domaine (si domaine opérateur disponible ; sinon Mech sans domain proof = karma/on-chain only)
- [ ] `mech run` ; 1 self-request test ≤ 0,02 xDAI
- [ ] Noter adresse Mech publique + tx explorateur dans ledger (pas de clés)

---

## 7. Cap spend proposé (exact)

| Paramètre | Valeur |
|-----------|--------|
| **Max spend pilote Mech** | **≤ 5 €** (≈ **≤ 5,5 xDAI** @ 0,91 €) |
| Sous-plafond vecteur V-04 | Cap catalogue 10 % (~20 €) ; pilote plan ≤ ~10 € → **5 €** = 50 % du pilote V-04 |
| Engage total post-trade | Doit rester ≤ 70 % NAV + floor **0,01 ETH L1** intact |
| Une allocation capital / jour | Oui (Europe/Paris) |
| Première tranche | **Gas Gnosis seulement** — pas de stake OLAS, pas de Nevermined payant, pas de dépôt « eligibility » |
| Bridge | **0 €** tant que non autorisé séparément ; si autorisé plus tard, le coût bridge **compte dans** le cap 5 € |

**Si le setup estime > 5 € de gas cumulé → stop** (kill gas-spike risk-limits : tx > 5 % de l’allocation).

---

## 8. Verdict Phase 2 — pourquoi **NO** spend live maintenant

| Blocage | Détail | Réf. |
|---------|--------|------|
| Infra Docker | `mech run` exige Docker ; non provisionné ; bootstrap = hooks only | `AGENTS.md` · `ops/infra-hooks.md` |
| Bridge | Mech cible = **Gnosis** ; fonds WALLET-01 = **ETH L1** ; bridge interdit sans auth | `risk-limits.md` §5.3 |
| Ops capital | Pas d’autorisation explicite spend on-chain | `AGENTS.md` règle 6 |
| Time-to-earn | Non prouvé pour notre outil ; dry-run d’abord | §3 |

**GO** pour poursuivre checklist §6.B (free).  
**NO** pour `mech setup` mainnet, bridge, ou financement wallets tant que les 3 blocages ci-dessus ne sont pas levés par l’opérateur / coordinateur.

---

## 9. Anti-scam checks (obligatoires)

| # | Check | Attendu |
|---|-------|---------|
| 1 | Domaines officiels seulement | `olas.network`, `stack.olas.network`, `build.olas.network`, `marketplace.olas.network`, repos `valory-xyz/*` |
| 2 | Pas de seed dans UI / DM / « support » | Kill immédiat |
| 3 | Olas ne revue pas les Mechs | Ne **jamais** payer un Mech tiers sans KYA + karma + terms ; pour *notre* offre : ne pas mentir sur accuracy |
| 4 | Registry / Safe | Suivre fix Immunefi registries (binding multisig) — ne pas réutiliser Safe « parked » obscures | [Blog registries](https://olas.network/blog/registries-update) |
| 5 | Fee 15 % | Attendu au claim — pas un « drain » surprise si documenté |
| 6 | Pas de pay-to-list | Setup = gas only ; si on demande un mint payant hors gas → kill |
| 7 | Pas de fund-custody pour tiers | Kill (V-12 / AGENTS) |
| 8 | Triangulation | ≥ 2 sources indépendantes avant tout spend (règle challenge) |

### Scams / risques connus (synthèse sources)

- **Mechs malveillants** côté demande (si on achetait) : Olas permissionless → phishing metadata, outils qui demandent des secrets dans le prompt.
- **Takeover Safe historique** (fixé) : vulnérabilité registries recovery ; fix déployé — leçon = ne pas laisser des Safes funded « parked » sans binding clair.
- **Mirrors / typosquat** CLI ou sites « olas » : installer uniquement depuis PyPI / GitHub Valory documentés.
- **Surpromesse volume** : turnover marketplace ≠ revenu d’un nouvel entrant.

---

## 10. Kill criteria (pilote)

| Déclencheur | Action |
|-------------|--------|
| Demande seed / export clé / signature hors scope | Kill immédiat + isolation wallet |
| Gas cumulé setup > **5 €** ou tx > 5 % allocation | Stop ; reporter |
| Bridge proposé vers chaîne non triangulée | Refus |
| 14 j post-`mech run` stable **sans** 1 requête tierce payante **et** sans plan d’acquisition | Pause Mech ; temps → ACP / Skyfire / V-11 |
| Fee d’entrée hors gas / « whitelist payante » | Kill V-04 sur ce canal |
| Infra exige garde de fonds clients | Kill |
| Soft jour −2 % NAV sur ops capital | Stop nouveaux engages (risk-limits) |

---

## 11. Journal de recherche (externe)

| Hypothèse | Sources (≥2) | Verdict |
|-----------|--------------|---------|
| « Mech = earn agent-natif live » | olas.network/mech-marketplace (turnover) · build.olas.network/monetize · stack mech-server | **Vrai** (marché live) ; earn **individuel** non garanti |
| « Fee protocole = 15 % au claim » | Blog 20M tx · page agent-economies/mech · theagenteconomy.si | **Confirmé** (15 % blog ; comparateur = % DAO sans chiffre — croiser blog) |
| « Setup Gnosis ≈ cents » | mech-quickstart 0,05 xDAI · testing guide ≥0,02 xDAI · gas Safe = réseau only | **Plausible** ; buffer → cap **5 €** |
| « On peut lancer aujourd’hui depuis ce runner » | ops/infra-hooks · `docker` absent · risk-limits bridge | **Faux** → Phase 2 NO |
| « Litige marketplace documenté » | theagenteconomy.si | **Non** — risque accepté / kill si conflit |

---

## 12. Prochaines actions

1. Coordinateur / opérateur : lever Docker (infra) **et/ou** autoriser bridge + spend ≤ 5 € si prioritaire.
2. Agent : exécuter §6.B dry-run ; stub outil ; pas de clés en git.
3. Si GO Phase 2 ultérieur : Bitwarden items §4 → setup Tenderly → Gnosis mainnet sous cap.

## Hors scope (rappel assignment)

Virtuals fund-transfer · Skyfire (plus tard) · game bots · Free-Work signup.
