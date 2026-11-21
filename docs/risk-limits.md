# Limites de risque dures — Agent 4

Capital de référence (WALLET-01) : **~0,136 ETH ≈ 203 €** (ordre de grandeur ; recalculer le NAV à chaque rapport).  
Ces plafonds sont **non négociables** tant qu’ils n’ont pas été révisés par PR + revue opérateur.  
**Ce document cadre** — les spends réels restent jugés par l’agent **sous ces caps** (pas de confirmation opérateur par dépense).

Sources internes : [`vecteurs.md`](vecteurs.md), [`pilot-plan.md`](pilot-plan.md), [`AGENTS.md`](../AGENTS.md).

## 0. Autonomie capital & multi-chaîne

| Règle | Contenu |
|-------|---------|
| **Juge agent** | Trade / bridge / gas / outils : l’agent décide **seul** si risk-limits + anti-scam OK. Pas de porte « OK spend » humaine. |
| **Multi-chaîne** | L1-only était un biais erroné. Bridge + wallets sur **Sui, Solana, BTC, L2s**, etc. = OK sous caps. |
| **Clés** | Tout seed / clé privée → Bitwarden collection `Agent 4` (item dédié) ; soft-delete si retrait. Jamais git. |
| **Floor gas** | Conserver **≥ 0,01 ETH liquide sur L1** (ou équivalent documenté) pour exit / ops, **même** après bridges. |
| **Horizon** | Caps / kills ci-dessous **ne** tuent **pas** un vecteur seulement pour « trop lent pour 30 j » — voir §3 note horizon. |

## 1. NAV, réserve et engage

| Contrôle | Plafond | ≈ EUR | ≈ ETH | Notes |
|----------|---------|-------|-------|-------|
| **NAV dédié** | 100 % | ~203 € | ~0,136 | Wallet `0x0617…5fCA` + soldes multi-chaîne **cités** (pas de clés) |
| **Engage total max** | **≤ 70 %** NAV | ~142 € | ~0,095 | Somme de toutes les allocations actives (toutes chaînes) |
| **Réserve obligatoire** | **≥ 30 %** NAV | ~61 € | ~0,041 | Gas + buffer opportunité + sorties |
| **Floor gas liquide L1** | **≥ 0,01 ETH** | ~15 € | 0,01 | Toujours disponible pour exit / ops ; hors positions |
| **Buffer opportunité** | ≥ 15 % NAV | ~30 € | ~0,020 | Inclus dans la réserve 30 % |

Règle : si le floor gas ou la réserve 30 % serait violé par un nouvel engage → **ne pas engager**.

## 2. Caps par vecteur (% NAV)

Alignés sur [`vecteurs.md`](vecteurs.md). **Non cumulatifs à 100 %** — le plafond global 70 % prime.

| ID | Vecteur | Max % NAV | Max ≈ € | Max perte tolérée (kill soft) |
|----|---------|-----------|---------|--------------------------------|
| V-01 | Yield conservateur (L1/L2 blue-chip) | 40 % | ~80 | −50 % de l’allocation **ou** APY net < gas 14 j |
| V-02 | Points / airdrop | 25 % | ~50 | Gas > 30 % de l’allocation sans preuve d’éligibilité |
| V-03 | Écarts / info-arb | 15 % / oppo. | ~30 | Stop net après frais ; −100 % de l’oppo. max |
| V-04 | Bounties / grants | 10 % (gas/outils) | ~20 | 0 dépôt « éligibilité » ; kill si frais d’entrée |
| V-05 | LP prudent | 20 % | ~40 | IL scénario > fees **ou** −50 % allocation |
| V-06 | Freelance | 0 % marché (+≤5 % outils) | ~10 outils | Temps : kill 14 j sans lead (voir vecteur) |
| V-07 | Contenu | 5 % | ~10 | 21 j sans engagement |
| V-08 | Micro-produit | 15 % | ~30 | Build > 10 j sans MVP |
| V-09 | Affiliation | 0–5 % | ~10 | Programme non officiel / faux avis |
| V-10 | Domaines | 25 % (≤3 actifs) | ~50 | 21 j sans offre / trademark |
| V-11 | Recherche on-chain | 5 % | ~10 | Demande de shill **ou** 14 j sans intérêt |
| V-12 | Modération / community | 0 % | 0 | Rôle exigeant garde de fonds |
| V-13 | Jeux assist / API autorisée | 5 % outils | ~10 | Automation ToS / arène non triangulée / 21 j sans livrable |

## 3. Kill switches (pertes / drawdown)

Échelle inspirée des pratiques retail (seuils de drawdown gradués + revue humaine sur hard stop). Adapter au **NAV dédié**, pas à un bot de trading.

| Niveau | Déclencheur | Action |
|--------|-------------|--------|
| **Soft jour** | −2 % NAV (~4 €) en 24 h **sur ops capital** | Stop nouveaux engages capital ; revue anti-scam |
| **Soft semaine** | −5 % NAV (~10 €) sur 7 j | Flatten / retirer ce qui est réversible ; pause capital ; note rapport |
| **Hard drawdown** | −15 % NAV (~30 €) vs pic ou vs NAV de départ (le plus bas) | **Kill all** ops capital ; escalade opérateur ; seuls vecteurs **temps** (V-06/V-04/V-11/V-12) peuvent continuer |
| **Anomalie** | UI seed / signature hors scope / exploit protocole / contrepartie non triangulée | Kill immédiat du vecteur + isolation wallet si besoin |
| **Gas spike** | Coût tx estimé > **5 %** de l’allocation concernée | Reporter ; ne pas forcer |

