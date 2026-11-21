# Jeux P2E — pour / contre (français clair)

Brief opérateur Agent 4 / Project M. Date : **2026-11-21**.  
Classement : **meilleur potentiel de gains réels (euros ou crypto)** en premier, sous nos règles (bots seulement si le règlement l’autorise ; sinon humain + aide IA sans jouer à sa place ; multi-chaîne OK ; capital jugé sous les plafonds de risque ; un vecteur lent reste utile s’il fait avancer vs les autres agents).  
Preuves tirées de l’étude profonde (pas du marketing). **Aucun dépôt capital recommandé ici** : le seul « go » actuel est du temps à 0 €.

Sources d’étude : deep-study complet, top 5, découverte P2E, cibles Pawtato / Clash.

---

## Légende des termes (une fois)

| Sigle | Signification |
|-------|----------------|
| **P2E** | Play-to-earn : jouer pour gagner de la crypto ou de l’argent |
| **F2P** | Free-to-play : jouable sans payer d’entrée |
| **ToS** | Terms of Service : conditions d’utilisation du jeu |
| **API** | Interface de programmation : permettre à un programme (bot) de jouer ou d’échanger avec le serveur |
| **MCP** | Model Context Protocol : pont officiel pour qu’un agent IA lise / agisse dans le jeu (Ashen Throne) |
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
| **Risk Pool** | Caisse partagée (Cambria) : les pertes d’énergie alimentent les gains des autres |

---

## Classement (25 titres)

### 1. Ashen Throne — https://ashenthrone.com/

**Pour.** Navigateur F2P, zéro mise obligatoire. Les cups d’alliance paient en USDC (historique) puis USDG, avec journal public et empreintes de transaction on-chain — on peut vérifier que l’argent sort vraiment. Le MCP officiel permet à un agent IA d’aider (lecture, parfois action avec confirmation) sans enfreindre le ToS, ce qui est rare. Même si les prix hebdo sont petits, le vecteur reste utile sur plusieurs mois face aux autres agents.

**Contre.** Les montants récents sont de l’ordre de dizaines à une centaine de dollars par cup, trop faibles pour doubler 200 € en 30 jours. Le jeu est encore en alpha (resets possibles). Les prix futurs en $THRONE avec blocage 90 jours rendent le cashout moins liquide. Il faut du temps humain d’alliance / siège, pas un bot 24/7 non surveillé.

**Verdict en clair :** meilleur choix actuel — investir du **temps à 0 €**, pas du capital.

---

### 2. MoltStation — https://www.moltstation.games/

**Pour.** Produit conçu pour les agents : API officielle, docs, contrats publics sur Base. Chemin score → snapshot on-chain → claim du token $MOLTS documenté. Entrée possible à presque 0 € (juste du gaz plus tard si on active les claims). C’est l’un des seuls rails Track A explicites hors Clash.

**Contre.** Au check du 21 nov. 2026 : **0** claims sur le pool de récompenses et volume d’échange $MOLTS ≈ 0 $ — économie morte. Même un score parfait ne se transforme pas en euros tant qu’il n’y a pas d’acheteurs. Risque « jouet fantôme » plutôt que rug classique. Le navigateur humain ne donne pas les rewards (practice only).

**Verdict en clair :** garder en **veille technique** (smoke API) ; **ne pas claim / ne pas spender** tant que des payouts et de la liquidité n’apparaissent pas.

---

### 3. ClawArcade — https://clawarcade.surge.sh/

**Pour.** Arène agent-native sur Solana (Snake, échecs, etc.) : les bots sont le produit, pas une triche. API Workers en ligne ; inscription agent documentée. Pas de salle de mise obligatoire — les prix sont des parts de pools SOL de tournoi. Fit naturel pour un agent autonome si les paiements se confirment.

**Contre.** Pools microscopiques (ex. ~0,27 SOL sur un mode) face à l’objectif 2×. Aucune transaction de payout on-chain trouvée au moment de l’étude. Projet jeune, peu d’étoiles GitHub, opérateur peu connu. Guest = pas de prix ; il faut être « verified » + wallet SOL.

**Verdict en clair :** **prometteur en structure**, bloqué tant qu’on n’a pas **une** preuve de paiement SOL réel.

---

### 4. Olderfall — https://play.olderfall.com/

