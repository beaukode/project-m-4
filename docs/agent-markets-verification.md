# Vérification claims — Olas Mech / Virtuals ACP / Skyfire

**Date :** 2026-11-21 · **0 spend** · **0 KYC** · secrets hors git.  
**Objectif :** falsifier ou confirmer chaque claim du brief GO, puis juger la **viabilité earn** pour Agent 4 (2× ~200 € / 30 j).  
**Méthode :** docs + UI/API live + ≥ 2 sources indépendantes avant `CONFIRMED` ; chiffres marketing traités comme non fiables jusqu’à triangulation.

**Sources primaires (probes 2026-11-21) :**  
olas.network/{mech-marketplace,agent-economies/mech,blog/…} · stack.olas.network · build.olas.network · theagenteconomy.si · rnwy.com · app.virtuals.io/acp/scan · acpx.virtuals.io/api · os.virtuals.io · fundstrat PDF · docs.skyfire.xyz · api.skyfire.xyz/directory/services · docs.apify.com/integrations/skyfire · akamai.com blog.

**Réf. :** [`agent-markets.md`](agent-markets.md) (corrigé après cette revue) · [`pilots/olas-mech.md`](pilots/olas-mech.md).

---

## Synthèse exécutive

| Canal | Verdict claims (global) | Viabilité 2×~200 € / 30 j | Survive scrutiny ? |
|-------|-------------------------|---------------------------|--------------------|
| **Olas Mech** | Mécanique **CONFIRMÉE** ; earn individuel **surestimé** | **MARGINAL** | **Partiel** — marché live mais demande = Predict + concentration + ~34 $/j de turnover récent |
| **Virtuals ACP** | Rails **CONFIRMÉS** ; pricing 50–250 **trop optimiste** | **MARGINAL → viable conditionnel** | **Oui, le mieux des 3** — revenus réels on-chain, mais graduation + acquisition jobs |
| **Skyfire seller** | Rails **CONFIRMÉS** ; trafic payant nouvel entrant **non prouvé** | **NOT VIABLE** (earn primaire) | **Non** comme bazaar earn — **oui** comme rail de paiement optionnel |

**Ordre révisé :** Virtuals ACP (provider, service-only) ≫ Olas Mech (docs/dry-run seulement) ≫ Skyfire seller (veille rail, pas Day-1 earn).

---

## 1. Olas Mech Marketplace

### 1.1 Claims → scores

| # | Claim | Score | Preuves (≥2 si CONFIRMED) | Note critique |
|---|-------|-------|---------------------------|---------------|
| O1 | Deploy Mech permissionless ; d’autres agents paient des tools | **CONFIRMED** | Blog KYA (« Anyone can run a Mech… ») · stack.olas.network/mech-server · build.olas.network/monetize | Olas **ne revue pas** les Mechs |
| O2 | Escrow / balance on-chain ; ~15 % DAO fee au withdraw | **CONFIRMED** | Blog 20M tx + Q2 2026 + homepage (15 %) · theagenteconomy.si (balance tracker + % DAO ; % exact non chiffré chez eux — croisé blog) | Fee live depuis ~15-juin-2026 ; fees $1 044,59 = sous-ensemble de tokens/chaînes |
| O3 | Turnover ~$111 k encore exact / significatif | **PARTIAL** | Page marketplace + Mech economy : **$111 215** (21-nov-2026) · blog août : $107 809 | Exact **oui**. « Significatif » **faible** : +~$3,4 k en ~99 j ≈ **~$34 / jour** gross marketplace ; A2A millions ≠ $ |
| O4 | Micropaiements peuvent agréger ~200 € / 30 j pour outil niche | **PARTIAL → FALSE** pour nouvel entrant typique | RNWY : ~$0,01 / job Gnosis ; top mech #2182 ~$3 714 / 371 k jobs · Demand : **~97 %** requests = Predict (11,9 M / 12,3 M) · **13** DAA Mechs | À 0,01 $/job → **20 000** jobs pour 200 $ ; volume récent total marché << besoin unilatéral ; niche hors Predict = « Other » ~260 k lifetime seulement |
| O5 | Docker + gas Gnosis ≤ 5 € = entrée réaliste | **PARTIAL** | Docs : Docker **obligatoire** · quickstart gas historique ~0,05 xDAI · DNS Valory top mech résout | Gas **oui ≪ 5 €**. Entrée **bloquée** sans Docker/bridge (déjà pilote). Claims « stake OLAS obligatoire » (chenecosystem) **non corroborés** par docs officielles setup |

