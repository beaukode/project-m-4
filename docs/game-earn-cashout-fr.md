# Jeux P2E — gagner in-game & cashout (français clair)

> Brief fusionné (pour / contre + gagner / cashout) : [`game-brief-complet-fr.md`](game-brief-complet-fr.md).

Brief opérateur Agent 4 / Project M. Date : **2026-11-21**.  
Même classement que [`game-pros-cons-fr.md`](game-pros-cons-fr.md) : **meilleur potentiel de gains réels** (euros ou crypto) en premier.  
Pour chaque titre : **comment gagner dans le jeu**, puis **comment convertir en argent / crypto** (ou « aucun cashout clair »).

Sources : deep-study complet / top 5, cibles Pawtato–Clash, pour/contre FR, docs officielles (Ashen, MoltStation, Reworth, Sport.fun, Pixels, Clash, etc.). **Aucun dépôt capital recommandé** : le seul « go » actuel reste du temps à 0 €.

---

## Légende (une fois)

| Sigle | Signification |
|-------|----------------|
| **P2E** | Play-to-earn : jouer pour gagner de la crypto ou de l’argent |
| **F2P** | Free-to-play : jouable sans payer d’entrée |
| **USDC** | Dollar stable en crypto (≈ 1 $) |
| **USDG** | Dollar stable côté Robinhood Chain (prix Ashen récents) |
| **DEX** | Exchange décentralisé : échanger des tokens sans banque |
| **CEX** | Exchange centralisé (Binance, etc.) |
| **NFT** | Jeton non fongible : objet / carte / terrain unique on-chain |
| **KYC** | Know Your Customer : vérification d’identité humaine |
| **API** | Interface de programmation (bot / agent) |
| **MCP** | Model Context Protocol : pont officiel agent IA (Ashen, Clash) |
| **ToS** | Conditions d’utilisation |
| **SOL** | Crypto native Solana |
| **Base** | Réseau Ethereum de couche 2 (L2) |
| **DERBY** | Monnaie custodiale Photo Finish (80 DERBY = 1 $ fixe) |
| **Risk Pool** | Caisse partagée Cambria : les pertes d’énergie alimentent les gains |

---

## Classement (25 titres)

### 1. Ashen Throne — https://ashenthrone.com/

**Gagner in-game.** Navigateur F2P (alpha) : rejoindre une alliance, participer aux sièges / tenue de districts de la Cup hebdomadaire. La part de prix dépend du split alliance + contribution (puissance détruite, garnison). Éligibilité basse (1 siège ou temps de garnison). Le **MCP officiel** permet à un agent IA d’aider (lecture ; action avec confirmation) sans bot non autorisé. Pas de loot token farm obligatoire.

**Cashout.** Après review fair-play (~48 h), la part va sur un **solde de prix** (pas de claim manuel). Dès **5 $** minimum, un humain signe un batch treasury ; le hash on-chain est public. Historique : **USDC** sur Base, puis **USDG** sur Robinhood Chain. Futur annoncé : prix en **$THRONE** verrouillés 90 jours (Prize Lock) puis unstake 7 j — moins liquide. Wallet vérifié obligatoire.

**Note.** Montants cup récents = dizaines à ~100 $ ; trop faibles pour 2×/30 j, utiles en temps 0 €.

---

### 2. MoltStation — https://www.moltstation.games/

**Gagner in-game.** Produit **agent-native** sur Base : mint Identity NFT, jouer ShellRunners / Flappy Bots via **API** (`source: agent_api`), snapshot du score on-chain, puis claim sur le contrat Rewards V2. Le navigateur humain = practice **sans** rewards.

**Cashout.** Claim → token **$MOLTS** dans le wallet → swap théorique **MOLTS/WETH** sur Uniswap V4 (Base). Au check 21 nov. 2026 : **0** claims sur le pool et **volume DEX ≈ 0 $** → pas de conversion réelle en euros.

**Note.** Veille technique (smoke API) ; ne pas claim / ne pas spender tant que liquidité et payouts n’existent pas.

---

### 3. ClawArcade — https://clawarcade.surge.sh/

**Gagner in-game.** Arène agent sur Solana (Snake, échecs, etc.) : bot rejoint via API Workers, score en tournoi. Guest = pas de prix. Compte **verified** (Moltbook) + wallet SOL pour être éligible aux parts de pool.

**Cashout.** Parts de **pools SOL** de tournoi vers le wallet Solana → vendre SOL sur DEX/CEX. **Aucune transaction de payout on-chain** trouvée à l’étude ; pools microscopiques (ex. ~0,27 SOL).

**Note.** Structure prometteuse ; bloqué sans **une** preuve de paiement SOL réel.

---

### 4. Olderfall — https://play.olderfall.com/

