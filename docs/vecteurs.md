# Vecteurs d’approche

Maintenir **≥ 10** vecteurs distincts et **peu corrélés**. Revisiter au moins une fois par jour (rapport 07:00 Europe/Paris).

**Objectif catalogue** : approches légales diversifiées visant **≥ 2× ~200 € ETH** en **30 jours**. Aucun déploiement de capital dans ce document — recherche et cadrage seulement.

**Caps dures & pilotes** : [`risk-limits.md`](risk-limits.md) · [`pilot-plan.md`](pilot-plan.md) (vague 1 : V-06, V-04, V-11).  
**Marchés agent-friendly** (shortlist GO/WATCH/NO) : [`agent-markets.md`](agent-markets.md) — pivot canaux V-06/V-04 hors Free-Work/LaborX/Malt/Upwork.  
Avant validate/reject d’une thèse : **recherche web externe** + triangulation (voir `AGENTS.md` règle 7).

Statuts : `idée` · `recherche` · `triangulé` · `prêt` · `actif` · `pause` · `abandonné`

Classes de risque : `faible` · `modéré` · `élevé` (toujours borné au capital dédié ; jamais de levier excessif)

## Vue d’ensemble

| ID | Vecteur | Famille | Cap capital suggéré | Risque | Statut | Ledger |
|----|---------|---------|---------------------|--------|--------|--------|
| V-01 | Yield L1 conservateur | crypto | ≤ 40 % (~80 €) | faible | idée | [ops/ledgers/V-01.md](../ops/ledgers/V-01.md) |
| V-02 | Points / airdrop légitimes | crypto | ≤ 25 % (~50 €) | modéré | idée | [ops/ledgers/V-02.md](../ops/ledgers/V-02.md) |
| V-03 | Écarts de frais / info-arb | crypto | ≤ 15 % (~30 €) | modéré | idée | [ops/ledgers/V-03.md](../ops/ledgers/V-03.md) |
| V-04 | Bounties / grants (+ Mech) | travail | ≤ 10 % gas (~20 €) ; pilote Mech ≤ 5 € | faible | triangulé (Mech) / recherche (pilote P1) · [`pilots/olas-mech`](pilots/olas-mech.md) | [ops/ledgers/V-04.md](../ops/ledgers/V-04.md) |
| V-05 | LP prudent paires majeures | crypto | ≤ 20 % (~40 €) | modéré | idée | [ops/ledgers/V-05.md](../ops/ledgers/V-05.md) |
| V-06 | Freelance / agent markets | web | 0 € capital (temps) | faible | recherche (pilote P0) · pivot agent-markets | [ops/ledgers/V-06.md](../ops/ledgers/V-06.md) |
| V-07 | Contenu niche monétisé | web | ≤ 5 % outils (~10 €) | faible | idée | [ops/ledgers/V-07.md](../ops/ledgers/V-07.md) |
| V-08 | Micro-produit digital | web | ≤ 15 % (~30 €) | modéré | idée | [ops/ledgers/V-08.md](../ops/ledgers/V-08.md) |
| V-09 | Affiliation déclarée | web | 0–5 % (~10 €) | faible | idée | [ops/ledgers/V-09.md](../ops/ledgers/V-09.md) |
| V-10 | Domaines / actifs numériques | ops | ≤ 25 % (~50 €) | modéré | idée | [ops/ledgers/V-10.md](../ops/ledgers/V-10.md) |
| V-11 | Recherche on-chain à façon | crypto-web | ≤ 5 % (~10 €) | faible | recherche (pilote P2) | [ops/ledgers/V-11.md](../ops/ledgers/V-11.md) |
| V-12 | Modération / community ops | web | 0 € capital | faible | idée | [ops/ledgers/V-12.md](../ops/ledgers/V-12.md) |
| V-13 | Jeux : assist humain / API autorisée | web-jeux | ≤ 5 % outils (~10 €) | faible–modéré | recherche | [ops/ledgers/V-13.md](../ops/ledgers/V-13.md) |

Caps **non cumulatifs à 100 %** : on n’alloue jamais tout le capital à un seul panier ; le total engagé à un instant T doit rester **≤ 70 %** du NAV dédié (réserve gas + opportunité).

---

## V-01 — Yield L1 conservateur

