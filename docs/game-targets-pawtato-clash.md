# Cibles manquées — Pawtato Land & Clash of Coins

Étude approfondie (Agent 4 / Project M). **Aucun spend / ops capital.**  
Langue : FR. Date : **2026-11-21**.  
Contexte : le funnel jeux initial (API bots explicites + titres connus + arènes agents crypto) a manqué cette classe **P2E / Web3 browser MMORPG**. Méthode corrigée → [§4](#4-méthode-de-découverte-future) + [`game-paths.md`](game-paths.md) §1.

**Préférence** : bots seulement si ToS/API **explicitement** autorisés ; sinon humain + assist IA **sans** injection d’inputs.

---

## Résumé exécutif

| Cible | Chaîne | Track A (bots) | Track B (humain+assist) | Fit ~200 € → 2×/30 j |
|-------|--------|---------------|-------------------------|---------------------|
| [Pawtato Land](https://pawtato.gg/) | Sui (+ TATO aussi Solana via Wormhole) | **NO** | **WATCH** | Faible (NFT gate, liquidité fine, hors L1) |
| [Clash of Coins](https://clashofcoins.com/) | Base (OWB ERC-20) | **WATCH** | **WATCH** | Faible→négatif attendu si stake/pass (EV floue, Risk-to-Earn, token spéculatif) |

**Aucun GO capital.** Pas de nouveau vecteur d’allocation ; journaliser sous **V-13** (`recherche`). Réévaluer Clash Agentic Mode seulement après (1) autorisation spend, (2) preuve cash-out ETH-compatible, (3) triangulation anti-scam renforcée.

---

## 1. Pawtato Land (`pawtato.gg`)

### 1.1 Qu’est-ce que c’est

Browser **Web2.5 MMORPG** (Pawtato Finance Corp.) : Lands / Heroes NFT sur **Sui**, boucle produce → craft → adventure → trade, token **$TATO** (supply fixe 1B, burns). Jouable sans wallet pour une grande partie ; wallet Sui requis pour stake NFT / withdraw on-chain.

Sources officielles : [landing](https://pawtato.gg/), [guide](https://pawtato.gg/guide), [getting started](https://pawtato.gg/guide/getting-started), [docs](https://docs.pawtato.gg/), [TATO](https://pawtato.gg/guide/tato-token).

### 1.2 Comment on « gagne » (crypto / cashout)

| Voie | Mécanique | Cashout |
|------|-----------|---------|
| Production / craft | Lands stakés → ressources → items | Vente Marketplace / Exchange → TATO backpack → withdraw wallet |
| Quêtes / Arena | Récompenses TATO (dont une part **soulbound** non withdrawable) | Soulbound ≠ cashout ; TATO sellable seulement |
| NFT secondary | Lands / Heroes TradePort + in-game | SUI / TATO ; bridge multi-chain possible |
| xTATO staking | Lock TATO → share 25 % fees gameplay | Yield en éco jeu, pas fiat auto |

Convert / swap in-game (ex. vers USDC via pool) documenté côté marketplace — **liquidité réelle à vérifier avant tout withdraw**.

### 1.3 ToS / bots / automation

| Règle | Verdict |
|-------|---------|
| [Rules](https://docs.pawtato.gg/pawtato-land/gameplay/rules) : *« No Botting or Automation »* — bots, macros, auto-clickers, scripts **interdits** ; gameplay **manuel** | Track A gameplay = **NO** |
| Exception : *automated trading via the Orderbook Exchange* **permis** ; Marketplace scripted/sniping **interdit** | Bot farm = NO ; bot orderbook = zone étroite seulement |
| [ToS](https://pawtato.gg/terms) (maj 2026-07-22) : scraping / robots non autorisés hors navigateur ; 18+ ; territoires sanctionnés exclus ; droits AML/suspension | Pas d’API bot play |

### 1.4 KYC / éligibilité

- Âge **≥ 18** ; Restricted Territories (ex. sanctions list ToS).
- Pas de KYC retail obligatoire pour jouer documenté ; **compliance / AML** à discrétion de Pawtato (suspension possible).
- Wallet non-custodial pour assets on-chain (risque user, pas custodial game).

### 1.5 Liquidité / risques / anti-scam

| Signal | Observation | Source |
|--------|-------------|--------|
| NFT Land | Floor ~54 SUI (~$44 snapshot tide) ; volume 7j ~1,3k SUI ; wash faible | [tide.ad collection](https://tide.ad/collection/pawtato-land) |
| TATO | Liquidité ~$168k, volume 24h ~$800 (snapshot bitgamble) — **slippage** probable | [bitgamble.org/p2e-games/pawtato](https://bitgamble.org/p2e-games/pawtato/) |
| Faux tokens | Docs : *beware fake TATO* ; adresses officielles Sui + Solana | [tokenomics](https://docs.pawtato.gg/token/basics/tokenomics) |
| Crédibilité projet | Podcast game director (économie / anti-dilution) ; docs riches | [JRPG podcast](https://jrpg.com/inside-pawtato-land-with-game-director-adam-jrpg-crypto-games-podcast/) |
| Chaîne | Focus jeu = **Sui** ≠ ETH L1 Agent 4 | Officiel |
| Entry | Lands/Heroes **fully minted** ; scholarship **annoncée** pas « live gratis earn » | Getting started |

**Anti-scam** : site + docs + TradePort + tide analytics = triangulation OK pour « projet réel ». Risque = **GameFi / illiquidité / NFT gate**, pas rug site clone évident. Toujours vérifier adresses TATO vs docs.

### 1.6 Fit Agent 4 (~200 € / 30 j / ETH L1)

- Cap entry : 1 Plot ~dizaines € SUI + Hero + working capital TATO → mange une part non triviale du NAV **sans** promesse de 2×.
- Revenu = économie joueur-vs-joueur + token volatile ; pas de salaire agent.
- Cashout → Sui/Solana/TATO → bridge → ETH = friction + risque + hors scope spend.
- Scholarship non disponible = pas de F2P earn sérieux documenté.

### 1.7 Verdicts

| Track | Verdict | Pourquoi |
|-------|---------|----------|
| **A bots** | **NO** | Rules interdisent automation gameplay ; seule exception orderbook (pas un path bot P2E). |
| **B humain+assist** | **WATCH** | Plans/stratégie hors client OK ; humain clique. Fit capital 2×/30 j **faible** ; hors L1. |
| **Capital** | **NO** (maintenant) | Pas de spend ; même autorisé → mauvais moteur 2×. |

**Kill** : pression bot/macro · faux token · demande seed · scholarship qui exigerait multi-account (interdit).

---

## 2. Clash of Coins (`clashofcoins.com`)

### 2.1 Qu’est-ce que c’est

PvP MMORPG temps réel (OWB Studio Inc., BVI) : carte monde, territoires, alliances ; **Web3 optionnel** ; token **$OWB** sur **Base** ; distribution Base App. Positionnement fort **Agentic Mode** : commander des agents IA (OVERRIDE) plutôt que grinder manuellement.

Sources : [landing](https://clashofcoins.com/), [docs](https://docs.clashofcoins.com/), [llms.txt](https://clashofcoins.com/llms.txt), [economy](https://clashofcoins.com/economy/), [OWB](https://docs.clashofcoins.com/owb-token).

### 2.2 Comment on « gagne »

| Voie | Mécanique | Notes |
|------|-----------|-------|
| Activity Points | Jeu + social + referral (Treasure Clash) | Points → upside éco ouverte ; règles changeables |
| Tournaments / Risk-to-Earn | Remplace grosses payouts saisonnières | EV peut être **négative** (stake/risk) |
| Agentic Tournament | Marketing pool prix (claims $5M) | Vérifier règles/éligibilité avant tout |
| OWB / items | Utility, marketplace, passes | Spéculation token ≠ salaire |
| x402 shop API | Agents achètent items en **USDC Base** | C’est **dépense**, pas earn |

F2P possible ; passes agentic marketing **$9 / $90 / $270 / $900** ([llms.txt](https://clashofcoins.com/llms.txt)).

### 2.3 ToS / bots / API

| Règle | Verdict |
|-------|---------|
| [Terms](https://clashofcoins.com/terms/) (rév. 2026-10-01) : interdisent cheats / *automation software (bots) **not expressly authorized*** | Bots tiers non autorisés = **NO** |
| Exception structurante : Agentic Mode + API x402 + MCP **publiés par l’éditeur** | Automation **autorisée** dans le cadre officiel seulement |
| API : `POST …/shop/x402/buy` — checkout items, **pas** un bot qui capture la map tout seul hors product | Track A = orchestrer **leur** agent / payer shop, pas reverse-engineer client |

Probe live : OpenAPI x402 répond (`openapi` 3.1, Base USDC) — surface agent réelle.

### 2.4 KYC / éligibilité

- **≥ 18** ; Prohibited Persons / sanctions.
- Société **peut** demander **KYC / AML** (achats, redemption voucher Clash Pass, compliance) — [Special Pre-Sale Terms](https://clashofcoins.com/agenticsale/).
- Guest / wallet connect pour jouer ; KYC = escalade humaine si bloquant.

### 2.5 Liquidité / risques / anti-scam

| Signal | Observation | Source |
|--------|-------------|--------|
| OWB CMC | Mcap ~$3.3M ; ATH ~$0.16 → ~−95 % | [CoinMarketCap OWB](https://coinmarketcap.com/currencies/owb/) |
| DEX | Aerodrome OWB/USDC liq. ~$55k | [DexScreener](https://dexscreener.com/base/0xef5997c2cf2f6c138196f8a6203afc335206b3c1) |
| On-chain risk | Rapport : high risk — mint flags / concentration top holders | [rapport.lat OWB](https://rapport.lat/token/base/0xef5997c2cf2f6c138196f8a6203afc335206b3c1) |
| Présence | Docs, Base leaderboard claims, GitHub onewayblock, CMC listing | Officiel + CMC |
| Modèle reward | Shift vers **Risk-to-Earn** (pression token) | [Game Activities](https://docs.clashofcoins.com/treasure-clash-program/game-activities) |

**Anti-scam** : projet visible / listé, **mais** token GameFi spéculatif + concentration + liq. fine + marketing prize pools. Triangulation = **WATCH élevé**, pas « safe blue-chip ».

### 2.6 Fit Agent 4

- Chaîne **Base** (proche écosystème ETH L2) mieux que Sui pour éventuel bridge, mais **pas** focus L1 wallet-01 tel quel.
- Track A « autorisé » existe **officiellement** — rare vs Pawtato — mais monétisation = tournois/points/OWB, pas salaire USDC clair.
- Passes / Risk-to-Earn peuvent **brûler** le capital 200 €.
- x402 API = surtout **payer** items, pas cashout.

### 2.7 Verdicts

| Track | Verdict | Pourquoi |
|-------|---------|----------|
| **A bots** | **WATCH** | Agents / x402 **expressly** dans le produit ; **pas** GO capital (EV, Risk-to-Earn, OWB risk, spend). |
| **B humain+assist** | **WATCH** | Modèle « commander » + plans stratégiques hors injection = aligné préf. ; temps opérateur. |
| **Capital** | **NO** (maintenant) | Spend non autorisé ; même plus tard → pilote micro seulement après preuve cashout. |

**Kill** : bot client non officiel · dépôt pass sans preuve payout · demande seed · KYC impossible **et** aucune voie F2P utile · scores risque on-chain qui empirent.

---

## 3. Comparaison & décision Agent 4

| Critère | Pawtato | Clash of Coins |
|---------|---------|----------------|
| Bot ToS-safe | Non (sauf orderbook) | Oui (Agentic + x402 officiels) |
| Earn → crypto liquide | TATO fin | OWB fin + points/tournois |
| Entry capital | NFT Lands/Heroes | F2P ; passes optionnels chers |
| Chaîne vs L1 | Sui | Base |
| Scam surface | Faible (projet réel) | Faible–modéré (token risk élevé) |
| 2× / 30 j | Non réaliste comme thèse | Non sans EV prouvée |

**Décision autonome** : documenter seulement ; **ne pas** ouvrir ledger d’allocation ni stub vecteur GO. Mettre à jour V-13 (journal). Annulation = ignorer ces cibles / passer V-13 en `abandonné` si opérateur refuse le panier jeux.

---

## 4. Méthode de découverte future

*(Pourquoi on a manqué ces deux : funnel trop étroit = « API bot explicite + titres AAA + agent arenas ».)*

### 4.1 Funnel élargi (obligatoire)

1. **Directories P2E / Web3 games** (pas seulement agent arenas) : listes Solana/Sui/Base/ETH gaming, DappRadar Gaming, CoinGecko « Play To Earn », LootRadar, Base App leaderboard, etc.
2. **Mots-clés recherche** (web, ≥2 passes) :  
   `play to earn browser` · `web3 mmorpg` · `nft land game` · `agentic gaming` · `x402 game` · `AI agents play to earn` · `Base App game` · `Sui RPG` · `optional web3 game` · noms issus des leaderboards.
3. **Signaux éditeur** : pages `/llms.txt`, OpenAPI, MCP, « agent mode », scholarship, activity points, marketplace withdraw.
4. **Filtres Agent 4** (dans l’ordre) :  
   (a) ToS bots → A/B/NO · (b) anti-scam ≥2 sources · (c) cashout réel vers crypto · (d) chaîne vs ETH L1 · (e) fit 200 € / 30 j · (f) KYC humain ? · (g) spend requis ?
5. **Ne pas s’arrêter** si « pas d’API bot » : classer en Track B candidat si humain+assist monétisable (contenu, coaching, spreadsheets).

### 4.2 Fréquence

- Au moins **1 scan directories** par semaine ou avant chaque rapport jeux.
- Toute suggestion opérateur (« et X.com ? ») → fiche courte ≤48 h avec GO/WATCH/NO.

### 4.3 Livrable type

Une ligne dans [`game-paths.md`](game-paths.md) tableau + fiche si WATCH/GO ; ledger V-13 ; **pas** de spend.

---

## 5. Sources (index)

| # | Source | Usage |
|---|--------|-------|
| 1 | https://pawtato.gg/ | Officiel Pawtato |
| 2 | https://pawtato.gg/guide | Guide produit |
| 3 | https://pawtato.gg/terms | ToS Pawtato |
| 4 | https://docs.pawtato.gg/pawtato-land/gameplay/rules | Ban bots + exception orderbook |
| 5 | https://docs.pawtato.gg/token/basics/tokenomics | Adresses TATO / fake warning |
| 6 | https://tide.ad/collection/pawtato-land | NFT liquidité indépendante |
| 7 | https://bitgamble.org/p2e-games/pawtato/ | Snapshot marché TATO indépendant |
| 8 | https://jrpg.com/inside-pawtato-land-with-game-director-adam-jrpg-crypto-games-podcast/ | Interview secondaire |
| 9 | https://clashofcoins.com/ | Officiel CoC |
| 10 | https://clashofcoins.com/llms.txt | Agents / pricing / API |
| 11 | https://clashofcoins.com/terms/ | ToS bots « expressly authorized » |
| 12 | https://docs.clashofcoins.com/ | Docs produit |
| 13 | https://docs.clashofcoins.com/owb-token | OWB contract Base |
| 14 | https://docs.clashofcoins.com/treasure-clash-program | Points / Risk-to-Earn |
| 15 | https://x402.clashofcoins.com/openapi.json | Probe API live |
| 16 | https://coinmarketcap.com/currencies/owb/ | Marché OWB |
| 17 | https://dexscreener.com/base/0xef5997c2cf2f6c138196f8a6203afc335206b3c1 | Liq. DEX |
| 18 | https://rapport.lat/token/base/0xef5997c2cf2f6c138196f8a6203afc335206b3c1 | Risk on-chain indépendant |
| 19 | https://clashofcoins.com/agenticsale/ | Passes / KYC redemption |

*Consulté 2026-11-21. Re-vérifier avant tout `prêt` / `actif` / spend.*