**Pour.** Auto-battler F2P browser/mobile avec pools USDC documentés via N3MUS (~500–750 $/semaine selon éditos). Studio Anubika + collab Immutable : projet réel, triangulé. Pas besoin de mise pour jouer ; un Fallen gratuit. Cashout en USDC = plus utile que la plupart des tokens de jeu.

**Contre.** Bots / multi-comptes ciblés par l’anti-cheat : seulement Track B (humain + plans hors client). Pour toucher l’USDC il faut grinder le ladder Deathmatch — EV temps très faible pour un nouveau. Pas d’API bot. Dépendance au tiers N3MUS et risque de dérive « betting ».

**Verdict en clair :** **USDC réel mais compétitif** — OK comme grind humain lent, pas comme bot autonome.

---

### 5. Clash of Coins — https://clashofcoins.com/

**Pour.** Rare : mode agentique + API x402 + MCP **publiés par l’éditeur** (automation autorisée dans ce cadre). Jouable F2P ; chaîne Base. Surface agent réelle (OpenAPI shop répond). Peut servir de terrain d’entraînement agent même sans GO capital.

**Contre.** Monetisation floue : points, Risk-to-Earn, token $OWB très baissé (~−95 % ATH) et liquidité DEX fine. Les passes agentic coûtent cher (jusqu’à des centaines $) et peuvent brûler le NAV. L’API shop = surtout **dépenser** de l’USDC, pas en gagner. KYC possible sur certaines redemptions.

**Verdict en clair :** **intéressant techniquement**, **capital fermé** tant qu’un cashout crypto clair et une EV positive ne sont pas prouvés.

---

### 6. Reworth Games — https://reworthgames.com/

**Pour.** Hub browser sur Base, leaderboards → prix USDC annoncés, F2P. Withdraw USDC Base prévu (manuel ≤ 7 j ouvrés selon ToS). Fit Agent 4 si les paiements existent vraiment : 0 stake, stablecoin, pas de NFT gate.

**Contre.** Early beta ; montants de prix **non publiés**. Équipe opaque (« Protocol Team »). **Aucune preuve tierce de payout** trouvée. Bots interdits → Track B seulement. Custody des gains côté site jusqu’au withdraw.

**Verdict en clair :** **probe F2P à 0 €** pour tester un claim ; sinon rester en defer.

---

### 7. Photo Finish Live — https://photofinish.live/

**Pour.** Studio Third Time établi ; rail DERBY → withdraw USDC Solana documenté (80 DERBY = 1 $ fixe custodial). Produit live post-bêta argent réel. Skill + breeding peuvent créer un edge (théorique) vs pure chance.

**Contre.** ToS : bots / cheats **interdits** → Track A mort. Modèle wager / picks → EV négative attendue sans edge prouvée. 21+ et géo restreinte (France à valider) ; KYC possible. Stable « sérieux » = dizaines–centaines $ de bankroll. Token $CROWN liquide faiblement.

**Verdict en clair :** rail cashout **clair** mais **pari skill** — 0 € tant qu’éligibilité FR + edge ne sont pas prouvés.

---

### 8. Cambria — https://cambria.gg/

**Pour.** Cashout USDC Risk Pool très documenté (Silver peggé, convert min, floor de pool). Projet crédible (bug bounties payés, couverture DappRadar). Track B possible : plans d’extraction / stratégie hors client. Cashout stable = le plus « banque » du lot skill/risk.

**Contre.** Bots bannis. Pour gagner sérieusement il faut **acheter de l’Energy** : burn qui peut coûter plusieurs $/heure et EV nette souvent négative (rake + haircut + morts). Avec ~200 €, quelques orbs mal joués = trou de NAV. Starter gratuit n’alimente presque pas le pool.

**Verdict en clair :** **ne pas acheter d’Energy** ; au mieux plans gratuits — capital **kill** tant qu’EV non mesurée positive.

---

### 9. Pixels — https://www.pixels.xyz/

**Pour.** MMO Ronin mature ; withdraw du token PIXEL documenté (seuils + réputation). Économie live, pas une démo. Contenu / assist Track B possible (guides, planning) sans bot.

**Contre.** Bots non autorisés. Grind humain lourd pour atteindre des montants withdrawables. Token sujet à volatilité et inflation de jeu. Faible fit autonomie Agent 4 et 2×/30 j.

**Verdict en clair :** **grind humain secondaire**, pas un pilote prioritaire.

---

### 10. Football Fun → Sport.fun — https://docs.sport.fun/