| Champ | Contenu |
|-------|---------|
| **ID** | `V-01` |
| **Thèse** | Stationner une part d’ETH/stables sur protocoles L1 établis (staking liquide mature, lending blue-chip) pour une rémunération faible mais positive pendant que d’autres vecteurs travaillent. |
| **Pourquoi ~200 €** | Pas besoin de taille institutionnelle ; les pools majeurs acceptent de petites tailles. Sert de **filet** et de base NAV, pas de moteur 2× seul. |
| **Cap capital** | ≤ **40 %** du NAV (~80 €) ; pas de leverage, pas de recursive looping. |
| **Risque** | `faible` (smart-contract + depeg stables si utilisés) |
| **Anti-scam** | Domaine officiel triangulé ; audits publics ; TVL historique ; pas de site « mirror » ; jamais de seed ; simuler tx en lecture seule d’abord. |
| **Prochaine étape** | Lister 3 protocoles L1 (ETH) avec liens docs + audits ; comparer APY réel vs frais gas sur 30 j. |
| **Kill** | APY net < coûts gas sur 14 j **ou** alerte exploit / admin-key douteuse **ou** UI demandant seed / signature hors scope. |

---

## V-02 — Points / airdrop légitimes

| Champ | Contenu |
|-------|---------|
| **ID** | `V-02` |
| **Thèse** | Accumuler des points sur protocoles crédibles (usage réel, pas farm toxique) avec asymétrie upside si distribution future. |
| **Pourquoi ~200 €** | Les programmes de points récompensent souvent l’activité qualitative plus que le capital massif ; petites tailles restent éligibles. |
| **Cap capital** | ≤ **25 %** (~50 €) + gas ; jamais « all-in » sur un seul programme. |
| **Risque** | `modéré` (opportunité nulle, lock, changement de règles) |
| **Anti-scam** | Annonces sur canaux officiels + explorateur + forum indépendant ; contrats connus ; **aucune** demande de seed ; méfiance des « checkers » tiers. |
| **Prochaine étape** | Shortlist de 2–3 programmes L1/L2 crédibles ; documenter règles, deadlines, coût gas estimé. |
| **Kill** | Demande de seed / signature aveugle **ou** programme sans source officielle triangulée **ou** coût gas > 30 % du capital alloué sans preuve d’éligibilité. |

---

## V-03 — Écarts de frais / arbitrage informationnel

| Champ | Contenu |
|-------|---------|
| **ID** | `V-03` |
| **Thèse** | Détecter des écarts de prix ou de frais entre venues publiques (CEX listées / DEX majeurs) exploitables **sans** MEV toxique ni front-running illégal. |
| **Pourquoi ~200 €** | Les micro-écarts existent à petite taille ; l’enjeu est le **seuil de rentabilité après frais**, pas le notional. |
| **Cap capital** | ≤ **15 %** (~30 €) par opportunité ; stop net après frais. |
| **Risque** | `modéré` (latence, frais, faux signaux) |
| **Anti-scam** | Feeds publics multiples ; pas de tip « exclusif » payant ; pas de bot vendeur de signaux ; venues réglementées ou DEX majeurs uniquement. |
| **Prochaine étape** | Construire une grille manuelle : 3 paires majeures × 2 venues ; mesurer spread vs frais sur 48 h (sans trade). |
| **Kill** | Aucun écart net > 0 après frais sur 7 j d’observation **ou** contrepartie / bot opaque **ou** pression vers levier. |

---

## V-04 — Bounties / grants crypto

| Champ | Contenu |
|-------|---------|
| **ID** | `V-04` |
| **Thèse** | Rémunération légitime (bounties docs/code, grants, quests vérifiées **et** micro-tâches Mech/agent escrowées) convertible en ETH ou fiat→ETH. |
| **Pourquoi ~200 €** | Le capital n’est presque pas engagé — le levier est le **temps / compétence**. Un seul bounty mid-size peut couvrir une part du 2×. |
| **Cap capital** | ≤ **10 %** en gas / outils (~20 €) ; pas de dépôt « pour être éligible ». |
| **Risque** | `faible` (non-paiement, scope creep) |
| **Anti-scam** | Plateforme connue + historique de paiements ; identité org vérifiable ; contrat / issue GitHub claire ; pas de frais d’inscription ; préférer escrow on-chain (voir [`agent-markets.md`](agent-markets.md)). |
| **Prochaine étape** | Fiche [`pilots/olas-mech.md`](pilots/olas-mech.md) : dry-run §6.B ; **pas** de `mech setup` mainnet tant que Docker + bridge + spend non autorisés. Opire = opportuniste. |
| **Kill** | Frais d’entrée demandés **ou** paiement uniquement via canal obscur **ou** 3 non-paiements documentés sur la même source **ou** board mort (OnlyDust/Algora déjà écartés) **ou** kills Mech de la fiche Day-0. |

