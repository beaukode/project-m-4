# Jeux P2E — brief complet (pour / contre / gagner / cashout)

Brief opérateur Agent 4 / Project M. Date : **2026-11-21**.  
Classement : **meilleur potentiel de gains réels (euros ou crypto)** en premier, sous nos règles (bots seulement si le règlement l’autorise ; sinon humain + aide IA sans jouer à sa place ; multi-chaîne OK ; capital jugé sous les plafonds de risque ; un vecteur lent reste utile s’il fait avancer vs les autres agents).  
Pour chaque titre : **Pour** · **Contre** · **Gagner in-game** · **Cashout** · **Verdict en clair**.  
Preuves tirées de l’étude profonde (pas du marketing). **Aucun dépôt capital recommandé ici** : le seul « go » actuel est du temps à 0 €.

Sources d’étude : deep-study complet, top 5, découverte P2E, cibles Pawtato / Clash, briefs [`game-pros-cons-fr.md`](game-pros-cons-fr.md) et [`game-earn-cashout-fr.md`](game-earn-cashout-fr.md).

---

## Légende des termes (une fois)

| Sigle | Signification |
|-------|----------------|
| **P2E** | Play-to-earn : jouer pour gagner de la crypto ou de l’argent |
| **F2P** | Free-to-play : jouable sans payer d’entrée |
| **ToS** | Terms of Service : conditions d’utilisation du jeu |
| **API** | Interface de programmation : permettre à un programme (bot) de jouer ou d’échanger avec le serveur |
| **MCP** | Model Context Protocol : pont officiel pour qu’un agent IA lise / agisse dans le jeu (Ashen Throne, Clash) |
| **USDC** | Dollar stable en crypto (≈ 1 $) |
| **USDG** | Dollar stable côté Robinhood Chain (prix Ashen récents) |
| **DEX** | Exchange décentralisé : échanger des tokens sans banque |
| **CEX** | Exchange centralisé (Binance, etc.) |
| **NFT** | Jeton non fongible : objet / carte / terrain unique on-chain |
| **KYC** | Know Your Customer : vérification d’identité humaine |
| **EV** | Espérance de gain : en moyenne, gagne-t-on ou perd-on après frais / risques |
| **Track A** | Voie bots / API autorisée par le jeu |
| **Track B** | Voie humain qui joue + outils IA d’aide (plans, guides) **sans** injecter les clics à sa place |
| **NAV** | Valeur nette du portefeuille (~200 € de départ) |
| **x402** | Protocole de paiement HTTP pour agents (souvent achat ou mise) |
| **SOL** | Crypto native Solana |
| **Base** | Réseau Ethereum de couche 2 (L2) où tournent plusieurs jeux |
| **DERBY** | Monnaie custodiale Photo Finish (80 DERBY = 1 $ fixe) |
| **Risk Pool** | Caisse partagée (Cambria) : les pertes d’énergie alimentent les gains des autres |

---

## Classement (18 titres)

Filtre opérateur : hors classement si **en pause** ou **sans cashout P2E métier** (devnet-only, démo sans earn, gambling/wager pur, prod morte, rail opaque non triangulé). Les cashouts **faibles** restent.

### 1. Ashen Throne — https://ashenthrone.com/

**Pour.** Navigateur F2P, zéro mise obligatoire. Les cups d’alliance paient en USDC (historique) puis USDG, avec journal public et empreintes de transaction on-chain — on peut vérifier que l’argent sort vraiment. Le MCP officiel permet à un agent IA d’aider (lecture, parfois action avec confirmation) sans enfreindre le ToS, ce qui est rare. Même si les prix hebdo sont petits, le vecteur reste utile sur plusieurs mois face aux autres agents.

**Contre.** Les montants récents sont de l’ordre de dizaines à une centaine de dollars par cup, trop faibles pour doubler 200 € en 30 jours. Le jeu est encore en alpha (resets possibles). Les prix futurs en $THRONE avec blocage 90 jours rendent le cashout moins liquide. Il faut du temps humain d’alliance / siège, pas un bot 24/7 non surveillé.

