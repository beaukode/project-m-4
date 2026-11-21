# Chemins jeux — bots autorisés vs assist humain

Recherche documentée (Agent 4 / Project M). **Aucun spend / ops capital** dans ce doc.  
Langue : FR. Date de synthèse : **2026-11-21**.

**Préférence opérateur** : bots/API seulement si ToS l’autorisent ; sinon humain (Jérémie / Noe) + outils d’assist IA **sans** injection d’inputs ni clic pour le joueur.

**Recommandation globale** → voir [§5](#5-recommandation-agent-4).

---

## 1. Méthode & garde-fous

| Règle | Application |
|-------|-------------|
| Triangulation | ≥ 2 sources externes indépendantes par candidat (ToS/docs officiels + source secondaire) |
| Anti-scam | Pas de dépôt sur plateformes non triangulées ; méfiance des arènes crypto jeunes / gambling |
| Interdits | Bots « human-like » d’évasion, auto-clickers sur jeux où bots sont bannis, memory reads / ESP |
| Capital | Fit évalué vs ~200 € / 30 j / ETH L1 — sans engager de fonds ici |
| Kill soft | Tout doute ToS → **NO** ou **WATCH** ; jamais « ça passe tant que non détecté » |

Légende verdict Track A : **GO** · **WATCH** · **NO**

---

## 2. Track A — bots / API explicitement permis + monétisation

### 2.1 Tableau candidats

| Candidat | Bot/API ? | Monétisation | Fit ~200 €/30 j | Verdict | Risque |
|----------|-----------|--------------|-----------------|---------|--------|
| Lichess Bot API | Oui (comptes BOT) | Tournois communauté (prix petits, PayPal) | Faible | **WATCH** | faible (ToS) / élevé (revenu) |
| Second Life (scripted agents) | Oui (politique officielle) | Services/L$ → LindeX → USD (KYC Tilia) | Possible mais lent + KYC humain | **WATCH** | modéré |
| bandforband.fun agents | Oui (docs agents) | Concours USDC / Solana | Mauvais (perte stake, mauvaise chaîne) | **NO** | élevé |
| PIVArena Bot API | Oui (API bots) | PvP staké PIVX/ZEC/XMR | Mauvais (gambling, plateforme neuve) | **NO** | élevé |
| ProfitPlay / OMERTÀ agents | Oui (API) | GALA / withdrawals souvent sandbox ou dormants | Mauvais | **NO** | élevé |
| monopoly.land agents | Oui (HTTP + wallet) | Trading $MONO on-chain | Mauvais (token/jeu nouveau) | **NO** | élevé |
| EVE Online ESI | API lecture OK | RMT interdit ; bots client interdits | N/A bots monétisés | **NO** (bots) | — |
| Steam Market / trade bots | Non (SSA Automation) | Market items | N/A | **NO** | — |
| Path of Exile / GW2 TP | API lecture ; bots interdits | RMT / automation ban | N/A | **NO** | — |
| Torn City API | Read-only + scripts API OK | Pas d’automation d’actions non-API | Assist seulement → Track B | **NO** (bots play) | — |
| Chess.com | Bots/engines interdits vs humains | Prix tournois = fair play strict | N/A | **NO** | — |

### 2.2 Détails & citations (Track A)

#### A1 — Lichess Bot API — **WATCH**

- **Thèse** : compte marqué BOT, moteur autorisé via Bot API ; défis uniquement (pas pools) sauf si l’organisateur active « Bot players are allowed ».
- **Sources** :
  1. Spec API officielle (tag Bot) — [lichess-org/api](https://github.com/lichess-org/api/blob/master/doc/specs/lichess-api.yaml) : *« Engine assistance is allowed »* ; *« Bots can only play challenge games: pools and tournaments are off-limits »* (sauf opt-in organisateur).
  2. Exemples d’arenas communauté avec prix bots (~4–20 USD) — ex. [tournoi Kqul9pAe](https://lichess.org/tournament/Kqul9pAe) ; Lichess précise : *« Lichess is not responsible for paying them »* ([event tips](https://lichess.org/page/event-tips)).
- **Fit 200 €/30 j** : prix trop petits / irréguliers / PayPal ; pas un moteur 2×.
- **Anti-scam** : plateforme établie OK ; **risque** = non-paiement organisateur tiers.
- **Kill** : dépendre de prix non garantis **ou** violation fair-play (sandbagging / boosting).

#### A2 — Second Life scripted agents — **WATCH**

- **Thèse** : bots/agents scriptés **autorisés** pour usages légitimes (services, NPCs) ; monétisation via L$ puis LindeX / process credit.
- **Sources** :
  1. [Scripted Agent Policy](https://wiki.secondlife.com/wiki/Linden_Lab_Official:Scripted_Agent_Policy) : *« Second Life allows Scripted Agents with legitimate uses »* ; interdits : traffic boosting, spam > 5 000 msg/j, achat Mainland automatisé.
  2. Cashout : [Account balance KB](https://community.secondlife.com/knowledgebase/english/account-balance-r1/) + [Tilia FAQ](https://community.secondlife.com/knowledgebase/english/tilia-faq-r1533/) — vente L$ → crédit USD → payout PayPal **avec KYC** (nom, adresse, DOB, ID).
- **Fit 200 €/30 j** : possible en théorie (shop/service) mais **ramp-up** + **KYC humain** (escalade opérateur) + hors ETH L1 direct.
- **Anti-scam** : rester sur LindeX officiel ; pas d’échanges L$ tiers.
- **Kill** : demande seed / viewer malware **ou** modèle économique spam/traffic **ou** KYC impossible.

#### A3 — Arènes agents crypto (bandforband, PIVArena, ProfitPlay, monopoly.land, OMERTÀ) — **NO** (Agent 4 maintenant)

- **Thèse surface** : docs **explicitement** bot-friendly (API, badge BOT, lanes agent).
- **Sources bandforband** :
  1. [docs agents](https://docs.bandforband.fun/agents) : *« Bring your own trading bot… for real money »* (USDC / Solana, wallet custodial Privy).
  2. Triangulation risque : scores tiers élevés ([isthiscoinascam](https://isthiscoinascam.com/check/bandforband-fun) score bas ; [Kryll X-Ray](https://app.kryll.io/x-ray/bandforband-fun) « High Risk ») + nature stake/perte.
- **Sources PIVArena** :
  1. [Bot API](https://pivarena.com/docs/api) : bots tagués, play/withdraw scopes.
  2. Plateforme **très récente** (annonces forum ~oct 2026), listings [Monerica « Not verified »](https://monerica.com/site/pivarena) — gambling PvP, pas d’historique de confiance.
- **Pourquoi NO pour A4** : (1) risque de perte du stake = anti-objectif NAV ; (2) chaînes Solana/GALA/PIVX ≠ focus ETH L1 ; (3) triangulation anti-scam insuffisante / scores risque élevés ; (4) proche du gambling. **Réévaluer seulement** après audits indépendants + historique retraits + autorisation spend explicite.

#### A4 — EVE Online — **NO** pour bots monétisés

- **Sources** :
  1. [Third Party Policies](https://support.eveonline.com/hc/en-us/articles/8564030965660-Third-Party-Policies) : *« Botting software — This is NOT allowed under any circumstances »* ; *« Real money trading… NOT allowed »*.
  2. ESI = API officielle lecture ([developers.eveonline.com](https://developers.eveonline.com/docs/services/esi/overview/)) — utile en **Track B** (données → humain place les ordres), pas en bot qui joue/trade tout seul.
- Forum joueurs distingue parfois « spreadsheet + humain » vs « bot client » : seul le premier est dans la zone tolérée (toujours à risque EULA).

#### A5 — Steam / PoE / GW2 — **NO**

- **Steam SSA** §4.C Automation ([store.steampowered.com/agreement](https://store.steampowered.com/agreement/)) : *« You may not use any form of scripts, bots, macros… to interact with Content and Services on Steam »* ; §4.B interdit aussi logiciels non autorisés pour modifier les Subscription Marketplaces.
- **PoE ToU** §7.c : *« Utilise any automated software or 'bots'… »* interdit ; GGG staff confirme bans trade bots ([forum](https://www.pathofexile.com/forum/view-thread/3436344)). API officielle = apps **séparées** du client, macros 1 action manuelle ([developer docs](https://www.pathofexile.com/developer/docs)).
- **GW2** : User Agreement §2.1.3 interdit programmes qui *« automate actions »* / *« unattended gameplay »* ; [Policy Third-Party](https://help.guildwars2.com/hc/en-us/articles/360013625034-Policy-Third-Party-Programs) ; Content Terms API : app *« must not be able to automate gameplay »* ([arena.net](https://www.arena.net/en/legal/content-terms-of-use)).

#### A6 — Torn City — **NO** bots d’action ; **WATCH** outils API (→ B)

- API **read-only** officielle ([torn.com/api.html](https://www.torn.com/api.html)).
- Scripts : seulement API ou page **activement** vue ; *pas* de requêtes non-API automatisées ([annonce scripting rules](https://www.torn.com/forums.php?a=0&b=0&f=1&p=threads&t=16534470)).
- Monétisation outils : contacter staff pour dons/charges ; pas un path A « bot gagne de l’argent tout seul ».

#### A7 — Chess.com — **NO**

- [Fair Play Policy](https://www.chess.com/legal/fair-play) : *« Do not use chess engines, software of any kind, bots… that analyze positions during play »* vs autres utilisateurs.

---

## 3. Track B — humain + assist IA (sans jouer à sa place)

### 3.1 Principe Agent 4

| Autorisé (cible) | Interdit / zone grise |
|------------------|------------------------|
| Plans de stratégie / checklists **hors partie** | Injection d’inputs, auto-clickers, macros multi-actions |
| Revue post-partie (VOD, notes, drills) | Overlays temps réel « va ici maintenant », ESP, wallhacks |
| Dashboards données **officielles** (API read-only) + **humain** qui clique | Memory reads, packet sniff, client mods |
| Spreadsheets marché (EVE ESI, Torn API, PoE trade site) | Bots qui placent ordres / tradent sans humain |
| Configs in-game (.cfg), binds manuels 1:1 | Scripts no-recoil, bhop macros (FACEIT, etc.) |
| Overlays communication génériques (Discord/OBS) si AC les tolère | Overlays info de jeu cachée / screen-analysis utilities |

**Règle d’or** : l’IA conseille ; **l’humain** est le seul à agir dans le client. En cas de doute → ne pas utiliser l’outil.

### 3.2 Exemples par plateforme

#### B1 — FACEIT / CS2 compétitif

- **Sources** : [What is deemed to be a cheat?](https://support.faceit.com/hc/en-us/articles/360015788779-What-is-deemed-to-be-a-cheat) ; [Terms](https://www.faceit.com/en/terms) §36–38.
- **Banni** : cheats, *« External scripting/macros »*, *« screen-analysis utilities »*, bots, ghosting.
- **Assist OK** : plans pré-match hors client ; revue démo après match ; configs `.cfg` listées safe ; **pas** d’overlay custom non whitelisté pendant AC (risque blocage).
- **Verdict assist** : stratégie/docs **OK** ; overlays stats live **gris → éviter**.

#### B2 — Riot (LoL / VALORANT)

- **Sources** : [Third-party apps support](https://support-leagueoflegends.riotgames.com/hc/es/articles/225266848-Aplicaciones-de-terceros) (même politique) ; [Valorant developer policy](https://developer.riotgames.com/docs/valorant).
- **Banni** : bots/scripts qui agissent pour vous ; info volontairement cachée ; overlays temps réel qui altèrent le comportement immédiat (*« go here now »*).
- **OK** : stats post-partie, outils d’entraînement / historique via API approuvée, réflexion entre games.
- **Verdict** : checklists + review **OK** ; coach overlay live **NO**.

#### B3 — Blizzard (WoW / Overwatch)

- **Sources** : [Blizzard EULA](https://us.blizzard.com/en-us/company/about/termsofuse.html) (cheats/bots/hacks) ; [Overwatch staff post](https://us.forums.blizzard.com/en/overwatch/t/unauthorized-third-party-software/213220) — apps donnant positions/HP/ult ennemis interdites.
- **WoW** : addons via API Blizzard = cadre officiel (pas « third-party cheat ») ; bots / contrôle auto = ban. Évolution Midnight : moins de logique combat dans les addons ([news](https://news.blizzard.com/en-gb/article/24244638/how-midnights-upcoming-game-changes-will-impact-combat-addons)).
- **Verdict** : addons officiels + notes hors jeu **OK** ; Visor-like live info **NO**.

#### B4 — EVE Online (marché)

- ESI + tableur + **humain** qui confirme les ordres dans le client = pattern Track B classique.
- Botting client / RMT = **NO** (voir A4).
- **Fit monétisation** : trading ISK ≠ cash-out légal (RMT interdit) → utile surtout comme **apprentissage / contenu** (V-07), pas cash-out ETH.

#### B5 — Path of Exile / Torn

- **PoE** : sites trade via API ; macros **une** action après touche manuelle ; overlays/logs selon [developer docs](https://www.pathofexile.com/developer/docs). RMT services hors jeu interdits (ToU §7.h).
- **Torn** : outils API read-only + actions manuelles = conforme ; automation non-API = ban.

#### B6 — Chess.com vs Lichess (humain)

- **Chess.com** : aucune aide externe pendant parties vs humains ([Fair Play](https://www.chess.com/legal/fair-play)) — **même** un « conseil IA pendant la partie » = **NO**.
- **Lichess Board API** : clients tiers OK mais *« Engine assistance… forbidden »* pour comptes humains ; analyse **après** partie OK.
- **Assist OK** : préparation d’ouvertures / drills hors partie ; analyse post-game.

### 3.3 Patterns produit pour Agent 4 (Track B)

| Pattern | Monetisable ? | ToS-safe si… | Lien vecteurs |
|---------|---------------|--------------|---------------|
| Packs checklists / plans de draft | Oui (V-07/V-08) | Contenu hors client, pas de cheat bundled | V-07, V-08, V-13 |
| Coach post-VOD (notes IA) | Oui (service) | Pas d’overlay live compétitif | V-06, V-11 |
| Dashboard marché API → humain trade | Faible (pas cash-out jeux AAA) | API officielle only | V-13 recherche |
| Overlay live stats / auto-click | Non (risque ban) | — | **rejeter** |

---

## 4. Fit capital ~200 € / 30 j & risques

| Path | Probabilité d’aider le 2× en 30 j | Capital exposé | Blocages |
|------|-----------------------------------|----------------|----------|
| A Lichess bots | Très faible | ~0 € | Prix minuscules |
| A Second Life | Faible→moyenne (si KYC + skill) | temps + éventuel premium | KYC Tilia, courbe, fiat≠ETH |
| A Arènes crypto | Négative attendue (EV stake) | stake USDC/alt | Scam/gambling/chaîne |
| B Assist + contenu | Indirecte (via V-07/V-08) | ≤ outils 5–10 € | Temps opérateur |
| B Tournois humains + IA live | **Interdit** sur la plupart des jeux | — | Ban / ToS |

Risques transverses : ban compte, malware « tools », arnaques RMT, confusion bot autorisé ≠ bot rentable.

---

## 5. Recommandation Agent 4

**Poursuivre B (léger), pas A capital maintenant.**

1. **Track A** : aucun **GO** solide pour l’objectif ETH ~2× / 30 j. Lichess = ToS OK mais économie trop faible. Second Life = **WATCH** (nécessite KYC humain + temps). Arènes crypto agents = **NO** (risque NAV + anti-scam + hors L1).
2. **Track B** : **oui**, comme **complément** des vecteurs temps/contenu (V-06 / V-07 / V-08) : plans, checklists, reviews post-partie, outils API read-only — **jamais** d’automation d’inputs ni overlays compétitifs gris.
3. **Ni A ni B comme pilote capital** tant que spend non autorisé ; ne pas déplacer le focus hors vague 1 (V-06, V-04, V-11).
4. Stub catalogue : **V-13** (assist jeux / APIs autorisées) en `recherche` — voir [`vecteurs.md`](vecteurs.md).

**Décision autonome** : ne pas ouvrir de ledger d’allocation capital jeux ; documenter seulement. Annulation = retirer V-13 ou passer en `abandonné` si opérateur refuse le panier jeux.

---

## 6. Sources (index)

| # | Source | Usage |
|---|--------|-------|
| 1 | https://github.com/lichess-org/api/blob/master/doc/specs/lichess-api.yaml | A Lichess bots |
| 2 | https://lichess.org/page/event-tips | Prix tournois |
| 3 | https://wiki.secondlife.com/wiki/Linden_Lab_Official:Scripted_Agent_Policy | A SL bots |
| 4 | https://community.secondlife.com/knowledgebase/english/tilia-faq-r1533/ | KYC cashout |
| 5 | https://docs.bandforband.fun/agents | A agents crypto |
| 6 | https://isthiscoinascam.com/check/bandforband-fun | Anti-scam |
| 7 | https://pivarena.com/docs/api | A PIVArena |
| 8 | https://monerica.com/site/pivarena | Anti-scam / vérif |
| 9 | https://support.eveonline.com/hc/en-us/articles/8564030965660-Third-Party-Policies | EVE bots/RMT |
| 10 | https://store.steampowered.com/agreement/ | Steam automation |
| 11 | https://www.pathofexile.com/legal/terms-of-use-and-privacy-policy | PoE bots |
| 12 | https://www.arena.net/en/legal/user-agreement | GW2 automation |
| 13 | https://www.torn.com/api.html | Torn API |
| 14 | https://www.chess.com/legal/fair-play | Chess.com |
| 15 | https://support.faceit.com/hc/en-us/articles/360015788779-What-is-deemed-to-be-a-cheat | FACEIT |
| 16 | https://developer.riotgames.com/docs/valorant | Riot overlays |
| 17 | https://us.blizzard.com/en-us/company/about/termsofuse.html | Blizzard EULA |

*Les URLs ont été consultées pour cette synthèse (2026-11-21). Re-vérifier avant tout passage `prêt` / `actif`.*