---

## V-05 — Liquidité / LP prudent

| Champ | Contenu |
|-------|---------|
| **ID** | `V-05` |
| **Thèse** | Fournir de la liquidité sur paires majeures (ETH/stables blue-chip) avec fourchettes larges et IL borné. |
| **Pourquoi ~200 €** | Les DEX L1 majeurs acceptent de petites positions ; utile pour apprendre le flux fees vs IL à échelle réelle. |
| **Cap capital** | ≤ **20 %** (~40 €) ; une seule paire à la fois au début. |
| **Risque** | `modéré` (IL, smart-contract, gas) |
| **Anti-scam** | UI officielle ; audits ; simulation petite taille ; retirer = path clair ; pas de « vault » inconnu wrappant le LP. |
| **Prochaine étape** | Simuler IL sur ETH/USDC (range large) pour 40 € / 30 j ; comparer fees historiques vs IL scénario ±10 %. |
| **Kill** | IL estimé > fees sur scénario de base **ou** pool / vault non auditée **ou** UI non officielle. |

---

## V-06 — Freelance web / ops

| Champ | Contenu |
|-------|---------|
| **ID** | `V-06` |
| **Thèse** | Vendre du temps / livrables (dev front, scripts, ops docs, automatisation, briefs) facturé en fiat ou crypto — **via marchés qui acceptent explicitement les agents** quand possible ; reconversion en ETH si besoin. |
| **Pourquoi ~200 €** | Indépendant du yield DeFi : **1–2 missions** à 200–400 € suffisent pour viser le 2× ; corrélation faible avec le marché crypto. |
| **Cap capital** | **0 €** de capital marché ; éventuels outils ≤ 5 %. |
| **Risque** | `faible` (impayés, mauvaise scope) — risque **canal** si board KYC/personne physique. |
| **Anti-scam** | Client identifiable ; acompte ou plateforme escrow connue ; pas de « pay to apply » ; pas de chèque / crypto étrange en prépaiement inverse ; **pas** LaborX automation ; pas Malt/Upwork (prefs). |
| **Prochaine étape** | Publier 1 offre claire sur **2 canaux GO** de [`agent-markets.md`](agent-markets.md) : **Virtuals ACP** (provider, service-only) + **Skyfire seller** (MCP/API) ; Olas Mech quand runtime autorisé. Free-Work seulement si email humain. Viser 3 conversations / 1 job funded en 7–14 j. |
| **Kill** | 14 j sans lead qualifié malgré outreach documenté **et** pivot vers V-04/V-07/V-11 ; ou client exigeant paiement hors escrow sans historique ; ou canal exigeant KYC personne / forbidding bots. |

---

## V-07 — Contenu niche monétisé

| Champ | Contenu |
|-------|---------|
| **ID** | `V-07` |
| **Thèse** | Produire un flux court (notes techniques, veille protocoles, tutoriels ops) monétisé via abonnements, tips crypto, ou sponsoring déclaré. |
| **Pourquoi ~200 €** | Coût de démarrage quasi nul ; un sponsor unique ou quelques abonnés payants peuvent dépasser le yield DeFi sur 30 j. |
| **Cap capital** | ≤ **5 %** (~10 €) outils / domaine. |
| **Risque** | `faible` (audience lente ; risque réputation si claim faux) |
| **Anti-scam** | Pas de shill token non triangulé ; sponsoring **déclaré** ; pas de « sign up & send ETH » ; sources citées. |
| **Prochaine étape** | Choisir 1 niche (ex. « garde-fous agent crypto ») ; publier 3 notes publiques ; activer un lien de tip / abonnement. |
| **Kill** | 21 j sans engagement mesurable (vues/réponses) **ou** pression à promouvoir un projet non triangulé. |

---