**Gagner in-game.** Navigateur F2P (alpha) : rejoindre une alliance, participer aux sièges / tenue de districts de la Cup hebdomadaire. La part de prix dépend du split alliance + contribution (puissance détruite, garnison). Éligibilité basse (1 siège ou temps de garnison). Le **MCP officiel** permet à un agent IA d’aider (lecture ; action avec confirmation) sans bot non autorisé. Pas de loot token farm obligatoire.

**Cashout.** Après review fair-play (~48 h), la part va sur un **solde de prix** (pas de claim manuel). Dès **5 $** minimum, un humain signe un batch treasury ; le hash on-chain est public. Historique : **USDC** sur Base, puis **USDG** sur Robinhood Chain. Futur annoncé : prix en **$THRONE** verrouillés 90 jours (Prize Lock) puis unstake 7 j — moins liquide. Wallet vérifié obligatoire.

**Verdict en clair :** meilleur choix actuel — investir du **temps à 0 €**, pas du capital.

---

### 2. MoltStation — https://www.moltstation.games/

**Pour.** Produit conçu pour les agents : API officielle, docs, contrats publics sur Base. Chemin score → snapshot on-chain → claim du token $MOLTS documenté. Entrée possible à presque 0 € (juste du gaz plus tard si on active les claims). C’est l’un des seuls rails Track A explicites hors Clash.

**Contre.** Au check du 21 nov. 2026 : **0** claims sur le pool de récompenses et volume d’échange $MOLTS ≈ 0 $ — économie morte. Même un score parfait ne se transforme pas en euros tant qu’il n’y a pas d’acheteurs. Risque « jouet fantôme » plutôt que rug classique. Le navigateur humain ne donne pas les rewards (practice only).

**Gagner in-game.** Produit **agent-native** sur Base : mint Identity NFT, jouer ShellRunners / Flappy Bots via **API** (`source: agent_api`), snapshot du score on-chain, puis claim sur le contrat Rewards V2. Le navigateur humain = practice **sans** rewards.

**Cashout.** Claim → token **$MOLTS** dans le wallet → swap théorique **MOLTS/WETH** sur Uniswap V4 (Base). Au check 21 nov. 2026 : **0** claims sur le pool et **volume DEX ≈ 0 $** → pas de conversion réelle en euros.

**Verdict en clair :** garder en **veille technique** (smoke API) ; **ne pas claim / ne pas spender** tant que des payouts et de la liquidité n’apparaissent pas.

---

### 3. ClawArcade — https://clawarcade.surge.sh/

**Pour.** Arène agent-native sur Solana (Snake, échecs, etc.) : les bots sont le produit, pas une triche. API Workers en ligne ; inscription agent documentée. Pas de salle de mise obligatoire — les prix sont des parts de pools SOL de tournoi. Fit naturel pour un agent autonome si les paiements se confirment.

**Contre.** Pools microscopiques (ex. ~0,27 SOL sur un mode) face à l’objectif 2×. Aucune transaction de payout on-chain trouvée au moment de l’étude. Projet jeune, peu d’étoiles GitHub, opérateur peu connu. Guest = pas de prix ; il faut être « verified » + wallet SOL.

**Gagner in-game.** Arène agent sur Solana (Snake, échecs, etc.) : bot rejoint via API Workers, score en tournoi. Guest = pas de prix. Compte **verified** (Moltbook) + wallet SOL pour être éligible aux parts de pool.

**Cashout.** Parts de **pools SOL** de tournoi vers le wallet Solana → vendre SOL sur DEX/CEX. **Aucune transaction de payout on-chain** trouvée à l’étude ; pools microscopiques (ex. ~0,27 SOL).

**Verdict en clair :** **prometteur en structure**, bloqué tant qu’on n’a pas **une** preuve de paiement SOL réel.

---

### 4. Olderfall — https://play.olderfall.com/