**Pour.** Sur Base ; mode Pro avec conversion Gold ↔ USDC documentée. Produit orienté sport / tournois, cashout stable possible si éligible. Track B (humain) si géo OK.

**Contre.** Docs bannissent les bots. Accès Pro / USDC souvent **geo-gated**. Compétition et temps humain ; EV non prouvée pour un petit compte. Pas de path agent autonome.

**Verdict en clair :** **humain seulement si la France / géo ouvre** ; sinon skip pratique.

---

### 11. Pawtato Land — https://pawtato.gg/

**Pour.** MMORPG browser Sui réel (docs, marketplace, analytics NFT). Boucle produce → craft → adventure → trade vers $TATO. Orderbook trading automatisé **autorisé** (étroite exception). Multi-chaîne (TATO aussi Solana via bridge) OK sous nos règles.

**Contre.** Rules : **no botting** gameplay. Lands / Heroes mintés : entrée NFT ~dizaines € + working capital. Liquidité TATO fine (slippage). Scholarship non live = pas de F2P earn sérieux. 2×/30 j irréaliste.

**Verdict en clair :** projet **sérieux** mais **porte NFT + bots interdits** → veille Track B seulement, capital fermé.

---

### 12. RavenQuest — https://ravenquest.io/

**Pour.** MMORPG live sur Immutable ; modèle earn Fame → coffres $QUEST documenté. Withdraw via Passport après Legacy 15 + Withdraw Pass. Studio et whitepaper matures. Assist guides Track B OK.

**Contre.** ToS anti-bots strict (bans réels signalés). $QUEST ≈ −99 % depuis l’ATH, market cap retail faible. Pass + grind = friction vs capital et temps. Liquidité DEX limitée pour de gros withdraw.

**Verdict en clair :** **token cassé + temps lourd** — contenu possible, cashout **faible**.

---

### 13. World of Dypians — https://egamers.io/games/world-of-dypians/

**Pour.** MMORPG + token WOD listé CEX : rail withdraw existe en théorie. Volume directory P2E historique. Track B grind si on accepte le temps login.

**Contre.** Token loin de l’ATH ; earn « token-first » sans edge clair pour A4. Pas d’API bot utile. Grind vs 200 € / autonomie = mauvais fit. Priorité découverte basse.

**Verdict en clair :** **basse priorité** — pas de pilote.

---

### 14. Agent Poker — https://agentpoker.io/

**Pour.** Heads-up poker pour agents via WebSocket : design agent-first. Docs publiques. Si mainnet + liquidité un jour, Track A structurellement aligné.

**Contre.** Aujourd’hui **devnet SOL** seulement ; mainnet après audit. Poker avec rake = EV négative attendue dès qu’il y a de vrais stakes. Pas de gains réels maintenant.

**Verdict en clair :** **watch post-audit** ; zéro capital.

---

### 15. HYTOPIA — https://hytopia.com/

**Pour.** Metaverse Base ; angle créateur / earn si services reviennent. Historique produit et blog techniques.

**Contre.** Homepage : services **en pause** 1–3 mois (funding). Pas de rail earn vivant. Réouverture conditionnelle seulement.

**Verdict en clair :** **fermé tant que paused** ; réévaluer à l’unpause + cashout clair.

---

### 16. WhisperDark — https://whisperdark.ngd.network/

**Pour.** Démo agent x402 (Neo X / COZ) : utile pour apprendre le rail paiement agent. Faible risque si on ne dépose rien.

**Contre.** C’est du **spend** de démo, pas une boucle earn vers le NAV. Aucun cashout P2E. Hors objectif argent.

**Verdict en clair :** **lab technique seulement**, pas un vecteur de gains.

---

### 17. Parallel TCG — https://parallel.life/

**Pour.** TCG sci-fi F2P Steam/mobile ; marketplace Sanctuary ; fondation Echelon longue durée. Skill + marché secondaire (pas idle farm).

**Contre.** Bots interdits. Pour earn sérieux : decks NFT + Battle Pass = **centaines–milliers $**, >> 200 €. Token PRIME très loin de l’ATH → cashflow gameplay négligeable au retail. Track B aussi **NO** sur le critère cashout.

**Verdict en clair :** **fermé pour Agent 4** — trop cher pour trop peu de cash.

---

### 18. The Sandbox — https://www.sandbox.game/

**Pour.** Marque connue ; events SAND parfois ; opportunité contenu / creator (vecteur éditorial) si besoin.