**Gagner in-game.** Auto-battler F2P : 1 Fallen gratuit, préparer loadouts, grinder le ladder **Deathmatch** (seul mode qui compte pour N3MUS). Points tournoi → classements Weekly / Quick Play. Quêtes Immutable Play = engagement, pas le rail USDC principal. Marketplace NFT = vente d’items (pas un salaire).

**Cashout.** Pools documentés **~500–750 USDC / semaine** via **N3MUS** : register hub + wallet Sequence → claim sur page tournoi (signature message ; pas de KYC documenté dans la FAQ N3MUS). USDC reçu = déjà stable ; ensuite CEX/wallet. Token $AURE planifié ≠ cashout actuel.

**Note.** Bots interdits (anti-cheat) → humain seulement ; EV temps faible pour un nouveau.

---

### 5. Clash of Coins — https://clashofcoins.com/

**Gagner in-game.** PvP territoires F2P : Activity Points (jeu, social, referral), tournois / **Risk-to-Earn**, staking **$OWB** (≥ 10k OWB pour points de stake), mode agentique officiel (MCP / API x402). L’API shop sert surtout à **acheter** des items en USDC Base — c’est de la dépense, pas un earn.

**Cashout.** Pas de withdraw USDC documenté depuis les points. Voie théorique : points → allocation **$OWB** (post-saison / TGE) → vendre OWB sur DEX Base (Aerodrome, liquidité fine) → USDC. Passes / redemptions peuvent déclencher **KYC**. Aucun taux points→USDC publié.

**Note.** Intéressant techniquement ; **aucun cashout clair** prouvé pour Agent 4 → capital fermé.

---

### 6. Reworth Games — https://reworthgames.com/

**Gagner in-game.** Hub browser Base (early beta) : jouer aux mini-jeux, monter au **leaderboard** quotidien. Prix financés par le yield d’un Vault USDC (80 % → réserve de prix). Montants de prix **non publiés**. VIP / Coins / Founder Pass = accélérateurs payants (hors GO).

**Cashout.** Gains → balance **custodiale** site → withdraw **USDC Base** manuel, **≤ 7 jours ouvrés** (ToS). Frais de service possibles. Pas de preuve tierce de payout trouvée au check.

**Note.** Probe F2P 0 € pour tester un claim ; sinon defer. Bots interdits.

---

### 7. Photo Finish Live — https://photofinish.live/

**Gagner in-game.** Courses hippiques virtuelles argent réel (Third Time) : picks, races, breeding / skill sur chevaux. Dépôt → monnaie in-game **DERBY**. Token **$CROWN** = utilité staking pistes (séparé, liquide faiblement).

**Cashout.** Rail custodial documenté : **80 DERBY = 1 $** fixe → withdraw **USDC sur Solana** (frais historiques ~1 % en Beta 3). Ensuite USDC → CEX / bridge. Âge **21+** ; géo restreinte (France à valider) ; KYC possible.

**Note.** Cashout clair, mais bots interdits + modèle **pari** → EV négative sans edge ; 0 € tant qu’éligibilité FR + edge non prouvées.

---

### 8. Cambria — https://cambria.gg/

**Gagner in-game.** MMORPG browser risk-to-earn : acheter / brûler de l’**Energy** hors zone sûre → loot Artifacts → cash-in Treasury → **Credits** → conversion Risk Pool → **Silver** (peg USDC). Starter gratuit n’alimente presque pas le pool. Plans d’extraction / stratégie hors client = Track B possible.

**Cashout.** Risk Pool très documenté : **10 000 Silver = 1 USDC** ; convert min ~1 $ ; floor de pool ≥ ~10k $ ; haircut ~1 %. Withdraw **USDC** depuis Silver. Funding = 97 % energy brûlé des joueurs + 3 % rake → EV souvent négative.

**Note.** Ne pas acheter d’Energy ; cashout clair mais burn capital. Bots bannis.

---

### 9. Pixels — https://www.pixels.xyz/

**Gagner in-game.** MMO Ronin : **Task Board** (Hazel) = voie principale vers **$PIXEL** + Coins (farm, craft, quêtes). VIP / land augmentent les chances de tâches PIXEL. Marketplace in-game (seuils de réputation). Guildes / events.

**Cashout.** Wallet **Ronin** connecté + **≥ 2 000 Reputation** → `dashboard.pixels.xyz/exchange` → Withdraw to Wallet (pas de frais PIXEL documentés ; nouveau wallet = 7 j d’attente). Puis PIXEL → DEX/CEX Ronin/écosystème. Token volatil / inflation.

**Note.** Grind humain lourd ; bots non autorisés ; mauvais fit autonomie Agent 4.

---

### 10. Football Fun → Sport.fun — https://docs.sport.fun/