Les vecteurs « temps » n’ont pas de stop-loss € : appliquer les **kill** du catalogue (délais, scam, impayés).

**Note horizon** : un kill catalogue basé sur « pas de lead en N jours » reste valide (coût d’opportunité). Un vecteur **lent mais EV positif** après ce filtre → **re-rang** (baisse priorité), **pas** abandon automatique parce que la fenêtre 30 j est trop courte. Le classement vs autres agents sur des mois prime sur le discard précipité.

## 4. Cap d’engage (pilotes & routine)

Avant **chaque** spend (juge agent, pas opérateur) :

1. Allocation écrite dans le ledger `ops/ledgers/V-XX.md` + mention rapport du jour.
2. Triangulation anti-scam ≥ 2–3 sources **et** recherche externe documentée (voir §6).
3. Downside max ≤ cap vecteur **et** engage total post-trade ≤ 70 %.
4. Floor gas 0,01 ETH L1 conservé **après** la tx / bridge.
5. Une seule nouvelle allocation capital / jour calendaire (Europe/Paris), sauf kill/exit.
6. Bridge : protocole / bridge **triangulé** ; coût bridge **dans** le cap du vecteur ; pas de fragmentation qui casse le floor L1.

**Cap d’engage pilote** — voir [`pilot-plan.md`](pilot-plan.md) :

| Pilote | Cap engage | Notes |
|--------|------------|-------|
| V-06 / ACP | 0 € marché ; si tests sandbox : ≤ **5 €** USDC/gas Base ([`pilots/virtuals-acp.md`](pilots/virtuals-acp.md)) | Temps d’abord ; spend outils sous juge agent + caps |
| V-04 / Mech | ≤ **5 €** gas Gnosis (fiche [`pilots/olas-mech.md`](pilots/olas-mech.md)) ; ≤ 10 € V-04 total | Sous le cap 10 % ; bridge Gnosis OK si triangulé + floor L1 OK |
| V-11 | ≤ 10 € outils/API | Sous le cap 5 % ; prix offre ACP = **5–25 USDC** (pas engage capital) |
| **Total pilotes** | **≤ ~20 €** | ≪ 70 % ; le reste reste liquide |

## 5. Interdits absolus à cette taille de capital (~200 €)

Ne **jamais** faire avec ce NAV :

1. **Levier / looping** (Aave recursive, perp, margin) — un seul mouvement peut liquider le compte.
2. **All-in** sur un protocole, airdrop, domaine ou client.
3. **Bridge non triangulé** ou vers protocole / chaîne sans sources indépendantes (risque + fragmentation du floor gas). Multi-chaîne **triangulée** = autorisée sous caps.
4. **Vault / farm / « points »** non audités ou annoncés uniquement via DM / mirror.
5. **Payer pour être éligible** (frais d’inscription bounty, « whitelist » payante).
6. Signer quoi que ce soit qui demande **seed**, export de clé, ou `eth_sign` / permit illimité non compris.
7. **Garder des fonds** pour un tiers / multisig improvisé / rôle « treasury ».
8. Typosquatting, faux avis, shill non déclaré, manipulation de marché.
9. Empiler V-01+V-02+V-03+V-05 au-delà du cap global 70 % (corrélation crypto).
10. Compter sur le **yield seul** pour le 2× : à ~2 % APR net, ~80 € → ≪ 2 € / an — utile comme **parcage**, pas comme moteur (hypothèse challengée, nov. 2026).
11. Réviser ces plafonds « à chaud » après une perte sans PR.
12. Illégal / scam / harm (voir `AGENTS.md` règles 1–2).

**Retiré (correction opérateur 2026-11-21)** : interdiction globale « pas de bridge / pas de spend sans auth opérateur » — remplacée par autonomie sous ce document.

## 6. Challenge des hypothèses (règle dure)

Avant de **valider ou rejeter** une hypothèse de risque, d’allocation ou de vecteur :

1. **Énoncer** l’hypothèse (ex. « le yield L1 contribue au 2× »).
2. **Chercher** ≥ 2 sources web / docs officielles **externes** (pas la seule mémoire du modèle).
3. **Consigner** liens + conclusion courte dans le ledger ou le rapport quotidien.
4. Si les sources contredisent le plan → **ajuster le plan**, pas les faits.

Cette règle s’applique aussi aux kill, aux caps et au choix des pilotes.  
Ne pas rejeter une thèse **seulement** parce que le payoff 30 j est improbable — noter le rang / horizon plus long.

## 7. Recalcul

- NAV et €/ETH (et autres actifs) : à chaque rapport **07:00 Europe/Paris**.
- Si NAV change de > 10 % (PnL, transfert) → recalculer tous les € du tableau ; les **%** restent la source de vérité.
