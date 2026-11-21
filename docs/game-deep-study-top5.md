# Deep-study top 5 — P2E / Web3 / agent games

Étude approfondie (Agent 4 / Project M). **PR docs-only — 0 spend ici.** Spend futur = juge agent sous [`risk-limits.md`](risk-limits.md) (pas d’auth opérateur par dépense).  
Langue : FR. Date : **2026-11-21**.  
Source shortlist : [`game-discovery-p2e.md`](game-discovery-p2e.md). Préférences : multi-chaîne OK ; self-spend sous caps ; ne pas tuer un vecteur *seulement* parce que le 2×/30 j est lent.

**Légende** : Track **A** = bots/API ; Track **B** = humain + assist IA (sans injection d’inputs non autorisée). Verdicts : **GO** · **WATCH** · **NO**.

---

## Résumé exécutif

| # | Jeu | Chaîne | A | B | Fit ~200 € / 2×30 j | Pilote ? |
|---|-----|--------|---|---|---------------------|----------|
| 1 | [MoltStation](https://www.moltstation.games) | Base | **WATCH** | **NO** (humain hors rewards) | Faible (0 claims, liq. morte, gas) | **#2** smoke API 0-spend → gas later |
| 2 | [Olderfall](https://play.olderfall.com/) | Polygon (+ Immutable Play) | **NO** | **WATCH** | Faible (top ranks USDC, temps) | Non capital ; B optionnel |
| 3 | [Cambria](https://cambria.gg/) | Base (+ saisons Ronin) | **NO** | **WATCH** | Négatif attendu si Energy payante | **Kill spend** Risk Pool |
| 4 | [RavenQuest](https://ravenquest.io/) | Immutable zkEVM | **NO** | **WATCH** | Faible (grind + QUEST −99 % ATH) | Non |
| 5 | [Ashen Throne](https://ashenthrone.com/) | Base / Robinhood Chain | **WATCH** (MCP officiel) | **WATCH→GO** léger | Faible € (prix petits) mais F2P + rails vérifiés | **#1** F2P + MCP |

**Aucun GO capital** (raisons EV / ToS / liquidité — pas « attendre auth opérateur »). Recommandation pilote (temps / 0 €) : **Ashen Throne** puis **MoltStation** (lecture API + docs ; gas/claim seulement si EV prouvée sous caps V-13, juge agent). Journal : [`ops/ledgers/V-13.md`](../ops/ledgers/V-13.md). Pilote Day-0 Ashen : [`pilots/ashen-throne.md`](pilots/ashen-throne.md).

---

## 1. MoltStation

### 1.1 Qu’est-ce que c’est

Arcade **agent-native** sur **Base** : ShellRunners + Flappy Bots. Agents mint Identity NFT, jouent via WebSocket (`source:"agent_api"`), snapshot score on-chain, claim **$MOLTS** via Rewards V2.

### 1.2 Rails earn / cashout

| Étape | Mécanique |
|-------|-----------|
| Play | Session `agent_api` → WS inputs (dir / FLAP) |
| Score | `POST /api/rewards/snapshot` + tx `snapshotScoreSigned` (gas) |
| Claim | Readiness (cooldown, daily/weekly mint remaining) → `payoutClaim` → `$MOLTS` |
| Exit | Swap MOLTS/WETH Uniswap V4 Base (si liquidité) |

`browser_ws` = practice **sans** rewards.

### 1.3 Bots / API / ToS

API **officielle** agents : docs + `SKILL.md` + `/api/*/agent-instructions`. Pas de ban bots — c’est le produit. Contrats publics Basescan (Identity, Rewards V2, MOLTS Clanker).

### 1.4 Capital nécessaire

- Entry : mint Identity + gas snapshot/payout (Base ETH) — ordre de grandeur **quelques €** si actif, **0 €** pour GET docs/API.
- Pas de stake USDC ; risque = gas perdu + illiquidité MOLTS.

### 1.5 Liquidité / scam signals

| Signal | Observation | Source |
|--------|-------------|--------|
| Payouts live | **0** claims / **0** used from 40B rewards pool (snapshot site) | [moltstation.games](https://www.moltstation.games) |
| MOLTS pool | ~$22k liq., **$0** vol 24h, ~27 holders, GT score ~32 | [GeckoTerminal](https://www.geckoterminal.com/base/pools/0xfc7e7134f7c432926aff0ba62b828354c3a186358f8d1ed48518dd2070fa06ab) · [DexScreener](https://dexscreener.com/base/0xfc7e7134f7c432926aff0ba62b828354c3a186358f8d1ed48518dd2070fa06ab) |
| Docs / contrats | Complets, adresses publiées, API online | [docs](https://docs.moltstation.games/getting-started/quick-start-agent.html) · [contracts](https://docs.moltstation.games/smart-contracts/contract-by-contract-reference.html) |
| Âge | Pool ~7–8 mois ; économie rewards **non prouvée** | DEX |

**Anti-scam** : pas un site clone évident ; **mais** économie morte (0 payouts + volume nul) = risque « toy / ghost economy », pas rug classique.

### 1.6 Fit Agent 4

Seul nouveau path **Track A explicite** hors Clash. Multi-chaîne OK (Base). Ne tue pas pour lenteur 30 j — **mais** sans claims ni volume, EV attendue ≈ 0.

### 1.7 Verdicts

| Track | Verdict | Pourquoi |
|-------|---------|----------|
| **A** | **WATCH** | API + payout documentés ; EV/liquidité non prouvées |
| **B** | **NO** | Humain browser = practice only (pas de rewards) |

**Kill** : continue 0 claims après smoke **ou** honeypot / admin mint abusif **ou** gas > valeur claim.

**Sources (≥2)** : [quick-start agent](https://docs.moltstation.games/getting-started/quick-start-agent.html) · [SKILL.md](https://www.moltstation.games/skills/moltstation/SKILL.md) · [GeckoTerminal MOLTS](https://www.geckoterminal.com/base/pools/0xfc7e7134f7c432926aff0ba62b828354c3a186358f8d1ed48518dd2070fa06ab) · [site stats](https://www.moltstation.games)

---

## 2. Olderfall

### 2.1 Qu’est-ce que c’est

Auto-battler F2P browser/mobile (studio **Anubika**) : gladiateurs **Fallen** NFT, boucle prep → combat auto. Chaînes **Polygon** (+ présence Immutable Play / Moonbeam pour N3MUS). Social login, 1 Fallen gratuit.

### 2.2 Rails earn / cashout

| Voie | Détail |
|------|--------|
| N3MUS Weekly | ~**500 USDC** pool → top ranks (ex. top 75 selon édito PlayToEarn mai 2026) |
| N3MUS Quick Play | ~**250 USDC** vendredi |
| Immutable Play quests | Rewards engagement (pas USDC direct documenté ici) |
| Marketplace | NFT Fallen/gear → trade (pas cashout fiat auto) |
| $AURE / wAURE | Token natif planifié / en évolution — **pas** le rail cash principal aujourd’hui |

Claim N3MUS : register hub + wallet Sequence in-game → claim sur page tournoi (FAQ : *prize money available to claim*). Vérif wallet = signature message ; **pas de KYC documenté** dans FAQ N3MUS.

### 2.3 Bots / API / ToS

- Pas d’API bot play officielle.
- Combat déjà « auto » après setup humain ; automation externe / multi-account = cible anti-cheat N3MUS (BGA : AI anti-cheat bots/smurfing).
- Marketplace Sequence : interdiction robots/scraping (ToS marketplace) — pas une permission bot jeu.

→ Track A = **NO**.

### 2.4 Capital nécessaire

- **0 €** pour jouer F2P.
- Optionnel : NFT/gear/Battle Pass pour accélérer — hors GO tant qu’EV non prouvée (juge agent).
- Temps : grind Deathmatch pour points tournoi (seul mode qui compte N3MUS).

### 2.5 Liquidité / scam signals

| Signal | Observation | Source |
|--------|-------------|--------|
| Studio | Anubika, 2–3 ans build, BGA / Immutable collab PR mars 2026 | [PR Newswire](https://www.prnewswire.com/news-releases/immutable-and-olderfall-announce-launch-of-olderfall-on-immutable-play-bringing-quest-rewards-to-a-competitive-auto-battler-302713110.html) · [anubika.com](https://anubika.com/portfolio) |
| USDC tournois | Documentés Games.gg + PlayToEarn + Reddit officiel | [games.gg](https://games.gg/news/olderfall-season-1-launches/) · [PlayToEarn mai 2026](https://playtoearn.com/news/5-pvp-games-making-players-money-right-now-may-2026) |
| Contrepartie | Payouts via **tiers N3MUS** (claim page) — trust = historique tournois + anti-cheat | [N3MUS FAQ](https://n3mus.gitbook.io/docs/product-documentation/faq) |
| Revue tierce | CryptoGames nov 2026 : live, F2P, PEGI 18 / betting features à surveiller | [cryptogames.gg](https://cryptogames.gg/olderfall-review-is-the-free-auto-battler-worth-playing/) |

**Anti-scam** : projet réel triangulé. Risques = compétition ladder (EV bas pour new), dépendance N3MUS, éventuel drift gambling/betting.

### 2.6 Fit Agent 4

F2P + USDC = aligné prefs multi-chaîne / 0 stake. Mais **temps humain** élevé pour top ranks d’un pool ~500–750 USDC/sem. Pas un bot agent. OK comme vecteur lent si ranking vs autres agents compte.

### 2.7 Verdicts

| Track | Verdict | Pourquoi |
|-------|---------|----------|
| **A** | **NO** | Pas d’API bot ; anti-cheat N3MUS |
| **B** | **WATCH** | Plans/loadouts hors client OK ; cashout USDC réel mais EV temps faible |

**Kill** : N3MUS arrête USDC **ou** KYC bloquant **ou** betting payant obligatoire.

**Sources (≥2)** : [PlayToEarn](https://playtoearn.com/news/5-pvp-games-making-players-money-right-now-may-2026) · [Immutable PR](https://www.prnewswire.com/news-releases/immutable-and-olderfall-announce-launch-of-olderfall-on-immutable-play-bringing-quest-rewards-to-a-competitive-auto-battler-302713110.html) · [N3MUS tournaments](https://n3mus.gitbook.io/docs/product-documentation/n3mus-tournaments) · [games.gg Season 1](https://games.gg/news/olderfall-season-1-launches/)

---

## 3. Cambria (Gold Rush / Dungeons)

### 3.1 Qu’est-ce que c’est

Browser MMORPG / risk-to-earn (**Cambria**) : brûler **Energy** hors safe zone → loot Artifacts → Credits → Silver (peg USDC) → withdraw. Mentionné DappRadar « best of 2025 ». Base (+ historique saisons Ronin/ETH).

### 3.2 Rails earn / cashout

```
USDC/Silver → Energy Orb (~$3 / 100k Energy)
  → burn hors ville → Artifacts
  → cash-in Treasury → Credits
  → Risk Pool convert (1 % haircut) → Silver
  → withdraw USDC
```

| Règle Risk Pool | Valeur |
|-----------------|--------|
| Peg | 10 000 Silver = 1 USDC |
| Convert min | $1 (10k Silver) |
| Pool floor | ≥ $10k pour convertir |
| Soft caps | si pool &lt; $20k : plafond perso 50 % energy 24h + $100, + caps globaux/heure |
| Funding | 97 % energy brûlé → pool ; 3 % rake ; starter free orb **n’alimente pas** |

Burn T2 ≈ **$5,4/h** ; T6 jusqu’à **~$108/h** risk nominal (docs). EV = skill + loot vs burn + rake + haircut + death loss Artifacts.

### 3.3 Bots / API / ToS

- Islands : multi-account / **botting** → ban + forfeiture.
- Duel Arena : botting rewards → ban / discount EP.
- Security : exploits / leaderboard abuse → ineligibility.
- Pas d’API agent play.

→ Track A = **NO**.

### 3.4 Capital nécessaire

- Free starter orb limité ; jeu sérieux = **achat Energy** (USDC/Silver).
- Expose immédiatement le NAV sous risk-limits (cap V-13 ; **0 € Energy** tant qu’EV Risk Pool non prouvée — juge agent, pas auth opérateur).
- Fit 200 € : quelques orbs = perte rapide si EV négative.

### 3.5 Liquidité / scam signals

| Signal | Observation | Source |
|--------|-------------|--------|
| Docs économie | Risk Pool + Silver/Credits très documentés | [wiki Risk Pool](https://wiki.cambria.gg/w/Risk_Pool) · [docs Floating Risk Pool](https://docs.cambria.gg/genesis-misc/floating-risk-pool) · [Silver/Credits](https://docs.cambria.gg/l0-economic-engine/silver-credits-and-energy) |
| Crédibilité | Bug bounties **$85k+** payés ; DappRadar 2025 | [security](https://docs.cambria.gg/genesis-misc/security-and-game-integrity) · [DappRadar](https://dappradar.com/blog/best-nft-and-crypto-games-in-web3-from-2025) |
| Nature | **Parimutuel / risk-to-earn** — peers fund winners ; EV peut être négative | Docs |
| Resets | Pool reset si patch change Gold-earning efficiency | Floating Risk Pool docs |

**Anti-scam** : projet sérieux. Risque = **perte de stake Energy**, pas rug site.

### 3.6 Fit Agent 4

Cashout USDC le plus clair du top 5 — **mais** exige spend Energy + skill + downside. V-13 reste **0 € stake** tant qu’EV négative attendue / non mesurée (juge agent sous risk-limits). Ne pas piloter capital.

### 3.7 Verdicts

| Track | Verdict | Pourquoi |
|-------|---------|----------|
| **A** | **NO** | Botting banni |
| **B** | **WATCH** | Assist stratégie/extraction OK ; Energy spend seulement si EV + caps OK (juge agent) |

**Kill** : toute allocation Energy sans journal ledger **ou** EV nette négative après N sessions **ou** pool &lt; floor convert.

**Sources (≥2)** : [wiki Risk Pool](https://wiki.cambria.gg/w/Risk_Pool) · [docs Silver/Credits](https://docs.cambria.gg/l0-economic-engine/silver-credits-and-energy) · [Floating Risk Pool](https://docs.cambria.gg/genesis-misc/floating-risk-pool) · [DappRadar 2025](https://dappradar.com/blog/best-nft-and-crypto-games-in-web3-from-2025)

---

## 4. RavenQuest

### 4.1 Qu’est-ce que c’est

MMORPG pixel (Ravendawn Eternal Studios) sur **Immutable zkEVM** (+ QUEST aussi ETH). Fame → weekly $QUEST chests ; Silver ↔ QUEST P2P ; land/guild systems. Live ops + whitepaper earn.

### 4.2 Rails earn / cashout

| Étape | Détail |
|-------|--------|
| Earn | Fame (activités) × Renown → chest mardi ; Guild Fame ; Silver→QUEST exchange |
| Gate | **Legacy Level 15** + **Withdraw Pass** one-time (prix en QUEST, ex. ~182 QUEST snapshot guide — flotte avec marché) |
| Flow | Game QUEST → Website Balance → Immutable Passport (≥ 50 QUEST) → DEX |
| Anti-bot | Pass + AnyBrain.gg anti-cheat |

### 4.3 Bots / API / ToS

ToS / misconduct **explicites** : bots, macros, trainers, client mods **interdits** ; bénéfice indirect de bots = sanction ; guilds responsables. → Track A = **NO**.

### 4.4 Capital nécessaire

- Client/Epic temps lourd ; Withdraw Pass = dépense QUEST (ou grind puis auto-buy).
- Working capital éventuel pour land/gear — hors petit NAV.
- Temps jusqu’à Legacy 15 = friction majeure vs 30 j.

### 4.5 Liquidité / scam signals

| Signal | Observation | Source |
|--------|-------------|--------|
| Prix QUEST | ~**$0,00078** ; mcap ~**$390k** ; ATH ~$0,13 (**−99,4 %**) | [CoinGecko](https://www.coingecko.com/en/coins/ravenquest/) · [Bybit price](https://www.bybit.com/en/price/ravenquest/) |
| DEX | QuickSwap V3 IMX QUEST/USDC ~$360k liq. / ~$1,6k vol 24h | [GeckoTerminal](https://www.geckoterminal.com/immutable-zkevm/pools/0xbe2930d274f862542740dcdc95257b3163172343) |
| ToS | Liquidité **non garantie** | [ravenquest.io/terms](https://ravenquest.io/en/terms-of-service) |
| Studio LP | Annonce historique $500k LP TGE | [Peakd / studio](https://peakd.com/hive-148441/@shinoxl/tge-party-in-ravencrest) |
| Trustpilot | Plaintes ban Rule 8.2 (bots) — signal enforcement réel | [Trustpilot](https://www.trustpilot.com/review/ravenquest.io) |

**Anti-scam** : jeu réel, token **high-risk / illiquide retail**. Pas un faux site ; économie extractive difficile pour new F2P.

### 4.6 Fit Agent 4

Grind + pass + token dump = mauvais fit 200 € / autonomie agent. Contenu V-07 possible ; cashout faible.

### 4.7 Verdicts

| Track | Verdict | Pourquoi |
|-------|---------|----------|
| **A** | **NO** | ToS bots |
| **B** | **WATCH** | Assist guides OK ; earn→cashout lent + token fragile |

**Kill** : pass obligatoire sans EV **ou** volume QUEST &lt;&lt; taille withdraw **ou** ban automation dérive.

**Sources (≥2)** : [whitepaper earn](https://whitepaper.ravenquest.io/economy/a-simple-and-accessible-earning-model) · [GAM3S withdraw guide](https://gam3s.gg/ravenquest/guides/ravenquest-guide-how-to-withdraw-and-sell-quest-tokens/) · [ToS](https://ravenquest.io/en/terms-of-service) · [CoinGecko QUEST](https://www.coingecko.com/en/coins/ravenquest/)

---

## 5. Ashen Throne

### 5.1 Qu’est-ce que c’est

4X / war strategy MMO **browser F2P** (alpha) : Crawler mobile, extractions, sièges Citadel. Alliance Siege Cup hebdo. Studio indie (Andrew Chou) ; pas de paid marketing revendiqué.

### 5.2 Rails earn / cashout

| Époque | Rail |
|--------|------|
| Preseason / Cup USDC | USDC sur **Base** ; log payout public + tx hash |
| Weekly Cup récent | **USDG** sur **Robinhood Chain** ; min payout **$5** ; batch signé treasury |
| Futur annoncé | Prizes en **$THRONE** locked/vesting 90 j (Prize Lock) — illiquidité + unstake 7 j |

Mécanique : alliance capture/hold districts → split base % + contribution (power détruit + garrison). Éligibilité basse (1 siege ou temps garrison). Fair-play review 48 h. Multi-account / win-trade = void.

Exemples publics : preseason **27 joueurs / ~$96 USDC** ; Cup août 2026 **$1 000** ; cups oct ~**$50–90** USDG (tweets / PlayToEarn).

### 5.3 Bots / API / ToS

- ToS (2026-05-05) : *bots, macros, unauthorized scripts… unfair automation* **interdits**.
- **MCP officiel** (`https://mcp.ashenthr.one/mcp`) : ChatGPT/Claude/agents OAuth ; read default ; **act** = permission séparée + confirmation stakes ; STOP in-game ; pas de standing unattended orders.
- Guide MCP : *not an unattended server bot*.

→ Track A unattended = **NO** ; Track A via **MCP officiel** = **WATCH** ; Track B (read + plans + act confirmé) = **WATCH→GO** léger.

### 5.4 Capital nécessaire

- **0 €** play + Cup.
- Wallet vérifié pour recevoir ; bridge USDG/Robinhood → ETH = friction multi-chaîne (OK prefs, pas free).
- VIP Growth Status optionnel (limites MCP plus hautes) — non requis pour pilote 0-spend.

### 5.5 Liquidité / scam signals

| Signal | Observation | Source |
|--------|-------------|--------|
| Payouts | Log public + tx hash ; server ne custody pas ; human signs treasury | [docs payouts](https://ashenthrone.com/docs/events/payouts) · [PlayToEarn](https://playtoearn.com/news/1-000-in-usdc-rides-on-who-holds-the-last-city-on-earth) |
| Prix | Petits pools (~tens–low hundreds $/sem récemment) | Events / X |
| Alpha | Wipes / reward changes possibles | [ToS](https://ashenthrone.com/terms) |
| $THRONE | Staking → ASH only ; pas d’avantage combat Cup | [token overview](https://ashenthrone.com/docs/token/overview) |
| MCP | Différenciateur agent-friendly **officiel** | [mcp](https://ashenthrone.com/mcp) |

**Anti-scam** : triangulation OK (docs + PTE + on-chain logs). Risque = alpha, petite économie prize, migration USDG/$THRONE.

### 5.6 Fit Agent 4

Meilleur fit **temps/agent** du top 5 : F2P, MCP autorisé, payouts vérifiables, 0 stake. €/semaine trop petits pour 2× — **garder** comme vecteur lent / ranking (prefs). Contenu V-07 possible.

### 5.7 Verdicts

| Track | Verdict | Pourquoi |
|-------|---------|----------|
| **A** | **WATCH** | MCP officiel seulement ; pas bots non autorisés |
| **B** | **WATCH→GO** léger | Assist + MCP read/act confirmé = ToS-safe |

**Kill** : fin des cash prizes **ou** MCP retiré / ToS restreint act **ou** prize 100 % $THRONE illiquide sans exit.

**Sources (≥2)** : [payouts](https://ashenthrone.com/docs/events/payouts) · [event-rules](https://ashenthrone.com/event-rules) · [ToS](https://ashenthrone.com/terms) · [MCP](https://ashenthrone.com/mcp) · [PlayToEarn Cup](https://playtoearn.com/news/1-000-in-usdc-rides-on-who-holds-the-last-city-on-earth)

---

## 6. Comparaison & recommandation pilote

### 6.1 Matrice

| Critère | MoltStation | Olderfall | Cambria | RavenQuest | Ashen Throne |
|---------|-------------|-----------|---------|------------|--------------|
| Bot/API OK | Oui | Non | Non | Non | MCP oui |
| Cashout stable | MOLTS illiquide | USDC N3MUS | USDC Risk Pool | QUEST vol | USDC/USDG→$THRONE |
| Entry € | Gas | 0 | Energy $ | Pass+temps | 0 |
| Preuve payout | 0 claims | Éditos + claim | Docs + bounties | Live mais token dump | Log on-chain |
| Fit A4 autonome | Moyen | Faible | Faible | Faible | **Bon** (MCP) |

### 6.2 Pilotes recommandés (si / quand)

| Rang | Cible | Mode | Spend | Pourquoi |
|------|-------|------|-------|----------|
| **1** | **Ashen Throne** | Track B + MCP read (act seulement avec confirm humain) | **0 €** | Seul path agent-friendly + F2P + payouts vérifiés |
| **2** | **MoltStation** | Track A smoke : GET instructions / readiness ; **pas** de claim tant que 0 economy | **0 €** puis gas ≪ caps V-13 si EV OK | Unique API payout Base hors Clash ; EV à prouver |

**Ne pas piloter capital** (EV/ToS/risk) : Cambria Energy, RavenQuest pass/token, Olderfall NFT. Olderfall B F2P OK si temps dispo — priorité derrière Ashen. Micro-gas MoltStation = juge agent sous caps si claims deviennent réels.

### 6.3 Décisions autonomes

| Décision | Pourquoi | Annulation |
|----------|----------|------------|
| Aucun GO capital | Aucune EV triangulée ≥ coût/risque (pas attente auth opérateur) | Réouvrir après live claims + PnL sample ; spend = juge agent |
| Pilote #1 Ashen | MCP + F2P + logs | Opérateur refuse temps siege/alliance |
| Pilote #2 MoltStation docs/API | ToS A fort ; economy WATCH | 0 claims prolongés → abandon |
| Cambria / RQ hors spend | Risk Energy / token dump / ToS bots | Si EV + caps OK un jour → ledger + juge agent |

---

## 7. Sources (index)

| # | Source | Jeu |
|---|--------|-----|
| 1 | https://docs.moltstation.games/getting-started/quick-start-agent.html | MoltStation |
| 2 | https://www.moltstation.games/skills/moltstation/SKILL.md | MoltStation |
| 3 | https://www.geckoterminal.com/base/pools/0xfc7e7134f7c432926aff0ba62b828354c3a186358f8d1ed48518dd2070fa06ab | MoltStation MOLTS |
| 4 | https://playtoearn.com/news/5-pvp-games-making-players-money-right-now-may-2026 | Olderfall |
| 5 | https://www.prnewswire.com/news-releases/immutable-and-olderfall-announce-launch-of-olderfall-on-immutable-play-bringing-quest-rewards-to-a-competitive-auto-battler-302713110.html | Olderfall |
| 6 | https://n3mus.gitbook.io/docs/product-documentation/n3mus-tournaments | Olderfall / N3MUS |
| 7 | https://wiki.cambria.gg/w/Risk_Pool | Cambria |
| 8 | https://docs.cambria.gg/l0-economic-engine/silver-credits-and-energy | Cambria |
| 9 | https://docs.cambria.gg/genesis-misc/floating-risk-pool | Cambria |
| 10 | https://dappradar.com/blog/best-nft-and-crypto-games-in-web3-from-2025 | Cambria / RavenQuest |
| 11 | https://whitepaper.ravenquest.io/economy/a-simple-and-accessible-earning-model | RavenQuest |
| 12 | https://gam3s.gg/ravenquest/guides/ravenquest-guide-how-to-withdraw-and-sell-quest-tokens/ | RavenQuest |
| 13 | https://ravenquest.io/en/terms-of-service | RavenQuest |
| 14 | https://www.coingecko.com/en/coins/ravenquest/ | RavenQuest QUEST |
| 15 | https://ashenthrone.com/docs/events/payouts | Ashen Throne |
| 16 | https://ashenthrone.com/terms | Ashen Throne |
| 17 | https://ashenthrone.com/mcp | Ashen Throne |
| 18 | https://playtoearn.com/news/1-000-in-usdc-rides-on-who-holds-the-last-city-on-earth | Ashen Throne |
| 19 | https://cryptogames.gg/olderfall-review-is-the-free-auto-battler-worth-playing/ | Olderfall |
| 20 | https://docs.cambria.gg/genesis-misc/security-and-game-integrity | Cambria |

*Consulté 2026-11-21. Re-vérifier avant prêt / actif / spend.*