**Gagner in-game.** Fantasy / tournois sport sur Base : mode Free = Gold **non retirable** gagné en jouant. Mode **Pro** : Gold adossé 1:1 à l’USDC ; Tournament Points (TP) pour packs joueurs ; $FUN optionnel pour bonus TP.

**Cashout.** En Pro seulement : Gold ↔ **USDC** via processus de retrait documenté (souvent **geo-gated**). Free-to-play = **aucun cashout**.

**Note.** Humain seulement si la France / géo ouvre le Pro ; bots bannis.

---

### 11. Pawtato Land — https://pawtato.gg/

**Gagner in-game.** MMORPG browser Sui : staker Lands / Heroes → produire ressources → **craft** → adventure / arena → trade marketplace. Quêtes / Arena donnent du **$TATO** (une part peut être soulbound = non vendable). **xTATO** staking = share de fees gameplay. Orderbook trading automatisé **autorisé** (exception étroite) ; bot gameplay **interdit**.

**Cashout.** TATO sellable → backpack → withdraw wallet Sui (aussi Solana via bridge Wormhole selon docs) → swap DEX → stable/autre chaîne. Liquidité TATO fine (slippage). Entrée NFT Lands/Heroes ~dizaines €.

**Note.** Projet sérieux ; porte NFT + bots gameplay interdits → capital fermé, Track B seulement.

---

### 12. RavenQuest — https://ravenquest.io/

**Gagner in-game.** MMORPG Immutable : farm **Fame** / Renown → coffres hebdo **$QUEST** ; Silver ↔ QUEST en P2P ; land / guild. Anti-cheat AnyBrain.

**Cashout.** Gate : **Legacy Level 15** + **Withdraw Pass** (paiement en QUEST). Puis QUEST jeu → balance site → **Immutable Passport** (seuil ~50 QUEST) → DEX (ex. QuickSwap). Token ≈ −99 % depuis l’ATH ; liquidité retail faible.

**Note.** Token cassé + temps lourd ; bots ToS = ban.

---

### 13. World of Dypians — https://egamers.io/games/world-of-dypians/

**Gagner in-game.** MMORPG + activités / events directory P2E → earn token **WOD** (et contenus associés selon saisons). Grind login / quêtes ; pas d’API bot utile documentée pour Agent 4.

**Cashout.** **WOD** listé CEX → vendre contre USDT/USDC/fiat selon exchange. Token loin de l’ATH ; earn « token-first » sans edge clair.

**Note.** Basse priorité ; pas de pilote.

---

### 14. Agent Poker — https://agentpoker.io/

**Gagner in-game.** Poker heads-up pour agents via WebSocket : mise / bluff / pots selon règles NLHE. Aujourd’hui **devnet SOL** seulement (mainnet après audit).

**Cashout.** Sur mainnet (futur) : pots **SOL** → wallet → DEX/CEX. Aujourd’hui = **aucun cashout réel** (devnet).

**Note.** Watch post-audit ; rake = EV négative attendue dès qu’il y a de vrais stakes.

---

### 15. HYTOPIA — https://hytopia.com/

**Gagner in-game.** Metaverse Base : angle créateur / services / expériences (quand live). Homepage : services **en pause** 1–3 mois (funding).

**Cashout.** **Aucun cashout clair** tant que paused ; à réévaluer à l’unpause (token / marketplace créateur à confirmer).

**Note.** Fermé tant que paused.

---

### 16. WhisperDark — https://whisperdark.ngd.network/

**Gagner in-game.** Démo agent **x402** (Neo X / COZ) : sessions / rooms pour tester le paiement HTTP agent. C’est du **spend** de démo, pas une farm P2E.

**Cashout.** **Aucun cashout P2E** — pas de boucle vers le NAV.

**Note.** Lab technique seulement.

---

### 17. Parallel TCG — https://parallel.life/

**Gagner in-game.** TCG sci-fi F2P (Steam/mobile) : ranked wins, Battle Pass, decks. Earn **PRIME** plafonné (max sérieux = deck 40 NFT + Pass). Marketplace **Sanctuary** pour cartes NFT.

**Cashout.** Claim PRIME → Sanctuary / wallet → CEX/DEX. PRIME ~0,10 $ vs ATH >15 $ → cashflow gameplay **négligeable** au retail. Revente NFT = secondaire, capital d’entrée centaines–milliers $.

**Note.** Fermé pour Agent 4 — trop cher pour trop peu de cash. Bots interdits.

---

### 18. The Sandbox — https://www.sandbox.game/

**Gagner in-game.** Events saisons, quêtes, création d’expériences / contenu (creator). Pas un salaire P2E agent autonome.

**Cashout.** Récompenses **SAND** (souvent via events) → wallet → CEX. Events fréquemment **KYC**.

**Note.** Bots / automation interdits ; pas un path earn agent.

---

### 19. RollerCoin — https://rollercoin.com/

