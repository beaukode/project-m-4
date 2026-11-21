# Deep-study complet — tous les candidats discovery P2E

Étude exhaustive (Agent 4 / Project M). **PR docs-only — 0 spend ici.** Spend futur = juge agent sous [`risk-limits.md`](risk-limits.md).  
Langue : FR. Date : **2026-11-21**.  
Source : [`game-discovery-p2e.md`](game-discovery-p2e.md). Top 5 détaillé : [`game-deep-study-top5.md`](game-deep-study-top5.md) (**réutilisé** ; refresh spot-check ci-dessous).

**Légende verdict** (assignation) : **GO** · **TRACK B** · **NO** · **DEFER**  
Track **A** = bots/API ToS-safe ; Track **B** = humain + assist IA (sans injection d’inputs).  
Capital **NO** seulement pour EV / ToS / scam — pas pour « attendre auth opérateur ». Multi-chaîne OK.

---

## Résumé exécutif

| Compteur | Valeur |
|----------|--------|
| Entrées shortlist (#1–#12) | **12** |
| Mentions filtrées (noms distincts) | **11** |
| Déjà couverts (hors shortlist, pointeurs) | **2** (Pawtato, Clash) |
| **Total étudiés** | **25** |
| **GO capital** | **0** |
| **GO temps / 0 €** (recommandés) | Ashen Throne (MCP) ; MoltStation smoke API |

### Matrice shortlist (12)

| # | Titre | Chaîne | A | B | Verdict | Capital | EV / 30 j | Next |
|---|-------|--------|---|---|---------|---------|-----------|------|
| 1 | MoltStation | Base | DEFER | NO | **DEFER** | gas ≪ caps | ≈0 (0 claims) | Smoke GET API |
| 2 | Olderfall | Polygon (+ Immutable) | NO | TRACK B | **TRACK B** | 0 F2P | Faible (ladder) | Plans loadout |
| 3 | Cambria | Base (+ Ronin) | NO | TRACK B | **TRACK B** | Energy $ | Nég. si burn | **Kill spend** Energy |
| 4 | RavenQuest | Immutable zkEVM | NO | TRACK B | **TRACK B** | Pass+temps | Faible (QUEST −99 %) | Guides only |
| 5 | Ashen Throne | Base / Robinhood | DEFER (MCP) | **GO** léger | **GO** (temps) | 0 F2P | Faible € / Cup | Phase 2 compte+MCP |
| 6 | Photo Finish Live | Solana | NO | TRACK B | **TRACK B** | Wager DERBY | Nég. sans edge | Géo/KYC puis manuel |
| 7 | Parallel TCG | ETH + Base | NO | NO | **NO** | NFT >> 200 € | Négligeable | Fermé capital |
| 8 | Reworth Games | Base | NO | DEFER | **DEFER** | 0 F2P | Inconnu | Preuve payouts |
| 9 | SolFarmer | Solana | NO | NO | **NO** | Dépôt treasury | Scam/trust | Fermé |
| 10 | ClawArcade | Solana | DEFER | NO | **DEFER** | ~0 | Micro-pools | Tx payout on-chain |
| 11 | Cryptrix | Arc (USDC) | NO | NO | **NO** | Stake 0,5–5 USDC | EV− rake | Site 404 |
| 12 | Arcade Cafe / x402 chance | Solana / Base | NO | NO | **NO** | Wager USDC | EV− house | Fermé gambling |

### Mentions filtrées (11)

| Titre | Verdict | Pourquoi 1 ligne |
|-------|---------|------------------|
| HYTOPIA | **DEFER** | Services **paused** (funding) |
| WhisperDark | **TRACK B** | Demo spend x402 ; pas rail earn |
| GateQuake | **NO** | Stake BR / pot = gambling |
| BR1: INFINITE | **NO** | Pay-to-spawn / kill-to-earn |
| Agent Poker | **DEFER** | Agent OK mais **devnet** |
| Solana Bird (Finchb) | **NO** | Yield-like jeune / trust faible |
| Pixels | **TRACK B** | PIXEL live ; bots NO ; grind |
| World of Dypians | **TRACK B** | WOD/CEX ; grind faible |
| Football Fun → Sport.fun | **TRACK B** | USDC Pro geo ; bots ban |
| The Sandbox | **NO** (A) | Bots interdits ; events KYC |
| RollerCoin | **NO** | Bots/macros ToS ban |

### Déjà couverts (pointeurs)

| Titre | Doc | Verdicts |
|-------|-----|----------|
| Pawtato Land | [`game-targets-pawtato-clash.md`](game-targets-pawtato-clash.md) | A **NO** · B **TRACK B** |
| Clash of Coins | idem | A+B **DEFER** (WATCH) · pas GO capital |

### Next pilots (après full pass)

| Rang | Cible | Mode | Spend | Pourquoi |
|------|-------|------|-------|----------|
| **1** | **Ashen Throne** | Track B + MCP officiel | **0 €** | Seul GO temps : F2P + payouts on-chain + MCP |
| **2** | **MoltStation** | Track A smoke docs/API | **0 €** (gas later si EV) | API payout Base ; économie toujours 0 claims |
| **3** | **ClawArcade** | Track A guest → verified | **0 €** | Agent-native Solana ; attendre preuve payout SOL |
| **4** | **Olderfall** | Track B F2P | **0 €** | USDC N3MUS réel ; EV temps |
| **5** | **Reworth** | Track B F2P probe | **0 €** | USDC Base si payouts prouvés |

**Ne pas piloter capital** : Cambria Energy, RavenQuest pass, Parallel NFT, Photo Finish wager, SolFarmer dépôt, Cryptrix stake, Arcade/x402, GateQuake/BR1, Finchb.

Journal : [`ops/ledgers/V-13.md`](../ops/ledgers/V-13.md).

---

## Refresh top 5 (sources inchangées → verdicts inchangés)

Spot-check **2026-11-21** :

| Jeu | Signal live | Change vs [`game-deep-study-top5.md`](game-deep-study-top5.md) |
|-----|-------------|----------------------------------------------------------------|
| MoltStation | Site : **0** payout claims / 0 % pool 40B ; MOLTS pool ~$22k liq., **$0** vol 24h ([GeckoTerminal](https://www.geckoterminal.com/base/pools/0xfc7e7134f7c432926aff0ba62b828354c3a186358f8d1ed48518dd2070fa06ab)) ; API Online | **Aucun** — DEFER A |
| Olderfall | Collab Immutable + N3MUS USDC toujours documentés | **Aucun** — TRACK B |
| Cambria | Risk Pool docs inchangés | **Aucun** — TRACK B ; kill Energy |
| RavenQuest | QUEST ~**$0,00078** ; mcap ~$390k ; ATH −**99,4 %** ([CoinGecko](https://www.coingecko.com/en/coins/ravenquest/)) | **Aucun** — TRACK B faible |
| Ashen Throne | MCP + payouts docs live ; Cup → USDG / $THRONE Prize Lock ([payouts](https://ashenthrone.com/docs/events/payouts)) | **Aucun** — GO temps (0 €) |

Détail inchangé → sections 1–5 de [`game-deep-study-top5.md`](game-deep-study-top5.md). Ci-dessous : notes compactes + deep-dives **#6–#12** + filtrés.

---

## Notes compactes — top 5 (réutilisation)

### 1. MoltStation — **DEFER**

| Champ | Contenu |
|-------|---------|
| Chaîne | Base |
| Earn | Score `agent_api` → snapshot → claim **$MOLTS** (Rewards V2) |
| Bots | **Oui** (produit) — [`quick-start`](https://docs.moltstation.games/getting-started/quick-start-agent.html) · [SKILL.md](https://www.moltstation.games/skills/moltstation/SKILL.md) |
| Liquidité | 0 claims ; MOLTS illiquide ($0 vol) |
| Capital | 0 pour smoke ; gas mint/snapshot si actif |
| EV | ≈ 0 tant qu’économie morte |
| Next | GET agent-instructions / readiness ; **pas** claim |
| Kill | 0 claims prolongés **ou** honeypot |

### 2. Olderfall — **TRACK B**

| Champ | Contenu |
|-------|---------|
| Chaîne | Polygon (+ Immutable Play) |
| Earn | Tournois **N3MUS USDC** (~500–750 $/sem pools) |
| Bots | **Non** (anti-cheat N3MUS) |
| Capital | 0 F2P |
| EV | Faible hors top ranks |
| Next | Assist loadouts hors client |
| Sources | [PlayToEarn](https://playtoearn.com/news/5-pvp-games-making-players-money-right-now-may-2026) · [Immutable PR](https://www.prnewswire.com/news-releases/immutable-and-olderfall-announce-launch-of-olderfall-on-immutable-play-bringing-quest-rewards-to-a-competitive-auto-battler-302713110.html) |

### 3. Cambria — **TRACK B** (NO spend)

| Champ | Contenu |
|-------|---------|
| Chaîne | Base |
| Earn | Energy → loot → Credits → Silver → **USDC** Risk Pool |
| Bots | **Bannis** ([security](https://docs.cambria.gg/genesis-misc/security-and-game-integrity)) |
| Capital | Energy payante = risque NAV |
| EV | Négative attendue sans skill prouvé |
| Next | **0 € Energy** ; plans extraction only |
| Sources | [wiki Risk Pool](https://wiki.cambria.gg/w/Risk_Pool) · [Floating Risk Pool](https://docs.cambria.gg/genesis-misc/floating-risk-pool) |

### 4. RavenQuest — **TRACK B**

| Champ | Contenu |
|-------|---------|
| Chaîne | Immutable zkEVM |
| Earn | Fame → QUEST chests ; withdraw pass Legacy 15 |
| Bots | **ToS NO** ([terms](https://ravenquest.io/en/terms-of-service)) |
| Capital | Pass + grind |
| EV | Token dump + temps |
| Next | Contenu V-07 ; pas withdraw pass |
| Sources | [whitepaper](https://whitepaper.ravenquest.io/economy/a-simple-and-accessible-earning-model) · [CoinGecko](https://www.coingecko.com/en/coins/ravenquest/) |

### 5. Ashen Throne — **GO** (temps / 0 €)

| Champ | Contenu |
|-------|---------|
| Chaîne | Base (hist. USDC) / Robinhood USDG / $THRONE lock |
| Earn | Alliance Cup ; min $5 ; log on-chain |
| Bots | Non-MCP **interdits** ; **MCP officiel** OK ([mcp](https://ashenthrone.com/mcp)) |
| Capital | 0 F2P ; pas VIP / pas buy $THRONE |
| EV | €/sem petits ; rang multi-mois OK |
| Next | Phase 2 compte + MCP read ([`pilots/ashen-throne.md`](pilots/ashen-throne.md)) |
| Sources | [payouts](https://ashenthrone.com/docs/events/payouts) · [ToS](https://ashenthrone.com/terms) · [PlayToEarn](https://playtoearn.com/news/1-000-in-usdc-rides-on-who-holds-the-last-city-on-earth) |

---

## 6. Photo Finish Live — **TRACK B**

### Quoi
Courses hippiques virtuelles **argent réel** (Third Time Games). Live post–Beta 3. Solana USDC ↔ **DERBY** (80 DERBY = $1 fixe, custodial). **$CROWN** = utilité staking pistes (séparé).

### Earn / cashout
Dépôt USDC/carte → DERBY → races/picks/breeding → withdraw **USDC Solana** ([docs DERBY](https://thirdtimegames.com/docs/ecosystem/derby/) · [HappyFox withdraw](https://thirdtimegames.happyfox.com/kb/article/19-how-long-do-derby-withdrawals-take/)). Frais historiques ~1 % retrait (Beta 3).

### Bots / ToS
**Interdits** — [photofinish.live/terms-of-service](https://photofinish.live/terms-of-service) : *bots, cheats, and hacks*. → Track A **NO**.

### Capital / EV / anti-scam
Picks dès ~1 $ ; stable « sérieux » souvent dizaines–centaines $ DERBY. Studio établi (Orlando). **21+** ; géo restreinte (France à valider). Modèle **wager/skill** → EV négative sans edge. CROWN DEX mince.

| Track | Verdict |
|-------|---------|
| A | **NO** |
| B | **TRACK B** (humain manuel seulement) |
| Global | **TRACK B** |

**Kill** : géo/KYC bloquant **ou** dépôt sans edge documenté.  
**Next** : vérifier éligibilité FR ; **0 €** tant qu’edge non prouvée.

**Sources** : [DERBY docs](https://thirdtimegames.com/docs/ecosystem/derby/) · [Beta 3](https://thirdtimegames.com/welcome-to-real-money-only-beta-3/) · [ToS](https://photofinish.live/terms-of-service) · [player-protection](https://photofinish.live/player-protection)

---

## 7. Parallel TCG — **NO**

### Quoi
TCG sci-fi F2P (Parallel / Echelon). Steam/mobile **2026** ; NFT cartes ETH/Base ; **PRIME** ; marketplace [Sanctuary](https://www.sanctuary.online/marketplace).

### Earn / cashout
Ranked wins → PRIME (caps daily ; deck 40 NFT + Battle Pass pour max) → claim Sanctuary → CEX/DEX. PRIME ~**$0,10–0,11** vs ATH >$15 → cashflow gameplay **négligeable** à taille retail.

### Bots / ToS
**Interdits** — [parallel.life/terms-of-use](https://parallel.life/terms-of-use) : bots / automation. Echelon slash bot rewards.

### Capital / EV
Jouer F2P = 0 $ ; earn sérieux = **centaines–milliers $** NFT + BP. **~200 € insuffisant**.

| Track | Verdict |
|-------|---------|
| A | **NO** |
| B | **NO** (EV cashout trop faible pour A4) |
| Global | **NO** |

**Sources** : [Echelon PRIME gameplay](https://docs.echelon.io/echelon-prime-foundation/2.0-prime-token/2.1-gameplay) · [ToS](https://parallel.life/terms-of-use) · [CoinGecko PRIME](https://www.coingecko.com/en/coins/echelon-prime) · [PlayToEarn mobile](https://playtoearn.com/news/parallel-tcg-lands-on-ios-and-android-app-stores-with-free-global-mobile-launch-after-five-years-of-development)

---

## 8. Reworth Games — **DEFER**

### Quoi
Hub browser Base ; leaderboards → prizes **USDC**. Early beta (« First 100 » fév. 2026 roadmap).

### Earn / cashout
Daily prize (montant **non publié**) → Balance custodiale → withdraw **USDC Base**, **manuel ≤ 7 j ouvrés** ([ToS §7.3](https://reworthgames.com/docs/terms-of-use)). Vault yield → prize reserve ([economy](https://reworthgames.com/docs/economy)).

### Bots / ToS
**Interdits** — ToS : *Cheating and Automation: Using bots, scripts, automation tools…*

### Capital / anti-scam
0 $ F2P ; VIP/Founder optionnels. Équipe opaque (« Protocol Team ») ; **aucune preuve tierce de payout** trouvée au check. Safes publiés à auditer on-chain avant trust.

| Track | Verdict |
|-------|---------|
| A | **NO** |
| B | **DEFER** (probe F2P 0 €) |
| Global | **DEFER** |

**Kill** : 0 preuve withdraw après probe **ou** custody opacity.  
**Next** : 1 session manuelle ; journaliser claim ; **pas** de dépôt.

**Sources** : [reworthgames.com](https://reworthgames.com/) · [ToS](https://reworthgames.com/docs/terms-of-use) · [economy](https://reworthgames.com/docs/economy)

---

## 9. SolFarmer — **NO**

### Quoi
Idle « mining » simulateur Solana → SOL withdraw (min **0,1 SOL** annoncé presse). Opérateur **anonyme** ; alpha.

### Earn / cashout
Balance = *« withdrawable share of the Platform's pooled treasury »* ([terms](https://solfarmer.io/terms) §6–7). Withdraw subject anti-fraud / **KYC possible**. Chance features : Lucky Boxes, Rivals wagers (§9).

### Bots / ToS
**Interdits** — §10 : *bots, scripts, automation, macros*.

### Anti-scam
[ScamAdviser](https://www.scamadviser.com/check-website/solfarmer.io) trust **0** ; WHOIS masqué. Proof-of-payouts : signaux contradictoires / non fiables. Dépôts alimentent treasury opérateur.

| Track | Verdict |
|-------|---------|
| A | **NO** |
| B | **NO** (trust + chance) |
| Global | **NO** |

**Sources** : [terms](https://solfarmer.io/terms) · [ScamAdviser](https://www.scamadviser.com/check-website/solfarmer.io) · [cryptogames.gg review](https://cryptogames.gg/solfarmer-review-is-the-solana-idle-mining-game-worth-it/) · [PlayToEarn](https://playtoearn.com/news/solfarmer-brings-real-sol-play-to-earn-to-a-cozy-solana-mining-world)

---

## 10. ClawArcade — **DEFER**

### Quoi
Arène **agent-native** Solana (Snake, Chess, …) — Colosseum hackathon. API Workers **up** (`/api/health` = ok, check 2026-11-21). Front [clawarcade.surge.sh](https://clawarcade.surge.sh/).

### Earn / cashout
Tournois highscore → parts **SOL** (pools micro, ex. Snake ~0,27 SOL). Guest = pas de prix ; prix = **Moltbook-verified** + wallet SOL ([bot-guide](https://clawarcade.surge.sh/bot-guide.html)). **Aucune preuve payout on-chain** trouvée.

### Bots / ToS
**Conçu pour bots** — WS join/move ; anti-cheat = détecter humains trop lents. Pas de stake room.

### Capital / EV
~0 €. Pools microscopiques vs 2×. GitHub actif, 0 stars ; opérateur email GitHub.

| Track | Verdict |
|-------|---------|
| A | **DEFER** (smoke OK ; GO après 1 tx payout) |
| B | **NO** (humain hors produit) |
| Global | **DEFER** |

**Next** : guest bot smoke → verified → documenter 1 payout SOL.  
**Kill** : pools mortes **ou** non-paiement.

**Sources** : [GitHub](https://github.com/Omnivalent/clawarcade) · [bot-guide](https://clawarcade.surge.sh/bot-guide.html) · API health live

---

## 11. Cryptrix — **NO**

### Quoi
Agents **Cache Rush** sur **Arc** (USDC stake rooms). Repo OSS ([Sacura1/cryptrix](https://github.com/Sacura1/cryptrix)).

### Earn / cashout
Mise **0,5–5 USDC**/siège ; pool − **1 %** fee ; top 3 60/25/15 %. EV médiane **négative** (rake + majority losers).

### Statut live
**2026-11-21** : `cryptrix.app`, `/guide`, `/api/agent.md` → **HTTP 404**. Prod morte.

### Bots
Agent API documentée (quand live) — mais **gambling stake**.

| Track | Verdict |
|-------|---------|
| A | **NO** (EV− stake même si API) |
| B | **NO** |
| Global | **NO** (réouvrir **DEFER** si prod + liq. sans EV−) |

**Sources** : [GitHub](https://github.com/Sacura1/cryptrix) · [arc-mainnet.json](https://github.com/Sacura1/cryptrix/blob/main/docs/deployments/arc-mainnet.json) · curl 404 live

---

## 12. Arcade Cafe / x402 chance — **NO**

### Quoi
[Arcade Cafe](https://arcade.cafe/docs) = protocole arcade **x402** (agents + house LP) ; jeux type Dice / Sweeper = **wager**. [play.0000402.xyz](https://play.0000402.xyz/) = lottery Base (~0,10 USDC → chance 1 USDC).

### Earn
House/LP ou jackpot chance — **pas** grind skill P2E. EV house négative pour le joueur.

### Bots
Agents **attendus** sur le rail x402 — mais monétisation = **gambling**.

| Global | **NO** |

**Sources** : [arcade.cafe/docs](https://arcade.cafe/docs) · [play.0000402.xyz](https://play.0000402.xyz/)

---

## Mentions filtrées — fiches courtes

### HYTOPIA — **DEFER**
Metaverse Base ; earn creator. Homepage : **paused** 1–3 mois (funding). [hytopia.com](https://hytopia.com/) · [blog](https://blog.hytopia.com/2024/12/06/hytopia-the-next-generation/). Réouvrir si unpause + cashout clair.

### WhisperDark — **TRACK B**
Demo agent **spend** x402 (Neo X / COZ) ; pas de boucle earn NAV. [coz.io blog](https://www.coz.io/blog/whisperdark-infinity-room/) · [whisperdark.ngd.network](https://whisperdark.ngd.network/). Lab technique seulement.

### GateQuake — **NO**
Browser BR Solana ; stake USDC → pot. [gatequake.com](https://gatequake.com/) · [PlayToEarn](https://playtoearn.com/blockchaingame/gatequake). Gambling / PvP wager.

### BR1: INFINITE — **NO**
Pay-to-spawn / kill-to-earn ; withdraw USDC min documenté presse. [litepaper](https://litepaper.bravoready.com/br1-infinite-guide/br1-infinite-guide/br1-infinite-overview). Math bankroll ~200 € mauvaise.

### Agent Poker — **DEFER**
Heads-up NLHE WebSocket agents ; **devnet SOL** ; mainnet après audit. [agentpoker.io/docs](https://agentpoker.io/docs). Watch post-audit ; rake = EV− si real stakes.

### Solana Bird (Finchb) — **NO**
Wallet game yield-like ; jeune ; triangulation anti-scam insuffisante pour GO. [whitepaper](https://www.finchb.com/legal/whitepaper) · [bird.finchb.com](https://bird.finchb.com/).

### Pixels — **TRACK B**
Ronin MMO ; PIXEL withdraw (≥200 + rep). Grind humain ; bots non. [Task Board](https://help.pixels.xyz/en/articles/9165794-what-is-the-task-board). Contenu / assist only.

### World of Dypians — **TRACK B**
MMORPG + **WOD** (BSC) → CEX. Token loin ATH ; login grind. [egamers](https://egamers.io/games/world-of-dypians/).

### Football Fun → Sport.fun — **TRACK B**
Base ; Pro Gold↔USDC ; docs bannissent bots. [docs Gold/TP/$FUN](https://docs.sport.fun/en/article/understanding-gold-tournament-points-and-fun-b8l8s2/). Humain geo-gated.

### The Sandbox — **NO** (bots A)
Events SAND + KYC ; ToS **bots/automation** interdits. [Seasons FAQ](https://docs.sandbox.game/en/players/seasons-and-events/faqs-seasons-and-events) · [ToU](https://www.sandbox.game/en/terms-of-use/). Contenu V-07 seulement si opportuniste.

### RollerCoin — **NO**
Idle mining → crypto withdraw ; ToS **no bots/scripts/macros**. [terms](https://rollercoin.com/terms) · [legit blog](https://rollercoin.com/blog/is-rollercoin-legit).

---

## Décisions autonomes

| Décision | Pourquoi | Annulation |
|----------|----------|------------|
| Aucun GO capital sur 25 titres | EV / ToS / scam / gambling (pas attente auth) | Live claims + PnL sample sous caps |
| GO temps = Ashen seulement | MCP + F2P + payouts vérifiés | Opérateur refuse siege/alliance |
| DEFER MoltStation + ClawArcade | API OK ; économie / payouts non prouvés | Claims/tx on-chain → upgrade |
| NO SolFarmer / Cryptrix / Arcade / GateQuake / BR1 / Finchb / Parallel | Trust, EV−, stake, NFT gate | Nouvelles preuves externes |
| TRACK B Photo Finish | Rail USDC clair mais bots NO + wager | Edge + géo OK → micro-cap juge agent |
| DEFER Reworth / HYTOPIA / Agent Poker | Prod immature / paused / devnet | Preuve payout ou unpause |
| Mapping WATCH→DEFER / TRACK B | Alignement vocabulaire assignation | — |

---

## Sources (index complémentaire #6–filtrés)

| # | Source | Titre |
|---|--------|-------|
| 1 | https://thirdtimegames.com/docs/ecosystem/derby/ | Photo Finish DERBY |
| 2 | https://photofinish.live/terms-of-service | Photo Finish ToS |
| 3 | https://parallel.life/terms-of-use | Parallel bots |
| 4 | https://www.sanctuary.online/marketplace | Parallel Sanctuary |
| 5 | https://reworthgames.com/docs/terms-of-use | Reworth ToS |
| 6 | https://reworthgames.com/docs/economy | Reworth economy |
| 7 | https://solfarmer.io/terms | SolFarmer ToS |
| 8 | https://www.scamadviser.com/check-website/solfarmer.io | SolFarmer scam |
| 9 | https://clawarcade.surge.sh/bot-guide.html | ClawArcade API |
| 10 | https://github.com/Omnivalent/clawarcade | ClawArcade GH |
| 11 | https://github.com/Sacura1/cryptrix | Cryptrix |
| 12 | https://arcade.cafe/docs | Arcade Cafe x402 |
| 13 | https://hytopia.com/ | HYTOPIA paused |
| 14 | https://www.coz.io/blog/whisperdark-infinity-room/ | WhisperDark |
| 15 | https://gatequake.com/ | GateQuake |
| 16 | https://litepaper.bravoready.com/br1-infinite-guide/br1-infinite-guide/br1-infinite-overview | BR1 |
| 17 | https://agentpoker.io/docs | Agent Poker |
| 18 | https://www.finchb.com/legal/whitepaper | Finchb |
| 19 | https://help.pixels.xyz/en/articles/9165794-what-is-the-task-board | Pixels |
| 20 | https://docs.sport.fun/en/article/understanding-gold-tournament-points-and-fun-b8l8s2/ | Sport.fun |
| 21 | https://www.sandbox.game/en/terms-of-use/ | Sandbox |
| 22 | https://rollercoin.com/terms | RollerCoin |
| 23–42 | Voir index [`game-deep-study-top5.md`](game-deep-study-top5.md) §7 | Top 5 |

*Consulté / re-vérifié 2026-11-21. Re-vérifier avant prêt / actif / spend.*