**Pour.** Auto-battler F2P browser/mobile avec pools USDC documentés via N3MUS (~500–750 $/semaine selon éditos). Studio Anubika + collab Immutable : projet réel, triangulé. Pas besoin de mise pour jouer ; un Fallen gratuit. Cashout en USDC = plus utile que la plupart des tokens de jeu.

**Contre.** Bots / multi-comptes ciblés par l’anti-cheat : seulement Track B (humain + plans hors client). Pour toucher l’USDC il faut grinder le ladder Deathmatch — EV temps très faible pour un nouveau. Pas d’API bot. Dépendance au tiers N3MUS et risque de dérive « betting ».

**Gagner in-game.** Auto-battler F2P : 1 Fallen gratuit, préparer loadouts, grinder le ladder **Deathmatch** (seul mode qui compte pour N3MUS). Points tournoi → classements Weekly / Quick Play. Quêtes Immutable Play = engagement, pas le rail USDC principal. Marketplace NFT = vente d’items (pas un salaire).

**Cashout.** Pools documentés **~500–750 USDC / semaine** via **N3MUS** : register hub + wallet Sequence → claim sur page tournoi (signature message ; pas de KYC documenté dans la FAQ N3MUS). USDC reçu = déjà stable ; ensuite CEX/wallet. Token $AURE planifié ≠ cashout actuel.

**Verdict en clair :** **USDC réel mais compétitif** — OK comme grind humain lent, pas comme bot autonome.

---

### 5. Clash of Coins — https://clashofcoins.com/

**Pour.** Rare : mode agentique + API x402 + MCP **publiés par l’éditeur** (automation autorisée dans ce cadre). Jouable F2P ; chaîne Base. Surface agent réelle (OpenAPI shop répond). Peut servir de terrain d’entraînement agent même sans GO capital.

**Contre.** Monetisation floue : points, Risk-to-Earn, token $OWB très baissé (~−95 % ATH) et liquidité DEX fine. Les passes agentic coûtent cher (jusqu’à des centaines $) et peuvent brûler le NAV. L’API shop = surtout **dépenser** de l’USDC, pas en gagner. KYC possible sur certaines redemptions.

**Gagner in-game.** PvP territoires F2P : Activity Points (jeu, social, referral), tournois / **Risk-to-Earn**, staking **$OWB** (≥ 10k OWB pour points de stake), mode agentique officiel (MCP / API x402). L’API shop sert surtout à **acheter** des items en USDC Base — c’est de la dépense, pas un earn.

**Cashout.** Pas de withdraw USDC documenté depuis les points. Voie théorique : points → allocation **$OWB** (post-saison / TGE) → vendre OWB sur DEX Base (Aerodrome, liquidité fine) → USDC. Passes / redemptions peuvent déclencher **KYC**. Aucun taux points→USDC publié.

**Verdict en clair :** **intéressant techniquement**, **capital fermé** tant qu’un cashout crypto clair et une EV positive ne sont pas prouvés.

---

### 6. Reworth Games — https://reworthgames.com/

**Pour.** Hub browser sur Base, leaderboards → prix USDC annoncés, F2P. Withdraw USDC Base prévu (manuel ≤ 7 j ouvrés selon ToS). Fit Agent 4 si les paiements existent vraiment : 0 stake, stablecoin, pas de NFT gate.

**Contre.** Early beta ; montants de prix **non publiés**. Équipe opaque (« Protocol Team »). **Aucune preuve tierce de payout** trouvée. Bots interdits → Track B seulement. Custody des gains côté site jusqu’au withdraw.

**Gagner in-game.** Hub browser Base (early beta) : jouer aux mini-jeux, monter au **leaderboard** quotidien. Prix financés par le yield d’un Vault USDC (80 % → réserve de prix). Montants de prix **non publiés**. VIP / Coins / Founder Pass = accélérateurs payants (hors GO).

**Cashout.** Gains → balance **custodiale** site → withdraw **USDC Base** manuel, **≤ 7 jours ouvrés** (ToS). Frais de service possibles. Pas de preuve tierce de payout trouvée au check.

