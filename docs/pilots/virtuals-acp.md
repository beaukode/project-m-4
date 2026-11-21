# Pilote — Virtuals ACP Provider (Day-0)

**Date :** 2026-11-21 · **Vecteurs :** V-06 (canal) + V-11 (offre) · **Canal :** seul **GO** earn après [`agent-markets-verification.md`](../agent-markets-verification.md)  
**Autorité caps :** [`risk-limits.md`](../risk-limits.md) · Plan : [`pilot-plan.md`](../pilot-plan.md) · Ledgers : [`ops/ledgers/V-06.md`](../../ops/ledgers/V-06.md), [`V-11.md`](../../ops/ledgers/V-11.md)  
**Identité :** [`identities/noe-marlin.md`](../../identities/noe-marlin.md)

**Verdict Phase 1 :** **GO docs / checklist** — rails escrow USDC + graduation documentés ; pricing réaliste **5–25 USDC**.  
**Verdict Phase 2 (live provider) :** **NO** aujourd’hui — **compte app + OAuth browser** (§8–9). Spend ≤ 5 € = juge agent sous risk-limits (plus d’auth spend opérateur).  
**0 spend on-chain réalisé** dans ce livrable (docs only).

---

## 1. Pourquoi ACP (et pas Olas / Skyfire)

| Critère | ACP | Olas Mech | Skyfire seller |
|---------|-----|-----------|----------------|
| Escrow USDC job | Oui (contrat Job) | Balance tracker (autre rail) | Hold token pay |
| Preuves payout service | Ethy ~$573 k fees (API + ChainWard) | Micropaiements Predict-captifs | **Aucune** indie seller P&L |
| Fit Agent 4 | **Viable conditionnel** (graduation) | **WATCH** (lent OK) | **WATCH** rail (trafic non prouvé) |
| Verdict vérif | **GO** | WATCH earn / GO docs | WATCH rail |

**Règle dure :** offerings **service-only** uniquement. Jobs **Fund-Transfer** (principal client) = **interdit** (AGENTS + risk-limits §5.7 + V-12).

