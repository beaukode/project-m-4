# Marchés agent-friendly — shortlist

**Date de revue :** 2026-11-21 · **0 spend** · recherche docs + triangulation web uniquement.  
**Objectif :** plateformes où un **agent IA** peut s’enregistrer / offrir un service / être payé **sans** passer pour une personne physique sur un board freelance classique (Free-Work, LaborX.com, Malt, Upwork = hors scope ou bloqués — voir prefs + ledgers V-06).

**Méthode anti-scam :** ≥ 2 sources indépendantes par candidat (docs officielles + probe HTTP et/ou revue tierce). Pas d’invention de légitimité : doute → `WATCH` / `NO`.

**Verdicts :** `GO` = canal documenté + liveness + fit plausible 200 € / 30 j (temps, pas capital) · `WATCH` = intéressant mais volume / escrow / KYC / maturité non prouvés · `NO` = mort, mauvais côté du marché, ou monétisation absente.

**Réf. croisées :** [`vecteurs.md`](vecteurs.md) (V-06 / V-04) · [`pilot-plan.md`](pilot-plan.md) · ledgers `ops/ledgers/V-06.md`, `V-04.md`.

---

## Synthèse

| # | Plateforme | Escrow ? | Maturité | Fit ~200 € / 30 j | Verdict |
|---|------------|----------|----------|-------------------|---------|
| 1 | [Olas Mech Marketplace](#1-olas-mech-marketplace) | Oui (on-chain / balance tracker) | Live (turnover annoncé) | Moyen–élevé si outil niche demandée | **GO** |
| 2 | [Virtuals ACP](#2-virtuals-acp) | Oui (job contract USDC) | Live (docs + contrats Base) | Moyen (graduation + offre claire) | **GO** |
| 3 | [Skyfire (seller)](#3-skyfire-seller-directory) | Hold token pay / charge | Live (réseau + partenaires) | Moyen (MCP/API payante) | **GO** |
| 4 | [Agrenting](#4-agrenting) | Oui (plateforme) | Live API ; payouts non prouvés | Incertain | **WATCH** |
| 5 | [Opire](#5-opire) | Non | Live mais minuscule | Faible | **WATCH** |
| 6 | [GetAgentic](#6-getagentic) | Annoncé (x402 / Escrow.sol) | Pré-public / API 502 | Incertain | **WATCH** |
| 7 | [Agentverse / Fetch.ai](#7-agentverse-fetchai) | n/a earning agent | Discovery live ; monetization « coming soon » | Faible aujourd’hui | **NO** (earn) |
| 8 | [nullpath](#8-nullpath) | Annoncé | Shutdown / 522 | Nul | **NO** |
| 9 | [SwarmSync](#9-swarmsync) | Oui (claim) | Site up ; fiabilité contestée | Incertain | **WATCH** |
| 10 | [Vangrid](#10-vangrid) | Oui (côté acheteur) | Live docs | N/A (agent = acheteur) | **NO** (earn) |

**Top GO pour Agent 4 (ordre) :** Olas Mech → Virtuals ACP (provider) → Skyfire seller.

---

## 1. Olas Mech Marketplace

| Champ | Contenu |
|-------|---------|
| **URL** | [olas.network/mech-marketplace](https://olas.network/mech-marketplace) · docs build [build.olas.network/monetize](https://build.olas.network/monetize) · stack [stack.olas.network/mech-server](https://stack.olas.network/mech-server/) |
| **Ce que l’agent peut faire** | Déployer un **Mech** (service on-chain / HTTP off-chain) enregistré au registry Olas ; d’autres agents paient pour des outils (prédiction, image, recherche, etc.). |
| **Rails de paiement** | Crypto multi-chaînes (USDC / natifs / OLAS selon chaîne) ; paiements accumulés dans un balance tracker ; retrait avec fee DAO. |
| **Escrow ?** | Oui — dépôt requester + règlement à la livraison (détail : [theagenteconomy.si compare](https://theagenteconomy.si/compare/agent-escrow-marketplaces)). |
| **ToS / politique agent** | Marketplace **ouverte et permissionless** : « Anyone can run a Mech and offer its services there » ([blog KYA](https://olas.network/blog/kya)). Pearl Terms : les Mechs sont des logiciels enregistrés sur le marketplace ; Mechs tiers = Third-Party Integrations ([pearl-terms](https://olas.network/pearl-terms)). Quote Pearl : « Agents may request and pay for services from “Mechs” (software registered on the Olas Marketplace that performs tasks…) ». |
| **Maturité** | **Live** — page marketplace (snapshot 2026-11-21) : turnover ~**111 215 $** task payments ; millions de tx A2A revendiquées. API ERC-8004 marketplace HTTP 200 (probe). |
| **Volume / fit 200 €·30 j** | Volume global réel mais **concurrence** + besoin d’un outil différenciant (ex. brief anti-scam / docs lecture seule) et d’un runtime (Docker/Poetry — hors infra live actuelle → docs + design d’abord). Un flux micro-paiements répétés peut agréger vers ~200 € **si** demande ; non garanti. |
| **Risques / scams** | Mechs non revus par Olas (KYA = preuve de domaine, pas d’identité humaine) ; gas / ops multi-chaîne ; fee DAO à retrait ; pas de court de litige documenté (comparateur externe). |
| **Sources (≥2)** | olas.network/mech-marketplace · build.olas.network/monetize · olas.network/blog/kya · theagenteconomy.si · marketplace.olas.network API |
| **Verdict** | **GO** — canal agent-natif le plus crédible (volume + docs + permissionless). Prochaine étape docs : designer 1 outil Mech aligné V-11/V-06 ; **pas** de déploiement tant que spend/infra non autorisés. |

---

## 2. Virtuals ACP

| Champ | Contenu |
|-------|---------|
| **URL** | [os.virtuals.io/acp/overview](https://os.virtuals.io/acp/overview/) · concepts [os.virtuals.io/acp/concepts](https://os.virtuals.io/acp/concepts) · provider CLI [provider-workflow](https://os.virtuals.io/acp/cli/provider-workflow) · app [app.virtuals.io](https://app.virtuals.io/) |
| **Ce que l’agent peut faire** | S’enregistrer comme **Provider** (rôle HYBRID) ; publier des **Job Offerings** (prix USDC, SLA) ; livrer ; recevoir escrow. SDK/CLI machine-readable (`--json`). |
| **Rails de paiement** | USDC en escrow dans le smart contract Job ; split 95/5 (sans evaluator) ou 90/5/5 (avec). Chaînes multi (Base, etc.). |
| **Escrow ?** | **Oui** — « every job includes built-in escrow » ; release à `completed`, refund à `rejected` ([concepts](https://os.virtuals.io/acp/concepts)). |
| **ToS / politique agent** | [ACP Developer Agreement](https://app.virtuals.io/acp_developer_agreement.pdf) (2025-09-09) : « The ACP feature enables Users … to access and use **AI Agents** developed and operated by Developers » ; listing après **graduation** Sandbox→production. Terms of Use plateforme : [app.virtuals.io/terms-of-use](https://app.virtuals.io/terms-of-use). |
| **Maturité** | **Live** — >18 mois de production revendiqués ; >2 000 agents ; contrats ACP Core Base listés dans docs. app.virtuals.io HTTP 200. |
| **Volume / fit 200 €·30 j** | Fit **moyen** : une offre type « brief due-diligence / docs » à 50–250 USDC × 1–3 jobs = objectif. Frein : graduation manuelle Virtuals + éventuel compte app. **Interdit pour nous :** jobs *Fund-Transfer* (gestion de fonds client) — hors règles AGENTS. |
| **Risques / scams** | Graduation gate (déliste possible) ; rejet client = 0 pay ; risque de jobs demandant garde de fonds → kill immédiat ; tokenisation agent optionnelle = distraction hors scope. |
| **Sources (≥2)** | EconomyOS docs · ACP Developer Agreement PDF · GitHub Virtual-Protocol/acp-node-v2 · theagenteconomy.si |
| **Verdict** | **GO** — escrow USDC + politique agent explicite. Prioriser offre **service-only** (docs / research) alignée V-11 ; sandbox d’abord. |

---

## 3. Skyfire (seller directory)

| Champ | Contenu |
|-------|---------|
| **URL** | [skyfire.xyz](https://skyfire.xyz/) · seller services [docs.skyfire.xyz/docs/seller-services](https://docs.skyfire.xyz/docs/seller-services) · discovery [service-discovery](https://docs.skyfire.xyz/docs/service-discovery) · ToS [skyfire.xyz/terms-of-service](https://skyfire.xyz/terms-of-service/) |
| **Ce que l’agent / opérateur peut faire** | Créer un **seller agent** + **seller service** (API OpenAPI, MCP, site) ; agents acheteurs découvrent via Directory et paient avec tokens `pay` / `kya-pay`. |
| **Rails de paiement** | Crédits / USDC via tokens Skyfire ; charge après verify+deliver ; settlement garanti pour token valide (docs seller). |
| **Escrow ?** | Hold sur wallet acheteur à la création du token pay ; charge seller jusqu’au max du token (pas un escrow job classique freelance). |
| **ToS / politique agent** | Services Agreement : Access Authorizations pour « you and your **Associated Agents** » ([ToS](https://skyfire.xyz/terms-of-service/)). Directory : registry de services qui acceptent les AI agents comme clients de premier rang ([discovery](https://docs.skyfire.xyz/docs/service-discovery)). |
| **Maturité** | **Live** — sortie beta 2025 ; partenaires (Apify, Forter, Fetch.ai, etc.) BusinessWire ; case Akamai 2,5 M tx agentiques (nov. 2026). Docs HTTP 200. |
| **Volume / fit 200 €·30 j** | Fit **moyen** si on expose un MCP/API utile (ex. due-diligence lecture seule, résumé sources) à prix unitaire. Besoin : backend joignable + **review seller ~48 h**. Pas un board « mission 300 € » unique — plutôt volume micropaiements. |
| **Risques / scams** | KYB/KYA côté seller possible ; dépendance infra hébergement ; crédits non récupérables une fois présentés (ToS). |
| **Sources (≥2)** | docs.skyfire.xyz · BusinessWire launch · Akamai blog · skyfire ToS |
| **Verdict** | **GO** — pile identité+paiement crédible pour **vendre** un service à d’autres agents. Complète Olas/Virtuals (rail plutôt que bazaar jobs). |

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

1. **V-06** : pivoter les 2 canaux Day-1 hors Free-Work/LaborX vers **Virtuals ACP (provider)** + **Skyfire seller** (ou Olas Mech quand infra OK). Garder Free-Work seulement si email humain un jour — sinon abandon soft.
2. **V-04** : Opire reste WATCH opportuniste ; ajouter **Olas Mech** / bounties agent escrowés (pas OnlyDust mort).
3. **V-11** : offre naturelle sur ACP + Mech + Skyfire MCP (brief anti-scam lecture seule).
4. **Diversification** : paniers crypto/préservation inchangés ; cash services = GO agent markets, pas boards KYC.

## Prochaines actions (docs only)

- [ ] Rédiger 1 fiche offre Mech / ACP (prix, SLA, hors fund-transfer) alignée identité Noe.
- [ ] Surveiller GetAgentic API + Agrenting payouts (re-probe mensuel).
- [ ] Aucun claim Agrenting / aucun KYC Sumsub / aucun spend sans autorisation.

## Journal de triangulation (2026-11-21)

| Hypothèse | Sources | Verdict |
|-----------|---------|---------|
| « Des markets paient vraiment des agents » | Olas turnover page · Akamai/Skyfire · ACP docs | **Partiellement vrai** — Olas/Skyfire/Virtuals les plus solides |
| « Les boards x402 Base = cash facile » | Colony 0 $ · nullpath mort · GetAgentic 502 | **Faux** pour Day-1 |
| « Opire scale agents » | API 3 bounties / 162 $ · no escrow | **Rejeté** comme moteur 2× |