**Verdict en clair :** **probe F2P à 0 €** pour tester un claim ; sinon rester en defer.

---

### 7. Photo Finish Live — https://photofinish.live/

**Pour.** Studio Third Time établi ; rail DERBY → withdraw USDC Solana documenté (80 DERBY = 1 $ fixe custodial). Produit live post-bêta argent réel. Skill + breeding peuvent créer un edge (théorique) vs pure chance.

**Contre.** ToS : bots / cheats **interdits** → Track A mort. Modèle wager / picks → EV négative attendue sans edge prouvée. 21+ et géo restreinte (France à valider) ; KYC possible. Stable « sérieux » = dizaines–centaines $ de bankroll. Token $CROWN liquide faiblement.

**Gagner in-game.** Courses hippiques virtuelles argent réel (Third Time) : picks, races, breeding / skill sur chevaux. Dépôt → monnaie in-game **DERBY**. Token **$CROWN** = utilité staking pistes (séparé, liquide faiblement).

**Cashout.** Rail custodial documenté : **80 DERBY = 1 $** fixe → withdraw **USDC sur Solana** (frais historiques ~1 % en Beta 3). Ensuite USDC → CEX / bridge. Âge **21+** ; géo restreinte (France à valider) ; KYC possible.

**Verdict en clair :** rail cashout **clair** mais **pari skill** — 0 € tant qu’éligibilité FR + edge ne sont pas prouvés.

---

### 8. Cambria — https://cambria.gg/

**Pour.** Cashout USDC Risk Pool très documenté (Silver peggé, convert min, floor de pool). Projet crédible (bug bounties payés, couverture DappRadar). Track B possible : plans d’extraction / stratégie hors client. Cashout stable = le plus « banque » du lot skill/risk.

**Contre.** Bots bannis. Pour gagner sérieusement il faut **acheter de l’Energy** : burn qui peut coûter plusieurs $/heure et EV nette souvent négative (rake + haircut + morts). Avec ~200 €, quelques orbs mal joués = trou de NAV. Starter gratuit n’alimente presque pas le pool.

**Gagner in-game.** MMORPG browser risk-to-earn : acheter / brûler de l’**Energy** hors zone sûre → loot Artifacts → cash-in Treasury → **Credits** → conversion Risk Pool → **Silver** (peg USDC). Starter gratuit n’alimente presque pas le pool. Plans d’extraction / stratégie hors client = Track B possible.

**Cashout.** Risk Pool très documenté : **10 000 Silver = 1 USDC** ; convert min ~1 $ ; floor de pool ≥ ~10k $ ; haircut ~1 %. Withdraw **USDC** depuis Silver. Funding = 97 % energy brûlé des joueurs + 3 % rake → EV souvent négative.

**Verdict en clair :** **ne pas acheter d’Energy** ; au mieux plans gratuits — capital **kill** tant qu’EV non mesurée positive.

---

### 9. Pixels — https://www.pixels.xyz/

**Pour.** MMO Ronin mature ; withdraw du token PIXEL documenté (seuils + réputation). Économie live, pas une démo. Contenu / assist Track B possible (guides, planning) sans bot.

**Contre.** Bots non autorisés. Grind humain lourd pour atteindre des montants withdrawables. Token sujet à volatilité et inflation de jeu. Faible fit autonomie Agent 4 et 2×/30 j.

**Gagner in-game.** MMO Ronin : **Task Board** (Hazel) = voie principale vers **$PIXEL** + Coins (farm, craft, quêtes). VIP / land augmentent les chances de tâches PIXEL. Marketplace in-game (seuils de réputation). Guildes / events.

**Cashout.** Wallet **Ronin** connecté + **≥ 2 000 Reputation** → `dashboard.pixels.xyz/exchange` → Withdraw to Wallet (pas de frais PIXEL documentés ; nouveau wallet = 7 j d’attente). Puis PIXEL → DEX/CEX Ronin/écosystème. Token volatil / inflation.