## V-08 — Micro-produit digital

| Champ | Contenu |
|-------|---------|
| **ID** | `V-08` |
| **Thèse** | Packager un livrable réutilisable (template, checklist ops, petit outil CLI/web) vendu à prix bas/volume ou one-shot. |
| **Pourquoi ~200 €** | Coût de build en temps ; quelques ventes à 20–50 € convergent vers l’objectif sans exposer le wallet. |
| **Cap capital** | ≤ **15 %** (~30 €) hébergement / outils ; pas d’ads payants massifs au départ. |
| **Risque** | `modéré` (zéro vente, scope creep build) |
| **Anti-scam** | Paiement via processeur connu ou invoice claire ; pas de marketplace louche ; licence / TOS propres ; pas de scrape de contenu copyrighted. |
| **Prochaine étape** | Définir 1 MVP vendable en ≤ 5 j de build ; page d’offre + prix ; 10 outreaches ciblés. |
| **Kill** | Build > 10 j sans MVP **ou** 0 vente / 0 waitlist après 50 touches documentées. |

---

## V-09 — Affiliation déclarée

| Champ | Contenu |
|-------|---------|
| **ID** | `V-09` |
| **Thèse** | Recommander des outils / services réellement utilisés (hébergeurs, SaaS, hardware wallet, livres) via liens d’affiliation **divulgués**. |
| **Pourquoi ~200 €** | Zéro inventaire ; commissions unitaires faibles mais stackables avec V-07/V-08 ; convertible fiat→ETH. |
| **Cap capital** | **0–5 %** (~10 €) pour essais produits légitimes si nécessaire. |
| **Risque** | `faible` (réputation si mauvaise reco) |
| **Anti-scam** | Programmes officiels uniquement ; disclosure systématique ; jamais d’exchange / broker non régulé poussé pour kickback ; pas de « guaranteed returns ». |
| **Prochaine étape** | Sélectionner 3 programmes d’affiliation réputés liés au contenu V-07 ; vérifier ToS + taux ; ajouter disclosure template. |
| **Kill** | Programme demandant faux reviews **ou** produit non utiliséable triangulé **ou** 30 j à 0 clic tracké malgré trafic. |

---

## V-10 — Domaines / actifs numériques

| Champ | Contenu |
|-------|---------|
| **ID** | `V-10` |
| **Thèse** | Acquérir à bas prix des domaines ou actifs numériques liquides (noms clairs, typos légitimes absentes — **pas** de typosquatting) pour revente rapide. |
| **Pourquoi ~200 €** | Le marché des domaines entry-level permet des tickets de 10–50 € ; un flip 2–3× sur un actif finance une part du goal. |
| **Cap capital** | ≤ **25 %** (~50 €) ; max 3 actifs simultanés. |
| **Risque** | `modéré` (illiquidité, perte totale du ticket) |
| **Anti-scam** | Registrar connu ; pas de marketplace escrow obscur ; vérifier historique WHOIS / trademarks ; **interdiction** typosquatting / phishing domains. |
| **Prochaine étape** | Scruter 20 noms candidats (marque générique + extension) ; estimer revente via 2 marketplaces ; n’acheter qu’après triangulation prix. |
| **Kill** | Aucun bid / offre en 21 j **ou** conflit trademark **ou** marketplace demandant seed / paiement irréversible hors escrow reconnu. |

---

## V-11 — Recherche on-chain à façon

| Champ | Contenu |
|-------|---------|
| **ID** | `V-11` |
| **Thèse** | Vendre des briefs courts (due diligence protocole, cartographie flux, revue docs anti-scam) à des indés / petites équipes. |
| **Pourquoi ~200 €** | Service à forte marge ; 1–2 briefs à 150–300 € atteignent l’objectif ; capital quasi nul. |
| **Cap capital** | ≤ **5 %** (~10 €) outils d’explorateur / API free-tier. |
| **Risque** | `faible` (scope, responsabilité — disclaimer clair) |
| **Anti-scam** | Client réel ; pas de travail pour pump groups ; sources publiques citées ; disclaimer « pas un conseil financier ». |
| **Prochaine étape** | Rédiger 1 brief sample public (protocole blue-chip) ; proposer le format + prix sur **Virtuals ACP** + **Skyfire/Olas** (pas LaborX/Free-Work) — voir [`agent-markets.md`](agent-markets.md). |
| **Kill** | Demande de « shill report » payé **ou** 14 j sans intérêt après sample **et** réallocation temps vers V-04/V-06. |

