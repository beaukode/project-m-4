# Découverte P2E / Web3 / browser games

Scan large (Agent 4 / Project M). **Discovery only** — pas de deep-dive complet, **aucun spend**.  
Langue : FR. Date : **2026-11-21**.  
Préférences : multi-chaîne OK ; spend auto-jugé sous [`risk-limits.md`](risk-limits.md) ; ne pas tuer un vecteur lent *seulement* parce que le 2×/30 j est lent.

Exclus déjà couverts : Pawtato, Clash of Coins ([`game-targets-pawtato-clash.md`](game-targets-pawtato-clash.md)) · Lichess, Second Life, bandforband, PIVArena, ProfitPlay/OMERTÀ, monopoly.land ([`game-paths.md`](game-paths.md)).

---

## 1. Méthode

| Étape | Ce qui a été fait |
|-------|-------------------|
| Directories | [DappRadar Play2Earn rankings](https://dappradar.com/rankings/category/games-play2earn) ; éditos DappRadar ([Mars 2026](https://dappradar.com/blog/best-play-to-earn-crypto-nft-games), [2025](https://dappradar.com/blog/best-nft-and-crypto-games-in-web3-from-2025)) ; PlayToEarn (PvP cash [mai 2026](https://playtoearn.com/news/5-pvp-games-making-players-money-right-now-may-2026), cashout routes [août 2026](https://playtoearn.com/news/is-your-game-paying-you-the-top-5-apps-where-you-can-actually-cash-out), rankings [avril 2026](https://playtoearn.com/news/top-5-play-to-earn-games-to-earn-crypto-in-april-2026-full-rankings)) |
| Requêtes ciblées | `agentic game API` / bot mode ; `x402 game` ; `Sui/Base/Solana P2E browser cashout USDC` |
| Filtre A4 | Rail earn/cashout **explicite** ; bot/API **ou** jouable humain ; triage anti-scam (âge, liquidité/treasury, ToS gambling) |
| Hors scope | Deep-dive ToS ligne-à-ligne ; live probe wallets ; allocation capital |

**Triangulation** : chaque candidat a ≥ 2 sources (officiel / directory / revue tierce). Verdicts = **priorité découverte**, pas GO capital.

Légende priorité : **deep-study now** · **later** · **skip**

---

## 2. Shortlist (12 candidats)

| # | Candidat | Chaîne | Rail earn / cashout | Bot/API ou humain | Anti-scam (triage) | Pourquoi 1 ligne | Priorité |
|---|----------|--------|---------------------|-------------------|--------------------|------------------|----------|
| 1 | [MoltStation](https://www.moltstation.games) | Base | Snapshot → readiness → **payout** on-chain (Rewards V2) ; docs agent | **API agent officielle** (`source:"agent_api"`) | Docs publiques + contrat Identity Basescan ; âge / liquidity rewards à vérifier | Seul candidat fort « bot autorisé + payout » hors Clash | **deep-study now** |
| 2 | [Olderfall](https://play.olderfall.com/) | Polygon (+ Immutable Play) | Tournois **N3MUS USDC** (ex. ~500 USDC/semaine top ranks) ; marketplace Fallens | Humain (auto-battler browser/mobile) ; pas d’API bot connue | Studio Anubika + collab Immutable (PR 2026) ; tournois via tiers N3MUS | F2P browser, earn USDC documenté, hors stake-gambling pur | **deep-study now** |
| 3 | [Cambria](https://cambria.gg/) (Gold Rush / Dungeons) | Base (+ saisons Ronin) | Risk-to-earn → Credits/Silver → **USDC** (pool ≥ $10k ; limits si pool basse) | Humain browser MMORPG | Docs/wiki Risk Pool + couverture DappRadar 2025 ; EV négative possible | Cashout USDC le plus documenté côté skill/risk | **deep-study now** |
| 4 | [RavenQuest](https://ravenquest.io/) | Immutable zkEVM | Silver ↔ **$QUEST** ; withdraw pass + Passport wallet (Legacy 15) | Humain (MMORPG client/Epic) | Live ops + whitepaper earn model ; token vol / grind time | P2E « classique » mature, cashout token explicite | **deep-study now** |
| 5 | [Ashen Throne](https://ashenthrone.com/) | Base / Robinhood Chain (USDG prizes) | Cups alliance **USDC/USDG** ; log payout public (PlayToEarn) | Humain browser F2P | Prix petits ; chaîne prize à confirmer ; âge jeune | F2P + payout on-chain vérifiable, entrée 0 € | **deep-study now** |
| 6 | [Photo Finish Live](https://thirdtimegames.com/photo-finish-live/) | Solana | Courses **$DERBY** (80 = $1) → withdraw **USDC** ; $CROWN staking track | Humain (skill + breeding) | Studio établi Third Time ; gambling-adjacent (entry fees) | Rail fiat-like DERBY→USDC clair ; cap capital prudence | **later** |
| 7 | [Parallel TCG](https://dappradar.com/blog/best-play-to-earn-crypto-nft-games) | Ethereum + Base | Cartes NFT ERC-1155 → Sanctuary marketplace Base | Humain (TCG Steam/mobile, launch 2026) | Fondation Echelon / long build ; liquidité cartes | Skill + secondary market, pas idle farm | **later** |
| 8 | [Reworth Games](https://reworthgames.com/) | Base | Leaderboards quotidiens → **USDC** withdraw (claim site) | Humain browser F2P | Site marketing ; revenue « yield vault » non triangulé | Fit A4 (0 stake, Base USDC) **si** payouts prouvés | **later** |
| 9 | [SolFarmer](https://solfarmer.io/) | Solana | Idle hashrate → **SOL** withdraw (≥0,1 SOL) ; proof-of-payouts | Humain browser idle | Alpha anonyme ; ScamAdviser flags ; treasury opérateur | Cashout SOL public **mais** trust faible → pas now | **later** |
| 10 | [ClawArcade](https://github.com/Omnivalent/clawarcade) | Solana | Tournois **SOL** ; register agent 1 call | **API agent** WebSocket | Projet jeune / GitHub ; liquidity prize à vérifier | Agent-native hors Clash ; anti-scam d’abord | **later** |
| 11 | [Cryptrix](https://cryptrix.app/guide) | Arc (USDC) | Stake room → top-3 prize ; claim keeper | **API agent** (`/api/agent.md`) | Stake = perte possible ; chaîne Arc | Bot OK mais EV stake / gambling-like | **later** |
| 12 | [Arcade Cafe](https://arcade.cafe/) / [x402 chance](https://play.0000402.xyz/) | Solana / Base | x402 USDC play → settle | Agent HTTP 402 | Nature **wager / chance** | Rail agent intéressant, monétisation = gambling | **skip** |

### Mentions filtrées (pas shortlistés)

| Nom | Raison |
|-----|--------|
| HYTOPIA | Services **paused** (funding) — earn mort |
| WhisperDark (x402 Neo X) | Démo spend agent, pas rail earn |
| GateQuake / BR1: INFINITE / Agent Poker | Stake/extraction = gambling élevé ; BR1 invite-only |
| Solana Bird (Finchb) | Payouts publics OK mais wallet-game idle très jeune |
| Pixels / World of Dypians / Football Fun | Volume DappRadar ; rail earn flou / token-first sans cashout clair pour A4 |
| The Sandbox / RollerCoin | Connus ; creator/minigame — faible fit 2× ; option contenu V-07 seulement |

---

## 3. Deep-studies (top 5) — **fait**

Fiche : [`game-deep-study-top5.md`](game-deep-study-top5.md) (2026-11-21, **0 spend**).

| # | Jeu | A | B | Note 1 ligne |
|---|-----|---|---|--------------|
| 1 | MoltStation | **WATCH** | **NO** | API+payout OK ; 0 claims + MOLTS illiquide |
| 2 | Olderfall | **NO** | **WATCH** | USDC N3MUS réel ; bots non ; EV temps |
| 3 | Cambria | **NO** | **WATCH** | USDC Risk Pool clair ; **kill spend** Energy |
| 4 | RavenQuest | **NO** | **WATCH** | QUEST −99 % ATH ; bots ToS NO |
| 5 | Ashen Throne | **WATCH** (MCP) | **WATCH→GO** | F2P + payouts on-chain + MCP officiel |

**Pilotes recommandés (temps)** : #1 Ashen Throne · #2 MoltStation smoke API. Aucun GO capital.

Ne pas abandonner #2–#5 seulement parce que le ramp-up > 30 j — classer vs autres agents / vecteurs temps.

---

## 4. Décisions autonomes

| Décision | Pourquoi | Annulation |
|----------|----------|------------|
| 12 candidats (pas 15) | Filtre earn explicite + anti-scam a éliminé volume DappRadar « token only » | Ajouter une vague 2 directory si opérateur veut + volume |
| Skip x402 chance / Arcade Cafe | Gambling EV négative attendue | Réouvrir seulement si house-LP non-wager documenté |
| Pas de ledger capital | Discovery only | Notes deep-study → `ops/ledgers/V-13.md` (fait) |
| Multi-chaîne inclus | Préf opérateur | Restreindre L1 si prefs changent |
| Deep-study top 5 livré | Voir `game-deep-study-top5.md` | Réviser si EV live change |

---

## 5. Sources (index)

| # | Source | Usage |
|---|--------|-------|
| 1 | https://dappradar.com/rankings/category/games-play2earn | Directory volume |
| 2 | https://dappradar.com/blog/best-play-to-earn-crypto-nft-games | Édito Mars 2026 |
| 3 | https://dappradar.com/blog/best-nft-and-crypto-games-in-web3-from-2025 | Édito 2025 (Cambria, RavenQuest, …) |
| 4 | https://playtoearn.com/news/5-pvp-games-making-players-money-right-now-may-2026 | Olderfall / Parallel USDC |
| 5 | https://playtoearn.com/news/is-your-game-paying-you-the-top-5-apps-where-you-can-actually-cash-out | SolFarmer, BR1 cashout |
| 6 | https://docs.moltstation.games/getting-started/quick-start-agent.html | Agent API + payout |
| 7 | https://wiki.cambria.gg/w/Risk_Pool | Cambria USDC convert |
| 8 | https://www.prnewswire.com/news-releases/immutable-and-olderfall-announce-launch-of-olderfall-on-immutable-play-bringing-quest-rewards-to-a-competitive-auto-battler-302713110.html | Olderfall × Immutable |
| 9 | https://whitepaper.ravenquest.io/economy/a-simple-and-accessible-earning-model | RavenQuest earn |
| 10 | https://games.gg/ravenquest/guides/ravenquest-guide-how-to-withdraw-and-sell-quest-tokens/ | QUEST withdraw |
| 11 | https://playtoearn.com/news/1-000-in-usdc-rides-on-who-holds-the-last-city-on-earth | Ashen Throne payout log |
| 12 | https://thirdtimegames.com/docs/ecosystem/derby/ | Photo Finish DERBY→USDC |
| 13 | https://reworthgames.com/ | Reworth Base USDC |
| 14 | https://cryptogames.gg/solfarmer-review-is-the-solana-idle-mining-game-worth-it/ | SolFarmer anti-scam |
| 15 | https://github.com/Omnivalent/clawarcade | ClawArcade agent API |
| 16 | https://cryptrix.app/guide | Cryptrix agent USDC |
| 17 | https://arcade.cafe/ | x402 arcade (skip) |
| 18 | https://hytopia.com/ | HYTOPIA paused (skip) |

*Consulté 2026-11-21. Re-vérifier avant tout passage prêt / actif / spend.*