### 1.2 Providers / Mechs live (échantillon)

| Proxy | Observation | Source |
|-------|-------------|--------|
| DAA Mechs | **13** (moy. 7 j) | olas.network/agent-economies/mech |
| Task requests / deliveries | **12,32 M** / **10,37 M** all-time | idem |
| Origine demande | Predict **11,92 M** · Agents.fun 105 k · Contribute 34 k · Other 260 k | idem |
| Top Mechs (docs mech-client) | Id **2182** `0xc05e…632c` Fixed Native, **41 246+** deliveries (échantillon docs) ; **2235**, **2198**, … | stack.olas.network/mech-client |
| Opérateur Valory | DNS `c05e…632c-100.mech.valory.xyz` → **34.147.134.129** (probe 21-nov) | dig + docs Valory |
| RNWY (indep., mars 2026) | Mech gnosis/2182 : 371 k+ jobs, 245 clients, **$3 713,92** earned, ~$0,01/job | rnwy.com/learn/olas-mech-marketplace-agent-data |
| Concentration (tierce, moins fiable) | « Service 3 ~99 % deliveries » | chenecosystem — **à traiter comme hypothèse**, pas CONFIRMED |

**Concentration :** la demande est **dominée par Predict** et un petit set de Mechs (souvent Valory). Un nouvel outil anti-scam hors boucle Predict n’hérite **pas** du turnover affiché.

### 1.3 Preuves d’earnings

| Type | Chiffre | Interprétation |
|------|---------|----------------|
| Marketing / dashboard Olas | Task payments **$111 215** ; claimed / realised **$103 914** | Lifetime **gross** ; net mech après fee ; **pas** revenu d’un nouvel entrant |
| Fees protocole | **$1 044,59** depuis fee live (sous-ensemble tokens) | Corrobore qu’il y a eu des claims post-juin, pas le volume total |
| Indépendant RNWY | Top Mech ~**$3,7 k** lifetime à ~1 ¢/job | Earnings **réels** mais concentrés + long runway |
| Croissance récente | ~$34 / j marketplace | Même **100 %** de part de marché = ~1 000 $/mois total — impossible d’y prendre 200 €/mois sans cannibaliser Predict |

### 1.4 Viabilité Agent 4

**MARGINAL.** Canal **réel** et permissionless, mais (1) earn = micropaiements Predict-captifs, (2) concentration opérateurs historiques, (3) infra Docker/bridge bloquée, (4) 15 % au claim.  
**GO docs / dry-run** reste OK ; **GO earn 30 j** = non sans preuve de demande pour *notre* outil.

---

## 2. Virtuals ACP

### 2.1 Claims → scores

| # | Claim | Score | Preuves | Note critique |
|---|-------|-------|---------|---------------|
| V1 | Rôle Provider + escrow USDC job + split ~95/5 | **CONFIRMED** | os.virtuals.io/acp/concepts · Fundstrat Q2 2026 · theagenteconomy.si | Avec evaluator : 90/5/5 |
| V2 | Sandbox → graduation obligatoire | **CONFIRMED** | ACP changelogs (10 jobs sandbox + 3 consécutifs + review manuelle initiale) · printmoneylab (opérateur indépendant) · overview « 18 months / 2000+ » | Re-graduation auto possible après 1ère review |
| V3 | Briefs 50–250 USDC = pricing réaliste vs live | **PARTIAL** | Live : stratcheck **1–1,5** · NovaForge **4–40** · Keryx DD **20** / bootstrap **50** · GhOsT77 security **164–1 099** · API top agents : médiane offre échantillon **~$11**, peu d’offres ≥ 50 | **50–250 existe** (niche setup/security) mais **n’est pas le mode** pour research/DD automatisé ; modal ≈ **0,5–5 USDC** |
| V4 | Job type Fund-Transfer existe ; à éviter | **CONFIRMED** | concepts + provider-workflow + overview (Fund Transfer hook `0x9071…`) | Aligné kill AGENTS / V-12 |
| V5 | Scale prod (>2000 agents, etc.) | **PARTIAL** | Docs : « >2000 agents » / 18 mois · Scan UI : **2,55 M** jobs, **$4,53 M** revenue, **$481 M** aGDP · API `acpx` : **44 223** agents paginés | « 2000+ » = claim vendor. Scale **jobs/revenue** confirmé par UI. **aGDP ≠ revenue** (ChainWard / Ethy : $218 M aGDP vs **$573 k** fees) |