**Verdict en clair :** **grind humain secondaire**, pas un pilote prioritaire.

---

### 10. Football Fun → Sport.fun — https://docs.sport.fun/

**Pour.** Sur Base ; mode Pro avec conversion Gold ↔ USDC documentée. Produit orienté sport / tournois, cashout stable possible si éligible. Track B (humain) si géo OK.

**Contre.** Docs bannissent les bots. Accès Pro / USDC souvent **geo-gated**. Compétition et temps humain ; EV non prouvée pour un petit compte. Pas de path agent autonome.

**Gagner in-game.** Fantasy / tournois sport sur Base : mode Free = Gold **non retirable** gagné en jouant. Mode **Pro** : Gold adossé 1:1 à l’USDC ; Tournament Points (TP) pour packs joueurs ; $FUN optionnel pour bonus TP.

**Cashout.** En Pro seulement : Gold ↔ **USDC** via processus de retrait documenté (souvent **geo-gated**). Free-to-play = **aucun cashout**.

**Verdict en clair :** **humain seulement si la France / géo ouvre** ; sinon skip pratique.

---

### 11. Pawtato Land — https://pawtato.gg/

**Pour.** MMORPG browser Sui réel (docs, marketplace, analytics NFT). Boucle produce → craft → adventure → trade vers $TATO. Orderbook trading automatisé **autorisé** (étroite exception). Multi-chaîne (TATO aussi Solana via bridge) OK sous nos règles.

**Contre.** Rules : **no botting** gameplay. Lands / Heroes mintés : entrée NFT ~dizaines € + working capital. Liquidité TATO fine (slippage). Scholarship non live = pas de F2P earn sérieux. 2×/30 j irréaliste.

**Gagner in-game.** MMORPG browser Sui : staker Lands / Heroes → produire ressources → **craft** → adventure / arena → trade marketplace. Quêtes / Arena donnent du **$TATO** (une part peut être soulbound = non vendable). **xTATO** staking = share de fees gameplay. Orderbook trading automatisé **autorisé** (exception étroite) ; bot gameplay **interdit**.

**Cashout.** TATO sellable → backpack → withdraw wallet Sui (aussi Solana via bridge Wormhole selon docs) → swap DEX → stable/autre chaîne. Liquidité TATO fine (slippage). Entrée NFT Lands/Heroes ~dizaines €.

**Verdict en clair :** projet **sérieux** mais **porte NFT + bots interdits** → veille Track B seulement, capital fermé.

---

### 12. RavenQuest — https://ravenquest.io/

**Pour.** MMORPG live sur Immutable ; modèle earn Fame → coffres $QUEST documenté. Withdraw via Passport après Legacy 15 + Withdraw Pass. Studio et whitepaper matures. Assist guides Track B OK.

**Contre.** ToS anti-bots strict (bans réels signalés). $QUEST ≈ −99 % depuis l’ATH, market cap retail faible. Pass + grind = friction vs capital et temps. Liquidité DEX limitée pour de gros withdraw.

**Gagner in-game.** MMORPG Immutable : farm **Fame** / Renown → coffres hebdo **$QUEST** ; Silver ↔ QUEST en P2P ; land / guild. Anti-cheat AnyBrain.

**Cashout.** Gate : **Legacy Level 15** + **Withdraw Pass** (paiement en QUEST). Puis QUEST jeu → balance site → **Immutable Passport** (seuil ~50 QUEST) → DEX (ex. QuickSwap). Token ≈ −99 % depuis l’ATH ; liquidité retail faible.

**Verdict en clair :** **token cassé + temps lourd** — contenu possible, cashout **faible**.

---

### 13. World of Dypians — https://egamers.io/games/world-of-dypians/

**Pour.** MMORPG + token WOD listé CEX : rail withdraw existe en théorie. Volume directory P2E historique. Track B grind si on accepte le temps login.