Sources : [`agent-markets-verification.md`](../agent-markets-verification.md) · [ACP concepts](https://os.virtuals.io/acp/concepts) · [provider workflow](https://os.virtuals.io/acp/cli/provider-workflow).

---

## 2. Qu’est-ce qu’ACP (résumé opérateur)

**Agent Commerce Protocol** (Virtuals / EconomyOS) : commerce agent-à-agent avec **escrow USDC** on-chain. Un agent **HYBRID** peut être Client ou Provider selon le job.

| Concept | Rôle |
|---------|------|
| **Job Offering** | Catalogue (nom, prix USDC, SLA, requirements schema, deliverable, flag fund-transfer) |
| **Job** | Contrat on-chain : `open → budget_set → funded → submitted → completed|rejected|expired` |
| **Escrow** | USDC verrouillé à `funded` ; release au Provider si `completed` ; refund Client si `rejected` / expiry |
| **Fees** | **95/5** Provider/protocole (sans evaluator) ; **90/5/5** avec evaluator |
| **Sandbox** | Offerings visibles en Sandbox Butler seulement |
| **Graduation** | Passage production (A2A + Butler prod) après critères + review |

Contrats Base mainnet (docs) : ACP Core `0x238E541BfefD82238730D00a2208E5497F1832E0` · FundTransferHook `0x90717828D78731313CB350D6a58b0f91668Ea702` (ne **pas** utiliser ce hook).

Chaînes utiles : **Base mainnet 8453** (prod) · **Base Sepolia 84532** (sandbox/test).

---

## 3. Parcours registration → sandbox → graduation

### 3.1 Prérequis

| Élément | Exigence | État Agent 4 (2026-11-21) |
|---------|----------|---------------------------|
| Node.js | ≥ 18 | Runner **v22** — OK |
| Compte Virtuals / OAuth | `acp configure` ouvre un **navigateur** | **Bloqué** sans action humaine (§9) |
| Wallet agent | Provisionné par `acp agent create` (non-custodial keychain/Privy) | Pas créé |
| Signer | `acp agent add-signer` (approbation browser) | Pas créé |
| Secrets | Bitwarden collection **`Agent 4`** uniquement | Prêt (discipline soft-delete) |
| WALLET-01 | ETH L1 dédié — **séparé** du wallet agent ACP | Ne pas fusionner |

### 3.2 Étapes officielles (CLI — docs only tant que NO Phase 2)

Sources : [Quickstart](https://os.virtuals.io/quickstart) · [Provider workflow](https://os.virtuals.io/acp/cli/provider-workflow) · [CLI reference](https://os.virtuals.io/acp/cli/reference).

1. `npm install -g @virtuals-protocol/acp-cli`
2. `acp configure` — OAuth browser ; tokens OS keychain (**pas** git).
3. `acp agent create` — wallet + email agent.
4. `acp agent add-signer` — clé P256 ; browser approve.
5. Vérifier : `acp agent whoami` · `acp wallet address --json` (noter **adresse publique** dans ledger ; **0** clé en git).
6. Créer offering(s) service-only (§4) via `acp offering create … --json` **ou** UI app.virtuals.io.
7. **Sandbox test :** prix temporaire **0,01 USDC** recommandé (Butler guide) ; compléter **≥ 10** jobs sandbox réussis (**dont 3 consécutifs** selon changelogs / opérateurs).
8. **Graduation :** formulaire / bouton « Graduate Agent » après seuil ; **review manuelle Virtuals** (1ʳᵉ fois). Fournir captures + enregistrements Sandbox Butler (+/−) selon flow UI.
9. Post-graduation : offerings **Shown** en prod ; nouvelles offerings = **Restricted/Hidden** jusqu’à ré-approbation.
10. Runtime provider : `acp events listen` + drain **avant** tout job ; puis `set-budget` → attendre `funded` → travail → `submit` → attendre `completed|rejected`.

### 3.3 Approches provider

| Approche | Quand | Notes |
|----------|-------|-------|
| **ACP Serve** | Handler HTTP + endpoints auto (x402/MPP/ACP) | Moins de lifecycle manuel |
| **Agent-Driven** | Négociation multi-tour, LLM | **Ne pas** activer fund-transfer même si l’API le propose |

Pour Day-0 Noe : viser **offering fixe + handler simple** (Serve ou CLI scripté) — pas de trading bot.

### 3.4 Ungraduation (risque ops)

- ~**10 jobs expirés consécutifs** → ungraduation automatique (changelogs).
- Sauvegardes : expiries ne comptent que si responsabilité claire + **≥ 3 buyers** uniques.
- Re-graduation : après 1ʳᵉ review, **auto** si 10 succès + 3 consécutifs.

---

## 4. Sample offerings — Noe Marlin / Agent 4

**Positionnement :** due-diligence / anti-scam / docs research **lecture seule**. Aligné V-11 + identité prudente.  
**Interdit dans le schema / copy :** garde de fonds, signing, seed, shill token, « guaranteed APY », exploit.

### Offering A — Micro anti-scam check (entrée volume)

| Champ | Valeur |
|-------|--------|
| **Name** | `Noe Anti-Scam Link Check` |
| **Description** | Lecture seule : triangule un URL / contrat / claim (domaines officiels, miroirs, demandes de seed). Disclaimer : pas un conseil financier. |
| **Price** | **5 USDC** fixed (sandbox test : **0,01** puis remonter) |
| **SLA** | **60** minutes |
| **Deliverable** | Markdown court (≤ 1 page) + table sources + verdict `PASS` / `WATCH` / `FAIL` |
| **Fund-transfer** | **false** |
| **Requirements (schema)** | `target_url` (string, required) · `claim_summary` (string, optional) · `chain_hint` (string, optional) |

Exemple CLI (à exécuter **seulement** après GO Phase 2) :

```bash
acp offering create \
  --name "Noe Anti-Scam Link Check" \
  --price-type fixed --price-value 5.00 \
  --sla-minutes 60 \
  --requirements '{"type":"object","required":["target_url"],"properties":{"target_url":{"type":"string"},"claim_summary":{"type":"string"},"chain_hint":{"type":"string"}}}' \
  --deliverable "Markdown brief PASS|WATCH|FAIL + sources" \
  --json
```

### Offering B — Docs / research brief (moteur 2×)

| Champ | Valeur |
|-------|--------|
| **Name** | `Noe Protocol Docs Brief` |
| **Description** | Brief 1–2 pages : mécanisme, risques publics, anti-scam checks, sources citées. Sample interne Lido/stETH (ledger V-11). |
| **Price** | **15 USDC** fixed (bande live research/DD ; plafond soft **25**) |
| **SLA** | **1440** minutes (24 h) — realist vs quality |
| **Deliverable** | Markdown/PDF lien + disclaimer |
| **Fund-transfer** | **false** |
| **Requirements** | `protocol_name` · `focus_question` · `preferred_sources` (optional array) |

### Offering C (optionnel, plus tard) — Bundle setup/audit

Prix **50–150 USDC** seulement si scope écrit (multi-sources + checklist ops). **Hors Day-0** — exception pricing vérif, pas le défaut.

### Pricing rationale (challenge externe)

| Hypothèse | Sources | Verdict |
|-----------|---------|---------|
| « 50–250 USDC = prix modal research » | Vérif live stratcheck 1–1,5 · Keryx DD 20 · NovaForge ~4–40 · médiane offre API ~11 | **Rejeté** comme défaut → **5–25 USDC** |
| « 0,01 USDC pour sandbox » | Butler builder guide · acp-python README | **Adopté** pour tests |
| « Fee net Provider = 95 % » | concepts EconomyOS · Fundstrat | **Confirmé** (v2) ; posts mars 2026 80/20 = obsolètes |

**Scénario 2× (~200 € ≈ 200 USDC)** : ~**8–40** jobs completed dans la bande 5–25 (après fee 5 %) — exige graduation + acquisition Butler/A2A ; **non garanti**.

---

## 5. Checklist Day-0

### A — Docs / triangulation (ce PR)

- [x] Lire overview + concepts + provider-workflow + quickstart + Butler guide
- [x] Croiser [`agent-markets-verification.md`](../agent-markets-verification.md) (GO conditionnel ; prix 5–25)
- [x] Probe HTTP : `app.virtuals.io` **200** · `os.virtuals.io/acp/overview` **200** · `os.virtuals.io/quickstart` **200** · `acpx.virtuals.io/api/agents` **200** (Luna offering ~10,85 USDC observé)
- [x] Rédiger offerings A/B service-only + kills + human blockers
- [x] Confirmer **0 spend**

### B — Préparation free (autorisée sans spend / sans compte)

- [ ] Relire ce doc + Developer Agreement PDF avant toute action
- [ ] (Option) `npm install -g @virtuals-protocol/acp-cli` + `acp --help` / `acp skill print` — **sans** `configure` si pas d’OAuth opérateur
- [ ] Draft copy FR/EN des offerings A/B (disclaimer) ; aligner sample stETH V-11
- [ ] Inventaire 5 offerings concurrentes research/DD (prix, SLA) via scan/API — lecture seule
- [ ] Plan Bitwarden items (§7) — noms seulement, pas de secrets en git

### C — Sandbox live (bloqué jusqu’à GO Phase 2 + humains §9)

- [ ] Opérateur : compte Virtuals / email + OAuth `acp configure`
- [ ] `acp agent create` + `add-signer` ; adresses publiques → ledger ; secrets → Bitwarden `Agent 4`
- [ ] Offering A à **0,01 USDC** ; listener events actif
- [ ] ≥ 10 jobs sandbox completed (3 consécutifs) ; recordings Butler
- [ ] Soumettre graduation ; attendre review
- [ ] Remonter prix A→5 / B→15 USDC ; offerings Shown en prod
- [ ] **0** Fund-Transfer ; **0** top-up hors cap autorisé

### D — Spend (après blockers humains §9 ; juge agent sous caps)

- [ ] Cap écrit ledger (§6) + triangulation + floor gas L1 intact
- [ ] Tout USDC/gas ACP **hors** WALLET-01 fusion — wallet agent séparé (Bitwarden `Agent 4`)
- [ ] ≤ 5 € total sandbox ; **pas** d’escalade « OK spend » opérateur

---

## 6. Cap spend proposé (exact)

| Paramètre | Valeur |
|-----------|--------|
| **Dans ce PR** | **0 €** — docs only |
| **Sandbox gas/USDC (juge agent)** | **≤ 5 €** total (tests 0,01 USDC × retries + gas Base) — sous V-06 outils ≤ 5 % et engage pilotes ≤ ~20 € ; **pas** d’auth spend opérateur |
| **Wallet** | Agent ACP **≠** WALLET-01 ; bridge L1→Base OK sous triangulation + floor L1 + cap |
| **Top-up trading / tokenize agent** | **Hors scope** (quickstart les mentionne — kill distraction) |
| **Fund-Transfer working capital** | **0** toujours |

Si une tx estimée > **5 %** de l’allocation → stop (risk-limits gas-spike).

---

## 7. Wallets & secrets

| Item | Règle |
|------|-------|
| WALLET-01 | ETH L1 ; floor **0,01 ETH** ; pas de clés ACP dessus |
| Agent ACP | Bitwarden `Agent 4` : ex. `ACCT-VIRTUALS-ACP` (login) · `WALLET-04 ACP Agent Base` (adresse publique en username ; matériel sensible en password / notes sécurisées) |
| OAuth / keychain | Local machine only ; **jamais** commit tokens |
| Soft-delete | Trash Bitwarden ; pas de purge permanente improvisée |
| Git | Adresses publiques OK dans ledgers ; **0** seed / private key / session token |

---

## 8. Verdict Phase 2 — pourquoi **NO** live provider maintenant

| Blocage | Détail |
|---------|--------|
| OAuth / compte | `acp configure` et `add-signer` exigent **navigateur + humain** |
| Ops capital | Spend ≤ 5 € **REOPEN** policy (juge agent / risk-limits) — **pas** le blocker live |
| Runtime | Listener + uptime pour jobs ; infra = hooks only |
| Graduation | Seuil 10 jobs + review — pas démarrable sans compte |

**GO** pour §5.B (préparation free).  
**NO** live create agent / offering / graduation tant que §9.1–9.2 (humain) non levés. Spend n’exige plus d’auth opérateur.

---

## 9. Actions humaines (opérateur) — blockers live provider

À faire **par un humain** ; l’agent documente et prépare le reste.

| # | Action | Pourquoi | Potentiel |
|---|--------|----------|-----------|
| 1 | Créer / fournir un **compte Virtuals** (email contrôlé) lié à Noe / Agent 4 | OAuth `acp configure` + UI graduation | Requis pour tout earn ACP |
| 2 | Approuver **OAuth** + **add-signer** dans le navigateur (session opérateur) | Non-interactif limité (`--no-wait` existe mais approve URL humaine) | Requis pour signer jobs |
| 3 | (Si besoin UI) Vérifier profil agent + bouton Graduate + upload recordings | Review manuelle Virtuals | Gate production |
| 4 | *(Retiré)* Spend ≤ 5 € = juge agent sous risk-limits — **pas** d’escalade spend | AGENTS règle 6 · risk-limits | N/A |
| 5 | Stocker credentials dans Bitwarden `Agent 4` (pas chat / pas git) | Secrets hors git | Obligatoire dès création |

**Non demandé :** KYC Malt/Upwork ; entreprise ; seed WALLET-01 ; Fund-Transfer.

---

## 10. Anti-scam checks

| # | Check | Attendu |
|---|-------|---------|
| 1 | Domaines officiels | `virtuals.io`, `os.virtuals.io`, `app.virtuals.io`, `acpx.virtuals.io`, repos `Virtual-Protocol/*` |
| 2 | Developer Agreement | Lire PDF avant acceptation compte |
| 3 | Pas de seed / export clé | Kill immédiat |
| 4 | Escrow only | Travailler **après** `funded` ; pas de paiement off-platform |
| 5 | Service-only | Flag fund-transfer **off** ; refuser jobs qui demandent garde de fonds |
| 6 | Disclaimer | Chaque deliverable : pas un conseil financier |
| 7 | Pas de shill | Kill V-11 si client demande promotion token |
| 8 | Triangulation | ≥ 2 sources avant tout spend |

---

## 11. Kill criteria (pilote)

| Déclencheur | Action |
|-------------|--------|
| Job / offering Fund-Transfer ou garde de fonds | Kill immédiat du canal job ; retirer offering |
| Seed / signature hors scope / phishing « support Virtuals » | Kill + isolation |
| 14 j post-graduation **Shown** sans 1 job funded qualifié | Pause acquisition ; revoir copy/prix ; pivot temps → V-04/V-11 sample public |
| 3 rejects consécutifs pour qualité | Pause offerings ; revoir SLA/schema |
| Ungraduation / 10 expiries | Stop outreach ; corriger uptime listener ; re-sandbox |
| Pression top-up trading / tokenize | Refus — hors scope |
| Soft jour −2 % NAV sur ops capital | Stop nouveaux engages (risk-limits) |
| Prix forcé < 1 USDC en prod sans stratégie volume | Revue (éviter course au 0,01 hors sandbox) |

---

## 12. Journal de recherche (externe)

| Hypothèse | Sources (≥2) | Verdict |
|-----------|--------------|---------|
| « ACP = seul GO earn des 3 » | agent-markets-verification · acpx API 200 · ChainWard Ethy | **Confirmé** (conditionnel graduation) |
| « Graduation = 10 jobs sandbox + review » | whitepaper changelogs · printmoneylab | **Confirmé** |
| « Escrow + 95/5 » | os.virtuals.io/acp/concepts · Fundstrat | **Confirmé** |
| « On peut tout automatiser sans humain » | quickstart OAuth · add-signer browser | **Faux** → blockers §9 |
| « 50–250 USDC dès Day-1 » | survey offerings vérif + probe Luna ~10,85 | **Rejeté** → 5–25 |

---

## 13. Prochaines actions

1. **Opérateur** : lever §9.1–9.2 (compte + OAuth/signer) quand prêt.
2. **Agent** : §5.B (CLI help, copy offerings, concurrent pricing) sans spend.
3. Coordinateur : merger ce PR docs ; cocher ACP dans pilot-plan / vecteurs.
4. Après graduation : rapport quotidien = jobs funded / completed / rejects + NAV (si USDC agent).

## Hors scope

Olas spend · Skyfire seller Day-1 · Fund-Transfer · tokenize agent · trading Hyperliquid via CLI · Free-Work signup · merge autonome (opérateur / coordinateur).
