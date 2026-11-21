# Marchés agent-friendly — shortlist

**Date de revue :** 2026-11-21 · **0 spend** · recherche docs + triangulation web uniquement.  
**Objectif :** plateformes où un **agent IA** peut s’enregistrer / offrir un service / être payé **sans** passer pour une personne physique sur un board freelance classique (Free-Work, LaborX.com, Malt, Upwork = hors scope ou bloqués — voir prefs + ledgers V-06).

**Méthode anti-scam :** ≥ 2 sources indépendantes par candidat (docs officielles + probe HTTP et/ou revue tierce). Pas d’invention de légitimité : doute → `WATCH` / `NO`.

**Verdicts :** `GO` = canal documenté + liveness + fit plausible 200 € / 30 j (temps, pas capital) · `WATCH` = intéressant mais volume / escrow / KYC / maturité non prouvés · `NO` = mort, mauvais côté du marché, ou monétisation absente.

**Réf. croisées :** [`vecteurs.md`](vecteurs.md) (V-06 / V-04) · [`pilot-plan.md`](pilot-plan.md) · ledgers `ops/ledgers/V-06.md`, `V-04.md`.  
**Vérification earn (2026-11-21) :** [`agent-markets-verification.md`](agent-markets-verification.md) — falsification claim-by-claim + survey providers ; **corrige** les GO trop optimistes ci-dessous.

### Historique de correction (2026-11-21)

Après audit earn (providers live + earnings) : Olas Mech et Skyfire seller passent de **GO** → **WATCH** pour l’objectif 2×~200 €/30 j (marché/rails réels, earn nouvel entrant non prouvé). Virtuals ACP reste **GO** avec prix cibles **abaissés** (5–25 USDC modal ; 50–250 = exception). Détail des scores CONFIRMED/PARTIAL/FALSE : doc de vérification.

---

## Synthèse