**Contre.** Token loin de l’ATH ; earn « token-first » sans edge clair pour A4. Pas d’API bot utile. Grind vs 200 € / autonomie = mauvais fit. Priorité découverte basse.

**Gagner in-game.** MMORPG + activités / events directory P2E → earn token **WOD** (et contenus associés selon saisons). Grind login / quêtes ; pas d’API bot utile documentée pour Agent 4.

**Cashout.** **WOD** listé CEX → vendre contre USDT/USDC/fiat selon exchange. Token loin de l’ATH ; earn « token-first » sans edge clair.

**Verdict en clair :** **basse priorité** — pas de pilote.

---

### 14. Parallel TCG — https://parallel.life/

**Pour.** TCG sci-fi F2P Steam/mobile ; marketplace Sanctuary ; fondation Echelon longue durée. Skill + marché secondaire (pas idle farm).

**Contre.** Bots interdits. Pour earn sérieux : decks NFT + Battle Pass = **centaines–milliers $**, >> 200 €. Token PRIME très loin de l’ATH → cashflow gameplay négligeable au retail. Track B aussi **NO** sur le critère cashout.

**Gagner in-game.** TCG sci-fi F2P (Steam/mobile) : ranked wins, Battle Pass, decks. Earn **PRIME** plafonné (max sérieux = deck 40 NFT + Pass). Marketplace **Sanctuary** pour cartes NFT.

**Cashout.** Claim PRIME → Sanctuary / wallet → CEX/DEX. PRIME ~0,10 $ vs ATH >15 $ → cashflow gameplay **négligeable** au retail. Revente NFT = secondaire, capital d’entrée centaines–milliers $.

**Verdict en clair :** **fermé pour Agent 4** — trop cher pour trop peu de cash.

---

### 15. The Sandbox — https://www.sandbox.game/

**Pour.** Marque connue ; events SAND parfois ; opportunité contenu / creator (vecteur éditorial) si besoin.

**Contre.** ToS : bots / automation interdits. Events souvent **KYC**. Faible fit 2× autonome. Pas un P2E salaire.

**Gagner in-game.** Events saisons, quêtes, création d’expériences / contenu (creator). Pas un salaire P2E agent autonome.

**Cashout.** Récompenses **SAND** (souvent via events) → wallet → CEX. Events fréquemment **KYC**.

**Verdict en clair :** **pas un path earn agent** ; éventuellement contenu opportuniste hors bots.

---

### 16. RollerCoin — https://rollercoin.com/

**Pour.** Idle mining → withdraw crypto documenté ; produit connu / « legit » marketing.

**Contre.** ToS : **no bots / scripts / macros**. EV idle faible face au temps. Pas d’avantage Agent 4 vs un humain cliquant.

**Gagner in-game.** Idle « mining » : power, jeux mini, rachats d’équipement → solde crypto in-game.

**Cashout.** Withdraw crypto documenté vers wallet (seuils / frais selon asset). Produit connu marketing.

**Verdict en clair :** **interdit pour automation** — skip.

---

### 17. BR1: INFINITE — https://litepaper.bravoready.com/br1-infinite-guide/br1-infinite-guide/br1-infinite-overview

**Pour.** Withdraw USDC min documenté presse ; positionnement kill-to-earn.

**Contre.** Pay-to-spawn : chaque mort coûte. Math bankroll ~200 € mauvaise. Invite / extraction haute variance. Hors risk-limits sensées.

**Gagner in-game.** Kill-to-earn / extraction : chaque spawn coûte ; loot / kills alimentent le gain.

**Cashout.** Withdraw **USDC** (min documenté presse) vers wallet. Pay-to-spawn = burn capital rapide.

**Verdict en clair :** **fermé** — brûle le capital trop vite.

---

### 18. SolFarmer — https://solfarmer.io/

**Pour.** Idle Solana → withdraw SOL annoncé (min 0,1 SOL) ; couverture PlayToEarn.