### 2.2 Providers / offerings live (échantillon 21-nov-2026)

**Dashboard** `app.virtuals.io/acp/scan` : aGDP 481,82 M · Revenue **4,53 M** · Jobs **2,55 M** · Wallets actifs uniques 36,73 k.

**Top revenue (API `acpx.virtuals.io`, sort=revenue:desc) :**

| Agent | Revenue (API) | Jobs réussis | Buyers uniques | Gradué |
|-------|---------------|--------------|----------------|--------|
| Luna | $700 385 | 40 160 | 376 | false* |
| Ethy AI | $572 787 | 1 139 030 | 7 496 | true |
| Director Lucien | $262 537 | 59 488 | 405 | true |
| Capminal | $121 195 | 12 769 | 1 459 | true |
| Finwizz | $119 354 | 4 129 | 139 | — |
| WhaleIntel | $114 974 | 39 069 | 980 | true |

\* champ `hasGraduated` API parfois inconsistant avec présence marketplace — ne pas sur-interpréter un bool seul.

**Offerings UI (scan/offerings) — prix observés :** stratcheck_ai 1,00–1,50 · Stream Presence 0,01–5,00 · NovaForge / Artificium scraping **25–40** · research NovaForge ~4 · Keryx bootstrap **50** · GhOsT77 security **~164–1 099**.

**Concentration :** jobs massifs = agents **trading / swap / intel** (Ethy, Otto, Axelrod…). Les revenus service-only « research report » existent mais sont **d’un autre ordre** que le leaderboard trading.

### 2.3 Preuves d’earnings

| Source | Nature | Verdict |
|--------|--------|---------|
| Scan Virtuals | Revenue agrégé **$4,53 M** | Vendor dashboard — cohérent avec API agents |
| acpx API | Revenus par agent (Ethy ~$573 k, etc.) | Machine-readable ; ChainWard a vérifié Ethy on-chain (avr. 2026) |
| ChainWard | aGDP vs revenue ; Ethy fees ~$573 k | Indépendant — **confirme** que le marketing aGDP gonfle |
| printmoneylab | Graduation douloureuse ; split historique 80/20 dans un post mars 2026 | Expérience opérateur ; **split actuel = 95/5** (docs v2) — post partiellement obsolète sur les fees |

**Nouvel entrant :** possible **si** graduation + offre différenciée + buyers (Butler / A2A). Pas de garantie 1–3 jobs à 50–250 USDC ; scénario réaliste = **plusieurs jobs à 1–20 USDC** ou 1 job setup/security cher.

### 2.4 Viabilité Agent 4

**MARGINAL → VIABLE conditionnel.** Meilleur des 3 pour earn service-only : escrow USDC réel, preuves de payout, SDK/CLI. Freins : graduation manuelle, compte app, concurrence prix bas, **interdire Fund-Transfer**.  
Prix cible révisé pour V-11 : **5–25 USDC** (aligné live) ; 50–250 seulement si bundle setup/audit justifié.

---

## 3. Skyfire (seller directory)

### 3.1 Claims → scores

| # | Claim | Score | Preuves | Note critique |
|---|-------|-------|---------|---------------|
| S1 | Directory seller + MCP/OpenAPI + tokens pay / kya-pay | **CONFIRMED** | docs seller-services + service-discovery · API directory **84** services live · types API/MCP/… | Probe `GET https://api.skyfire.xyz/api/v1/directory/services` → 200 |
| S2 | Review seller ~48 h | **PARTIAL** | docs.skyfire.xyz uniquement (« typically takes 48 hours ») | Pas de 2ᵉ source indépendante sur le délai |
| S3 | Modèle micropaiement ; partenaires crédibles | **PARTIAL** | Directory : médiane prix **≪ 0,05 $** ; max listé ~**6,50 $** (BuildShip Veo3) · Apify **présent** (MCP, price 0 CUSTOM) · BuildShip **22** listings · Akamai blog 2,5 M tx | Partenaires **oui**. 2,5 M Akamai = transactions **KYA** (identité) chez un data provider — **≠** revenus sellers directory |
| S4 | Un nouveau seller peut obtenir du trafic payant | **UNKNOWN → probablement FALSE à court terme** | Aucun dashboard public d’earnings seller indie · Directory rempli de tests (QR $0,000001, « TestSvc », etc.) · Apify docs = agents **achètent** chez Apify, pas l’inverse | Listing ≠ demande. Pas de preuve qu’un MCP niche « anti-scam » soit découvert/payé |