**Contre.** ToS : bots / automation interdits. Events souvent **KYC**. Faible fit 2× autonome. Pas un P2E salaire.

**Verdict en clair :** **pas un path earn agent** ; éventuellement contenu opportuniste hors bots.

---

### 19. RollerCoin — https://rollercoin.com/

**Pour.** Idle mining → withdraw crypto documenté ; produit connu / « legit » marketing.

**Contre.** ToS : **no bots / scripts / macros**. EV idle faible face au temps. Pas d’avantage Agent 4 vs un humain cliquant.

**Verdict en clair :** **interdit pour automation** — skip.

---

### 20. Arcade Cafe / x402 chance — https://arcade.cafe/ · https://play.0000402.xyz/

**Pour.** Rail x402 agent-friendly (HTTP pay). Intéressant comme infra technique.

**Contre.** Monétisation = **wager / house / lottery** (ex. 0,10 USDC → chance 1 USDC). EV house négative pour le joueur. Hors règles « skill P2E » et anti-gambling de fait pour le NAV.

**Verdict en clair :** **fermé** — gambling, pas un métier.

---

### 21. Cryptrix — https://cryptrix.app/ (404 au check)

**Pour.** Idée : rooms Cache Rush agents avec stake USDC sur Arc ; API agent documentée en OSS GitHub.

**Contre.** Site / guide / API → **HTTP 404** (prod morte). Même live : mise 0,5–5 USDC + rake 1 % → EV médiane négative (majorité perd). Gambling stake.

**Verdict en clair :** **mort + EV−** — ne pas rouvrir sans prod + preuve sans rake ruinant.

---

### 22. GateQuake — https://gatequake.com/

**Pour.** Browser battle-royale Solana ; pots USDC visibles marketing.

**Contre.** Stake USDC → pot = **gambling / PvP wager**. Pas un grind skill F2P sûr. Risque de perte du stake.

**Verdict en clair :** **fermé** — mise = casino.

---

### 23. BR1: INFINITE — https://litepaper.bravoready.com/br1-infinite-guide/br1-infinite-guide/br1-infinite-overview

**Pour.** Withdraw USDC min documenté presse ; positionnement kill-to-earn.

**Contre.** Pay-to-spawn : chaque mort coûte. Math bankroll ~200 € mauvaise. Invite / extraction haute variance. Hors risk-limits sensées.

**Verdict en clair :** **fermé** — brûle le capital trop vite.

---

### 24. Solana Bird (Finchb) — https://bird.finchb.com/

**Pour.** Wallet game ; whitepaper ; payouts parfois publics en marketing.

**Contre.** Très jeune ; triangulation anti-scam **insuffisante** pour GO. Yield-like / trust faible. Risque dépôt vers opérateur opaque.

**Verdict en clair :** **fermé** tant que preuves externes solides manquent.

---

### 25. SolFarmer — https://solfarmer.io/

**Pour.** Idle Solana → withdraw SOL annoncé (min 0,1 SOL) ; couverture PlayToEarn.

**Contre.** Opérateur anonyme ; ScamAdviser trust **0** ; WHOIS masqué. Balance = part d’un **treasury** opérateur (pas un wallet joueur). Bots interdits. Features chance / wagers. Dépôts alimentent la caisse du site.

**Verdict en clair :** **fermé dur** — signaux scam / trust trop mauvais.

---

## Synthèse opérateur

| Rang | Titre | Potentiel relatif | Action sensée |
|------|-------|-------------------|---------------|
| 1 | Ashen Throne | Meilleur | Temps F2P + MCP, 0 € |
| 2–3 | MoltStation, ClawArcade | Structure agent | Smoke / preuve payout, 0 € |
| 4–6 | Olderfall, Clash, Reworth | USDC ou agents | Humain / veille ; pas de stake |
| 7–8 | Photo Finish, Cambria | Cashout clair | 0 € Energy / 0 € wager |
| 9–13 | Pixels → RavenQuest… | Grind faible | Secondaire ou skip |
| 14–16 | Agent Poker, HYTOPIA, WhisperDark | Immature / pause / lab | Watch |
| 17–25 | Parallel → SolFarmer | EV− / ToS / scam / NFT | Fermés |

**Rappel :** aucun GO capital sur les 25. Le classement mesure surtout **où le temps (et un éventuel micro-gaz futur) a le plus de chances de devenir de vrais euros/crypto**, pas le hype Discord.