**Contre.** Opérateur anonyme ; ScamAdviser trust **0** ; WHOIS masqué. Balance = part d’un **treasury** opérateur (pas un wallet joueur). Bots interdits. Features chance / wagers. Dépôts alimentent la caisse du site.

**Gagner in-game.** Idle Solana : « miner », Lucky Boxes, Rivals wagers. Balance = part d’un **treasury** opérateur (pas un wallet joueur).

**Cashout.** Withdraw **SOL** annoncé (min 0,1 SOL) sujet anti-fraud / **KYC possible**. Opérateur anonyme ; ScamAdviser trust **0**.

**Verdict en clair :** **fermé dur** — signaux scam / trust trop mauvais.

---

## Marché joueurs / craft / cashout trade-craft

Lecture rapide des **18** titres restants : y a-t-il un **marché entre joueurs** pour l’économie interne, un **craft**, et ces gains (vente / craft) peuvent-ils devenir de l’**argent réel ou de la crypto** — pas seulement une monnaie fermée.  
Les cashouts de type **prix de tournoi / pool** (hors trade-craft) restent dans les fiches ci-dessus ; cette table ne les compte comme « Oui » que s’ils passent par le **marché joueurs** ou le **craft**.

| # | Jeu | Marché économie interne joueurs ? | Craft ? | Cashout depuis trade/craft ? |
|---|-----|-----------------------------------|---------|------------------------------|
| 1 | Ashen Throne | **Non** — prix d’alliance, pas de P2P | **Non** — pas de craft loot | **Non** — cashout = prix cup, pas trade |
| 2 | MoltStation | **Non** — score agent → claim token | **Non** | **Non** — pas de boucle trade/craft |
| 3 | ClawArcade | **Non** — pools tournoi, pas marché items | **Non** | **Non** — payouts = parts de pool |
| 4 | Olderfall | **Oui** — marketplace NFT (Fallen, gear) | **Oui** — Forge / armures | **Partiel** — revente NFT possible ; USDC N3MUS = ladder, pas craft |
| 5 | Clash of Coins | **Limité** — shop USDC (surtout achat) | **Non** | **Non** — points ≠ vente craft ; OWB flou |
| 6 | Reworth Games | **Non** — leaderboard custodial | **Non** | **Non** — prix site, pas trade joueurs |
| 7 | Photo Finish Live | **Oui** — marketplace chevaux en DERBY | **Non** — élevage ≠ craft | **Oui** — vente cheval → DERBY → USDC Solana |
| 8 | Cambria | **Oui** — Trading Post (orderbook Silver) | **Oui** — forge / crafting tables | **Oui** — vente / craft → Silver → USDC |
| 9 | Pixels | **Oui** — marketplace + trade (seuils réputation) | **Oui** — farm / cook / craft | **Partiel** — coins fermées ; withdraw = $PIXEL (gates) |
| 10 | Sport.fun | **Non** — fantasy / packs, pas marché craft | **Non** | **Non** — cashout Pro = Gold↔USDC, pas trade |
| 11 | Pawtato Land | **Oui** — marketplace + exchange orderbook | **Oui** — stations craft (glyphs, gear) | **Oui** — vente / craft → $TATO withdraw |
| 12 | RavenQuest | **Oui** — marketplace + marché Silver↔QUEST | **Oui** — professions / tradepacks | **Oui** — Silver→QUEST→Passport (pass + Legacy) |
| 13 | World of Dypians | **Oui** — Shop / marketplace P2P NFT | **Oui** — forge & craft land | **Oui** — NFT / $WOD → CEX (token faible) |
| 14 | Parallel TCG | **Oui** — Sanctuary (cartes NFT / PRIME) | **Oui** — scraps → cartes | **Partiel** — NFT Sanctuary oui ; craft soft souvent fermé |
| 15 | The Sandbox | **Oui** — marketplace ASSETS / LAND (SAND) | **Oui** — mint VoxEdit / Catalyst | **Oui** — ventes → SAND on-chain |
| 16 | RollerCoin | **Non** — idle solo, pas marché joueurs | **Non** | **Non** — withdraw = solde mining, pas trade |
| 17 | BR1: INFINITE | **Limité** — loot extraction, peu de marché documenté | **Non** | **Non** — withdraw = kill/loot, pas trade/craft |
| 18 | SolFarmer | **Non** — balance treasury opérateur | **Non** | **Non** — withdraw SOL ≠ trade/craft |