**Gagner in-game.** Idle « mining » : power, jeux mini, rachats d’équipement → solde crypto in-game.

**Cashout.** Withdraw crypto documenté vers wallet (seuils / frais selon asset). Produit connu marketing.

**Note.** ToS : **no bots / scripts / macros** → interdit pour automation Agent 4 ; EV idle faible.

---

### 20. Arcade Cafe / x402 chance — https://arcade.cafe/ · https://play.0000402.xyz/

**Gagner in-game.** Rail x402 : jeux type Dice / Sweeper = **mise** ; lottery Base (ex. 0,10 USDC → chance 1 USDC). Agents attendus techniquement.

**Cashout.** Si gain : USDC / SOL déjà on-chain → wallet. EV **house négative** (gambling).

**Note.** Fermé — paris / maison, pas un métier skill.

---

### 21. Cryptrix — https://cryptrix.app/

**Gagner in-game.** Rooms Cache Rush agents : stake **0,5–5 USDC**/siège ; top 3 se partagent le pot (60/25/15 %) après **1 %** fee. Site / guide / API → **HTTP 404** au check (prod morte).

**Cashout.** Si live : pot USDC → wallet Arc. EV médiane négative (rake + majorité perd).

**Note.** Mort + EV− ; ne pas rouvrir sans prod + preuve sans ruin de rake.

---

### 22. GateQuake — https://gatequake.com/

**Gagner in-game.** Battle-royale browser Solana : stake USDC → pot PvP (survive / win).

**Cashout.** Pot **USDC** vers gagnants (marketing). Nature = **wager PvP**.

**Note.** Fermé — mise = casino.

---

### 23. BR1: INFINITE — https://litepaper.bravoready.com/br1-infinite-guide/br1-infinite-guide/br1-infinite-overview

**Gagner in-game.** Kill-to-earn / extraction : chaque spawn coûte ; loot / kills alimentent le gain.

**Cashout.** Withdraw **USDC** (min documenté presse) vers wallet. Pay-to-spawn = burn capital rapide.

**Note.** Fermé — math bankroll ~200 € mauvaise.

---

### 24. Solana Bird (Finchb) — https://bird.finchb.com/

**Gagner in-game.** Wallet game / whitepaper : boucles yield-like / gameplay léger (jeune produit).

**Cashout.** Payouts parfois annoncés en marketing — **triangulation anti-scam insuffisante** pour faire confiance au rail.

**Note.** Fermé tant que preuves externes solides manquent.

---

### 25. SolFarmer — https://solfarmer.io/

**Gagner in-game.** Idle Solana : « miner », Lucky Boxes, Rivals wagers. Balance = part d’un **treasury** opérateur (pas un wallet joueur).

**Cashout.** Withdraw **SOL** annoncé (min 0,1 SOL) sujet anti-fraud / **KYC possible**. Opérateur anonyme ; ScamAdviser trust **0**.

**Note.** Fermé dur — signaux scam / trust trop mauvais. Bots interdits.

---

## Synthèse rapide cashout

| Rang | Titre | Cashout en clair ? | Forme principale |
|------|-------|--------------------|------------------|
| 1 | Ashen Throne | Oui (petits montants) | USDC/USDG on-chain (futur $THRONE lock) |
| 2 | MoltStation | Documenté, **mort en pratique** | $MOLTS → DEX Base |
| 3 | ClawArcade | Annoncé, **non prouvé** | Parts SOL tournoi |
| 4 | Olderfall | Oui (compétitif) | USDC N3MUS |
| 5 | Clash of Coins | **Flou** | Points → $OWB → DEX ? |
| 6 | Reworth | Documenté, **non prouvé** | USDC Base custodial |
| 7 | Photo Finish | Oui | DERBY → USDC Solana |
| 8 | Cambria | Oui (pay-to-burn) | Silver → USDC Risk Pool |
| 9 | Pixels | Oui (seuils) | PIXEL → Ronin wallet |
| 10 | Sport.fun | Oui en Pro seulement | Gold ↔ USDC |
| 11 | Pawtato | Oui (NFT gate) | $TATO → wallet / DEX |
| 12 | RavenQuest | Oui (pass + grind) | $QUEST → Passport → DEX |
| 13 | World of Dypians | Oui théorique | WOD → CEX |
| 14–16 | Agent Poker, HYTOPIA, WhisperDark | Non / pas encore | Devnet / pause / lab |
| 17–19 | Parallel, Sandbox, RollerCoin | Faible / KYC / ToS | PRIME / SAND / withdraw idle |
| 20–25 | Arcade… SolFarmer | Gambling / mort / scam | Stake, treasury opaque |

**Rappel :** aucun GO capital sur les 25. Classement = où le temps (et un éventuel micro-gaz futur) a le plus de chances de devenir de vrais euros/crypto.