---

## V-12 — Modération / community ops

| Champ | Contenu |
|-------|---------|
| **ID** | `V-12` |
| **Thèse** | Missions rémunérées de modération, support, ou ops communauté pour projets crypto/web établis (pas de « guardez des fonds »). |
| **Pourquoi ~200 €** | Payé à l’heure ou au mois ; corrélation faible avec le prix de l’ETH ; convertible fiat→ETH. |
| **Cap capital** | **0 €** |
| **Risque** | `faible` (impayé, burn-out scope) |
| **Anti-scam** | Projet à présence publique vérifiable ; paiement via canal clair ; **jamais** de garde de seeds / multisig inconnue ; pas de rôle « treasury » improvisé. |
| **Prochaine étape** | Lister 5 projets hiring mods/community ; postuler avec profil Noe ; tracer réponses. |
| **Kill** | Rôle exigeant contrôle de fonds / seed **ou** 3 offres « pay to join staff » **ou** 21 j sans réponse qualifiée. |

---

## V-13 — Jeux : assist humain / API autorisée

| Champ | Contenu |
|-------|---------|
| **ID** | `V-13` |
| **Thèse** | Monétiser **légalement** le temps jeux via (B) contenus/outils d’**assist** pour un opérateur humain (plans, checklists, revue post-partie, dashboards API read-only) — **sans** injection d’inputs. Track A bots seulement si ToS **explicite** **et** économie viable (aujourd’hui : pas de GO capital ; Lichess/SL en WATCH). Détail : [`game-paths.md`](game-paths.md). |
| **Pourquoi ~200 €** | Capita presque nul ; 1 pack contenu ou 1 mission coach post-VOD peut contribuer au 2× via fiat→ETH. **Pas** un moteur stake/gambling. |
| **Cap capital** | ≤ **5 %** (~10 €) outils ; **0 €** stake tournois/arènes crypto tant que non autorisé + triangulation. |
| **Risque** | `faible`–`modéré` (ban si dérive ToS ; revenu lent ; KYC si Second Life cashout) |
| **Anti-scam** | Citer ToS/API officiels ; jamais de « bot indétectable » ; pas de dépôt arènes non triangulées ; LindeX officiel seulement pour SL. |
| **Prochaine étape** | 1 livrable Track B safe (ex. checklist pré-match hors client **ou** brief post-VOD sample) lié V-07/V-08 ; **ne pas** financer bandforband/PIVArena/etc. |
| **Kill** | Toute automation d’inputs / overlay compétitif gris **ou** pression vers RMT / arène non triangulée **ou** 21 j sans livrable utile après démarrage actif. |

---

## Corrélation & diversification

| Panier | Vecteurs | Rôle |
|--------|----------|------|
| Préservation | V-01, V-05 | NAV stable / apprentissage on-chain |
| Asymétrie crypto | V-02, V-03 | Upside non linéaire borné |
| Cash services | V-04, V-06, V-11, V-12 | Moteur principal vers 2× |
| Produits / attention | V-07, V-08, V-09, V-13 | Leviers web / jeux légitimes à faible capital |
| Actifs digitaux | V-10 | Ticket spéculatif borné |

Règle : au moins **3 paniers** représentés dans le plan de semaine ; ne pas empiler V-01+V-02+V-05+V-03 au-delà du cap global 70 %.

## Règles de validation

Avant de passer un vecteur en `prêt` / `actif` :

1. Trianguler (≥ 2–3 sources indépendantes).
2. Vérifier qu’aucune demande de seed / clé / signature aveugle n’est requise.
3. Estimer le downside max et rester dans le capital dédié + caps ci-dessus.
4. Remplir le ledger `ops/ledgers/V-XX.md` (décision, anti-scam, kill).
5. Mentionner dans le rapport quotidien.

## Hors scope (toujours)

- Vol, piratage, armes, drogues, harm, arnaques, phishing, market manipulation illégale.
- Engagement de capital (trading, bridging, spending) tant que non autorisé explicitement.
- Typosquatting, faux avis, shill non déclaré, garde de fonds pour tiers inconnus.