**Lecture utile :** les vrais rails **trade/craft → crypto** clairs restent surtout **Cambria, Pawtato, RavenQuest, Sandbox, Photo Finish (chevaux), Dypians** ; **Pixels / Parallel / Olderfall** sont **partiels** (gates, soft currency, ou earn principal hors craft).

---

## Synthèse opérateur

| Rang | Titre | Potentiel relatif | Cashout en clair ? | Action sensée |
|------|-------|-------------------|--------------------|---------------|
| 1 | Ashen Throne | Meilleur | Oui (petits montants) USDC/USDG | Temps F2P + MCP, 0 € |
| 2 | MoltStation | Structure agent | Documenté, **mort en pratique** ($MOLTS) | Smoke API, 0 € |
| 3 | ClawArcade | Structure agent | Annoncé, **non prouvé** (SOL) | Preuve payout, 0 € |
| 4 | Olderfall | USDC compétitif | Oui (N3MUS) | Humain lent ; pas de bot |
| 5 | Clash of Coins | Agents | **Flou** (points → $OWB ?) | Veille tech ; capital fermé |
| 6 | Reworth | USDC annoncé | Documenté, **non prouvé** | Probe F2P 0 € |
| 7 | Photo Finish | Cashout clair | Oui (DERBY → USDC Solana) | 0 € wager |
| 8 | Cambria | Cashout clair | Oui (Silver → USDC, pay-to-burn) | 0 € Energy |
| 9 | Pixels | Grind faible | Oui (seuils PIXEL) | Secondaire |
| 10 | Sport.fun | Géo | Oui en Pro seulement | Si FR/géo ouvre |
| 11 | Pawtato | NFT gate | Oui ($TATO, liquidité fine) | Track B ; capital fermé |
| 12 | RavenQuest | Token cassé | Oui (pass + grind) | Contenu faible |
| 13 | World of Dypians | Basse prio | Oui théorique (WOD → CEX) | Skip pilote |
| 14 | Parallel TCG | NFT / PRIME faible | Oui mais négligeable | Fermé pour A4 |
| 15 | The Sandbox | Events SAND | Oui (souvent KYC) | Pas path agent |
| 16 | RollerCoin | Idle faible | Oui (withdraw crypto) | Skip (no bots) |
| 17 | BR1: INFINITE | Pay-to-spawn | Oui USDC (burn bankroll) | Fermé |
| 18 | SolFarmer | Trust 0 | Annoncé SOL (opaque) | Fermé dur |

**Rappel :** aucun GO capital sur les 18. Le classement mesure surtout **où le temps (et un éventuel micro-gaz futur) a le plus de chances de devenir de vrais euros/crypto**, pas le hype Discord.

---

## Retirés du classement (pause ou sans cashout)

| Nom | URL | Raison |
|-----|-----|--------|
| Agent Poker | https://agentpoker.io/ | Cashout seulement **devnet** — pas de gains réels |
| HYTOPIA | https://hytopia.com/ | Services **en pause** (funding) |
| WhisperDark | https://whisperdark.ngd.network/ | Démo x402 — **aucun cashout P2E** |
| Arcade Cafe / x402 | https://arcade.cafe/ · https://play.0000402.xyz/ | Gambling / house — **pas de cashout métier** |
| Cryptrix | https://cryptrix.app/ | Prod **404** + stake gambling — sans cashout live |
| GateQuake | https://gatequake.com/ | Wager PvP — **pas de cashout métier** |
| Solana Bird (Finchb) | https://bird.finchb.com/ | Rail opaque — triangulation anti-scam insuffisante |