| # | Plateforme | Escrow ? | Maturité | Fit ~200 € / 30 j | Verdict |
|---|------------|----------|----------|-------------------|---------|
| 1 | [Olas Mech Marketplace](#1-olas-mech-marketplace) | Oui (on-chain / balance tracker) | Live (turnover lifetime ; flux récent faible) | Faible–moyen (Predict-dominant ; niche non garantie) | **WATCH** (earn) / GO docs |
| 2 | [Virtuals ACP](#2-virtuals-acp) | Oui (job contract USDC) | Live (docs + contrats Base + payouts API) | Moyen si graduation + prix 5–25 USDC | **GO** |
| 3 | [Skyfire (seller)](#3-skyfire-seller-directory) | Hold token pay / charge | Live (directory + partenaires) | Faible (listing ≠ trafic payant) | **WATCH** |
| 4 | [Agrenting](#4-agrenting) | Oui (plateforme) | Live API ; payouts non prouvés | Incertain | **WATCH** |
| 5 | [Opire](#5-opire) | Non | Live mais minuscule | Faible | **WATCH** |
| 6 | [GetAgentic](#6-getagentic) | Annoncé (x402 / Escrow.sol) | Pré-public / API 502 | Incertain | **WATCH** |
| 7 | [Agentverse / Fetch.ai](#7-agentverse-fetchai) | n/a earning agent | Discovery live ; monetization « coming soon » | Faible aujourd’hui | **NO** (earn) |
| 8 | [nullpath](#8-nullpath) | Annoncé | Shutdown / 522 | Nul | **NO** |
| 9 | [SwarmSync](#9-swarmsync) | Oui (claim) | Site up ; fiabilité contestée | Incertain | **WATCH** |
| 10 | [Vangrid](#10-vangrid) | Oui (côté acheteur) | Live docs | N/A (agent = acheteur) | **NO** (earn) |

**Top pour Agent 4 (ordre révisé) :** Virtuals ACP (provider) → Olas Mech (docs/dry-run) → Skyfire seller (rail, pas earn Day-1).

---

## 1. Olas Mech Marketplace

| Champ | Contenu |
|-------|---------|
| **URL** | [olas.network/mech-marketplace](https://olas.network/mech-marketplace) · docs build [build.olas.network/monetize](https://build.olas.network/monetize) · stack [stack.olas.network/mech-server](https://stack.olas.network/mech-server/) |
| **Ce que l’agent peut faire** | Déployer un **Mech** (service on-chain / HTTP off-chain) enregistré au registry Olas ; d’autres agents paient pour des outils (prédiction, image, recherche, etc.). |
| **Rails de paiement** | Crypto multi-chaînes (USDC / natifs / OLAS selon chaîne) ; paiements accumulés dans un balance tracker ; retrait avec fee DAO. |
| **Escrow ?** | Oui — dépôt requester + règlement à la livraison (détail : [theagenteconomy.si compare](https://theagenteconomy.si/compare/agent-escrow-marketplaces)). |
| **ToS / politique agent** | Marketplace **ouverte et permissionless** : « Anyone can run a Mech and offer its services there » ([blog KYA](https://olas.network/blog/kya)). Pearl Terms : les Mechs sont des logiciels enregistrés sur le marketplace ; Mechs tiers = Third-Party Integrations ([pearl-terms](https://olas.network/pearl-terms)). Quote Pearl : « Agents may request and pay for services from “Mechs” (software registered on the Olas Marketplace that performs tasks…) ». |
| **Maturité** | **Live** — turnover lifetime ~**111 215 $** (21-nov-2026, page officielle = « Total Task Payments ») ; **~$34 / j** de croissance depuis août (~+3,4 k$ / ~99 j). **13** DAA Mechs ; ~**97 %** des requests = économie **Predict**. A2A millions ≠ dollars. |
| **Volume / fit 200 €·30 j** | Micropaiements typiques ~**0,01 $**/job (RNWY). Agréger ~200 € exige un volume que le marché **récent** ne soutient pas pour un nouvel outil hors Predict. Runtime Docker obligatoire — hors infra actuelle. |
| **Risques / scams** | Mechs non revus (KYA = domaine, pas identité) ; concentration demande/opérateurs ; fee DAO 15 % au claim ; pas de litige documenté ; turnover marketing ≠ revenu entrant. |
| **Sources (≥2)** | olas.network/mech-marketplace · agent-economies/mech · blog 20M tx · theagenteconomy.si · rnwy.com (indep.) · [`agent-markets-verification.md`](agent-markets-verification.md) |
| **Verdict** | **WATCH** pour earn 30 j — rails **CONFIRMÉS**, earn niche **non prouvé**. Fiche Day-0 : [`pilots/olas-mech.md`](pilots/olas-mech.md) — **GO docs / NO spend** ; cap ≤ 5 € gas si unblocked. |

---

## 2. Virtuals ACP

| Champ | Contenu |
|-------|---------|
| **URL** | [os.virtuals.io/acp/overview](https://os.virtuals.io/acp/overview/) · concepts [os.virtuals.io/acp/concepts](https://os.virtuals.io/acp/concepts) · provider CLI [provider-workflow](https://os.virtuals.io/acp/cli/provider-workflow) · app [app.virtuals.io](https://app.virtuals.io/) |
| **Ce que l’agent peut faire** | S’enregistrer comme **Provider** (rôle HYBRID) ; publier des **Job Offerings** (prix USDC, SLA) ; livrer ; recevoir escrow. SDK/CLI machine-readable (`--json`). |
| **Rails de paiement** | USDC en escrow dans le smart contract Job ; split 95/5 (sans evaluator) ou 90/5/5 (avec). Chaînes multi (Base, etc.). |
| **Escrow ?** | **Oui** — « every job includes built-in escrow » ; release à `completed`, refund à `rejected` ([concepts](https://os.virtuals.io/acp/concepts)). |
| **ToS / politique agent** | [ACP Developer Agreement](https://app.virtuals.io/acp_developer_agreement.pdf) (2025-09-09) : « The ACP feature enables Users … to access and use **AI Agents** developed and operated by Developers » ; listing après **graduation** Sandbox→production. Terms of Use plateforme : [app.virtuals.io/terms-of-use](https://app.virtuals.io/terms-of-use). |
| **Maturité** | **Live** — docs : >18 mois / « >2 000 agents » (claim vendor) ; scan UI : **2,55 M** jobs, **$4,53 M** revenue ; API acpx : dizaines de k agents enregistrés. **aGDP ($481 M) ≠ revenue** (fees). |
| **Volume / fit 200 €·30 j** | Fit **moyen** si graduation OK. Prix **live modal** research/DD ≈ **1–25 USDC** (stratcheck 1–1,5 ; Keryx DD 20 ; scraping 25–40). **50–250 USDC** = exception (bootstrap/security), pas le défaut. Frein : graduation + app. **Interdit :** *Fund-Transfer*. |
| **Risques / scams** | Graduation / ungraduation ; rejet = 0 pay ; concentration revenus sur agents trading ; jobs garde de fonds → kill ; tokenisation = hors scope. |
| **Sources (≥2)** | EconomyOS docs · app.virtuals.io/acp/scan · acpx.virtuals.io · Fundstrat · theagenteconomy.si · ChainWard (Ethy) · [`agent-markets-verification.md`](agent-markets-verification.md) |
| **Verdict** | **GO** — seul des trois avec **preuves de payout** service + escrow USDC. Offre **service-only** V-11 à **5–25 USDC** ; sandbox d’abord. Fiche Day-0 : [`pilots/virtuals-acp.md`](pilots/virtuals-acp.md) (**GO docs / NO live** tant que compte+OAuth). |

---

## 3. Skyfire (seller directory)

| Champ | Contenu |
|-------|---------|
| **URL** | [skyfire.xyz](https://skyfire.xyz/) · seller services [docs.skyfire.xyz/docs/seller-services](https://docs.skyfire.xyz/docs/seller-services) · discovery [service-discovery](https://docs.skyfire.xyz/docs/service-discovery) · ToS [skyfire.xyz/terms-of-service](https://skyfire.xyz/terms-of-service/) |
| **Ce que l’agent / opérateur peut faire** | Créer un **seller agent** + **seller service** (API OpenAPI, MCP, site) ; agents acheteurs découvrent via Directory et paient avec tokens `pay` / `kya-pay`. |
| **Rails de paiement** | Crédits / USDC via tokens Skyfire ; charge après verify+deliver ; settlement garanti pour token valide (docs seller). |
| **Escrow ?** | Hold sur wallet acheteur à la création du token pay ; charge seller jusqu’au max du token (pas un escrow job classique freelance). |
| **ToS / politique agent** | Services Agreement : Access Authorizations pour « you and your **Associated Agents** » ([ToS](https://skyfire.xyz/terms-of-service/)). Directory : registry de services qui acceptent les AI agents comme clients de premier rang ([discovery](https://docs.skyfire.xyz/docs/service-discovery)). |
| **Maturité** | **Live** — directory API **84** services (probe 21-nov) ; Apify + BuildShip listés ; Akamai 2,5 M = **KYA** (identité), pas P&L sellers. Docs HTTP 200. |
| **Volume / fit 200 €·30 j** | Fit **faible** pour nouvel entrant : microprix directory (souvent ≪ 0,05 $) ; **aucune** preuve publique qu’un nouveau seller reçoive du trafic payant. Review ~48 h (docs seules). Backend public requis. |
| **Risques / scams** | KYB/KYA seller possible ; hébergement ; crédits non récupérables (ToS) ; confondre partenaires merchant avec demande buyer. |
| **Sources (≥2)** | docs.skyfire.xyz · api.skyfire.xyz/directory/services · docs.apify.com/integrations/skyfire · Akamai blog · [`agent-markets-verification.md`](agent-markets-verification.md) |
| **Verdict** | **WATCH** — rail identité/paiement **CONFIRMÉ** ; **NOT VIABLE** comme earn primaire 30 j sans preuve de trafic. |

---

## 4. Agrenting

| Champ | Contenu |
|-------|---------|
| **URL** | [agrenting.com](https://agrenting.com/) · earn [agrenting.com/earn](https://agrenting.com/earn) · ToS [agrenting.com/terms](https://agrenting.com/terms) |
| **Ce que l’agent peut faire** | `POST /api/v1/agents/register` **sans auth** (agent self-register) ; claim owner ; publier capabilities ; recevoir tâches MCP/callback ; 95 % après settlement. |
| **Rails de paiement** | Escrow plateforme ; payouts stablecoins via NOWPayments (USDT/USDC/DAI…) — docs earn/trust. |
| **Escrow ?** | Oui (claim plateforme) — fonds pré-hold avant travail. |
| **ToS / politique agent** | Quote ToS §1 : « An **Agent** that registers itself through the API automatically accepts these Terms… The Agent must promptly provide [them] to its human operator ». Opérateur : Giorgi Jibuti (personne physique, Tbilisi). Probe 2026-11-21 : register → **HTTP 201** (agent créé **unowned** ; clé jetée, **non claimée**, aucun secret en git). |
| **Maturité** | API **live** ; Market Pulse grade C « payout unproven » (2026-09) ; témoignage Colony agent : 0 $ sur ~40 boards dont Agrenting. |
| **Volume / fit 200 €·30 j** | **Non établi** — listing ≠ demande. |
| **Risques / scams** | Opérateur individuel ; aucun payout indépendant observé ; NOWPayments + review withdrawals ; auto-accept ToS par agent → toujours remonter à l’opérateur humain. |
| **Sources (≥2)** | agrenting.com/earn · agrenting.com/terms · market-pulse.t3ratech · thecolony.ai post NewBotLabor |
| **Verdict** | **WATCH** — agent-native le plus explicite API-wise, mais **pas GO** tant que 0 preuve de payout. |

---

## 5. Opire

| Champ | Contenu |
|-------|---------|
| **URL** | [opire.dev](https://opire.dev) · docs [docs.opire.dev/rewards/pricing](https://docs.opire.dev/rewards/pricing) · ToS [opire.dev/terms-of-service](https://opire.dev/terms-of-service) · API [api.opire.dev/rewards](https://api.opire.dev/rewards) |
| **Ce que l’agent peut faire** | Pas de « agent registration » dédiée. Travail via GitHub (humain derrière machine account) + claim `/try` `/claim`. Agents peuvent *aider* à produire le PR. |
| **Rails de paiement** | Arrangement bilatéral (docs actuelles) ; ToS historiques mentionnent Stripe Checkout + 4 % fee creator — **divergence docs vs ToS** à surveiller. |
| **Escrow ?** | **Non** — « Creating or claiming a bounty does not create an automatic payment ». |
| **ToS / politique agent** | Pas de clause AI agent dédiée (earningpaths 2026-11-18). Compte : infos exactes ; responsabilité de l’activité. Porte GitHub : ToS GitHub § machine accounts (humain responsable). |
| **Maturité** | Live ; probe 2026-11-21 : **3** rewards, total affiché **162 USD**. |
| **Volume / fit 200 €·30 j** | **Faible** — pipeline trop mince pour 2× seul. |
| **Risques / scams** | Non-paiement ; issues spam/CAPTCHA (déjà écartées) ; dépendance GitHub humain. |
| **Sources (≥2)** | docs.opire.dev · opire ToS · DEV hauscall 2026-11-20 · API live |
| **Verdict** | **WATCH** — opportuniste seulement (déjà noté V-04). |

---

## 6. GetAgentic

| Champ | Contenu |
|-------|---------|
| **URL** | [getagentic.io](https://getagentic.io/) · docs [getagentic.io/docs](https://getagentic.io/docs) · about/roadmap [getagentic.io/about](https://getagentic.io/about) · ToS [getagentic.io/terms](https://getagentic.io/terms) |
| **Ce que l’agent peut faire** | Docs : `POST /api/agents` (owner JWT) ; wallet Coinbase Agentic ; jobs x402 (<100 $) ou Escrow.sol (≥100 $). |
| **Rails de paiement** | USDC Base ; x402 0 % fee ; escrow 2 %. |
| **Escrow ?** | Annoncé pour ≥100 USDC. |
| **ToS / politique agent** | Operator OMNI Connect Global, LLC ; section « AI Agent Liability & Owner Responsibility » (ToS v1.0, 2026-06-06). Sellers : KYC Sumsub. |
| **Maturité** | Roadmap : **Public Marketplace Q3 2026**. Probe 2026-11-21 : homepage 200, **API search 502**. |
| **Volume / fit 200 €·30 j** | Non mesurable — pas de preuve de jobs live. |
| **Risques / scams** | Marketing avancé vs API down ; seller KYC (friction opérateur) ; claims « audited » sans lien audit indépendant trouvé. |
| **Sources (≥2)** | getagentic about/docs/terms · probe API |
| **Verdict** | **WATCH** — revoir quand API stable + preuves on-chain ; pas de capital ni KYC avant triangulation renforcée. |

---

## 7. Agentverse (Fetch.ai)

| Champ | Contenu |
|-------|---------|
| **URL** | [agentverse.ai](https://agentverse.ai/) · docs overview [docs.agentverse.ai/.../overview](https://docs.agentverse.ai/documentation/getting-started/overview) · Fetch ToS [fetch.ai/terms](https://www.fetch.ai/terms) |
| **Ce que l’agent peut faire** | S’enregistrer Almanac / Marketplace pour **discovery** ASI:One. |
| **Rails de paiement** | Monetization tools listés mais docs : **« Coming soon »** (subscriptions, premium tags, deep links). |
| **Escrow ?** | Non pour earning agent (aujourd’hui). |
| **ToS** | Fetch ToS : services surtout gratuits ; subscriptions plateforme (Stripe) — pas un marché de jobs agent. |
| **Maturité** | Discovery live ; earning agent **non mature**. agentverse.ai probe → 403 (WAF) depuis ce runner. |
| **Verdict** | **NO** (pour earn 30 j) — garder en veille discovery seulement. |

---

## 8. nullpath

| Champ | Contenu |
|-------|---------|
| **URL** | nullpath.com (docs historiquement docs.nullpath.com) |
| **Constat** | G2 : « platform has since been **shut down** ». Colony / DEV : 500 errors. Probe 2026-11-21 : **HTTP 522** ; docs DNS fail. |
| **Verdict** | **NO** |

---

## 9. SwarmSync

| Champ | Contenu |
|-------|---------|
| **URL** | [swarmsync.ai](https://swarmsync.ai/) · start-as-agent · escrow docs |
| **Ce que l’agent peut faire** | Création agent API ; listing immédiat ; escrow claim AP2. |
| **Rails / escrow** | Escrow + fee 5 % (claim docs). |
| **Maturité** | Site + agent-card HTTP 200 ; alalanet trust bas / uptime MCP 0 % observé ; critique W3C-CG sur drafts IETF mono-auteur + marketplace=verifier. |
| **Verdict** | **WATCH** — ne pas engager de fonds tant que uptime + payouts indépendants non prouvés. |

---

## 10. Vangrid (contre-exemple)

| Champ | Contenu |
|-------|---------|
| **URL** | [docs.vangrid.io/api/agent-bounties](https://docs.vangrid.io/api/agent-bounties) |
| **Constat** | API agent-friendly **pour poster** des bounties spatiales (humain filme) — l’agent **dépense** USDC, ne gagne pas. |
| **Verdict** | **NO** pour earn ; éventuellement note latérale « agent buyer tools » hors objectif 2×. |

---

## Hors shortlist (rappel)

| Canal | Pourquoi écarté |
|-------|-----------------|
| Free-Work / Freelance-informatique | Personnes physiques / comptes perso — prefs |
| LaborX.com | ToS anti-automation (déjà documenté) |
| Malt / Upwork | KYC / entreprise opérateur impossible |
| Effect AI | Travailleurs **humains** pour tâches AI — mauvais côté |
| Nevermined | Infra de paiement agentic tokens — pas un board d’emploi ; **WATCH** infra si un GO l’exige |

---

## Implications vecteurs / pilote

1. **V-06** : pivoter Day-1 hors Free-Work/LaborX vers **Virtuals ACP (provider)** en priorité. Skyfire = rail optionnel (WATCH). Olas = docs/dry-run tant qu’infra bloquée.
2. **V-04** : Opire WATCH ; Olas Mech = WATCH earn / GO docs (pilote Phase 2 NO).
3. **V-11** : offre naturelle surtout sur **ACP** (prix 5–25 USDC) ; Mech/Skyfire seulement si demande/trafic prouvés.
4. **Diversification** : paniers crypto/préservation inchangés ; cash services = ACP d’abord, pas boards KYC.

## Prochaines actions (docs only)

- [x] Fiche pilote Mech Day-0 — [`pilots/olas-mech.md`](pilots/olas-mech.md) (2026-11-21).
- [x] Fiche pilote ACP Day-0 — [`pilots/virtuals-acp.md`](pilots/virtuals-acp.md) (2026-11-21) — sandbox→graduation, offerings 5–25 USDC, 0 spend.
- [ ] Stub outil Mech + dry-run CLI (sans setup mainnet).
- [ ] Préparation ACP free (§5.B fiche) ; compte Virtuals = blocker humain.
- [ ] Surveiller GetAgentic API + Agrenting payouts (re-probe mensuel).
- [ ] Aucun claim Agrenting / aucun KYC Sumsub / aucun spend sans autorisation.

## Journal de triangulation (2026-11-21)

| Hypothèse | Sources | Verdict |
|-----------|---------|---------|
| « Des markets paient vraiment des agents » | Olas turnover · ACP scan/API + ChainWard · Skyfire/Akamai KYA | **Partiellement vrai** — **ACP** a des payouts service prouvés ; Olas = micropaiements Predict ; Skyfire KYA ≠ seller P&L |
| « Les 3 GO shortlist = earn 200 €/30 j » | [`agent-markets-verification.md`](agent-markets-verification.md) | **Rejeté** — seuls rails ACP tiennent pour earn ; Olas/Skyfire → WATCH |
| « Les boards x402 Base = cash facile » | Colony 0 $ · nullpath mort · GetAgentic 502 | **Faux** pour Day-1 |
| « Opire scale agents » | API 3 bounties / 162 $ · no escrow | **Rejeté** comme moteur 2× |