### 3.2 Providers / services live (probe API)

- **84** services actifs ; **~** dizaines de sellers uniques.  
- Types : API **63** · MCP remote **8** · reste WEB/Fetch/domain.  
- Exemples nominatifs : **Apify**, **BuildShip** (multi-outils 0,02–6,50 $), **Suede AI** (0,15–4,99 $), **x402node** (risk/TVL ~0,008–0,012 $), **StableInvoice** (0,10 $), nombreux micro-services génériques.  
- Forter / Sophtron : cités BusinessWire comme partenaires **merchant/trust**, **pas** trouvés comme sellers directory dans le probe.

### 3.3 Preuves d’earnings

| Source | Ce que ça prouve | Ce que ça ne prouve pas |
|--------|------------------|-------------------------|
| Akamai × Skyfire (nov. 2026) | KYA utilisé à l’échelle (2,5 M tx) | Paiements à des **nouveaux** sellers MCP |
| Apify docs Skyfire | Apify encaisse des PAY tokens agents | Qu’Agent 4 encaisse |
| Directory public | Offre côté supply existe | Volume charge/settlement par seller |

### 3.4 Viabilité Agent 4

**NOT VIABLE** comme canal earn primaire 30 j.  
**WATCH** comme **rail** (si un jour un backend MCP est exposé et qu’un buyer canal existe). Review 48 h + hébergement = friction sans ROI prouvé.

---

## 4. Table consolidée scores + verdicts

| Plateforme | Claims confirmés | Claims partiels / faux | Overall earn | Ancien verdict shortlist | **Verdict révisé** |
|------------|------------------|------------------------|--------------|-------------------------|--------------------|
| Olas Mech | O1, O2 | O3 (exact mais peu de flux récent), O4 (agrégation niche), O5 (gas oui / ops non) | **MARGINAL** | GO | **WATCH** (earn) · GO docs only |
| Virtuals ACP | V1, V2, V4 | V3 (prix), V5 (scale marketing vs aGDP) | **MARGINAL / viable si graduation** | GO | **GO** (conservateur) |
| Skyfire seller | S1 | S2, S3 ; S4 UNKNOWN | **NOT VIABLE** | GO | **WATCH** |

---

## 5. Corrections appliquées à `agent-markets.md`

Voir historique dans ce fichier + patch `agent-markets.md` (même date) :

1. Olas : fit **abaissé** ; turnover contextualisé (croissance lente, Predict-dominant, 13 DAA) ; verdict earn → **WATCH**.  
2. Virtuals : fourchette prix **5–25 USDC** (50–250 = exception) ; aGDP ≠ revenue ; garder **GO**.  
3. Skyfire : verdict → **WATCH** ; Akamai = KYA pas seller P&L ; pas de preuve trafic nouvel entrant.  
4. Ordre top : **ACP → Olas (docs) → Skyfire (rail)**.

---

## 6. Implications ops (sans spend)

1. **Prioriser Virtuals ACP sandbox** (offre service-only lecture seule, prix 5–25 USDC) — docs only jusqu’à auth.  
2. **Olas** : poursuivre checklist dry-run pilote ; ne pas attendre 200 €/30 j du turnover $111 k.  
3. **Skyfire** : ne pas ouvrir seller tant que pas de canal d’acquisition buyer identifié.  
4. Tuer toute offre **Fund-Transfer** ACP.  
5. Re-probe mensuel : directory Skyfire earnings si dashboard public ; subgraph Mechs si indexeur stable ; acpx top revenue.

---

## 7. Journal de triangulation

| Hypothèse brief GO | Verdict | Pourquoi |
|--------------------|---------|----------|
| « Les 3 GO ont un earn path 200 €/30 j plausible » | **Fausse** telle quelle | Seul ACP a des payouts service crédibles ; Olas/Skyfire surestimés pour nouvel entrant |
| « $111 k Olas = marché liquide pour niche » | **Fausse** | Predict ~97 % ; ~$34/j récent |
| « 50–250 USDC = prix marché ACP research » | **Partielle** | Existe mais hors mode ; modal ≪ 10 $ |
| « Skyfire partenaires = trafic seller » | **Non établi** | Partenaires = KYA/commerce ; directory ≠ earnings |
| « Escrow + fees Olas/ACP documentés » | **Vraie** | Docs + independants |
