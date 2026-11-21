# Plan pilote — premiers vecteurs (J0–J14)

Capital : **~0,136 ETH ≈ 203 €** (WALLET-01).  
**Ce PR = docs seulement — aucun spend on-chain.**  
Plafonds : [`risk-limits.md`](risk-limits.md) · Catalogue : [`vecteurs.md`](vecteurs.md) · Marchés agents : [`agent-markets.md`](agent-markets.md).

## 1. Pilotes retenus (3)

| Priorité | ID | Vecteur | Panier | Pourquoi maintenant |
|----------|----|---------|--------|---------------------|
| P0 | **V-06** | Freelance / agent markets | Cash services | 0 € capital ; 1 mission 200–400 € ≈ objectif 2× ; **canaux GO** : Virtuals ACP + Skyfire seller ([`agent-markets.md`](agent-markets.md)) — Free-Work/LaborX/Malt/Upwork écartés (ToS / KYC) |
| P1 | **V-04** | Bounties / Mech | Cash services | Gas/outils seulement ; **Olas Mech Marketplace** (turnover live) prioritaire vs Opire minuscule ; escrow on-chain préféré — fiche Day-0 [`pilots/olas-mech.md`](pilots/olas-mech.md) (**GO docs / NO spend** tant que Docker+bridge) |
| P2 | **V-11** | Recherche on-chain à façon | Cash services | Quasi 0 capital ; brief 150–300 € ; offre naturelle sur ACP / Mech / Skyfire MCP |

### Pourquoi pas les autres en vague 1

| Candidat | Décision | Recherche / raison |
|----------|----------|-------------------|
| V-01 Yield L1 | **Différé** | APR liquide staking ~2,2 % net (nov. 2026) → sur 80 €, rendement négligeable vs objectif 2×/30 j. Gas L1 actuellement bas, donc parcage **plus tard** si capital idle — pas un moteur. |
| V-02 / V-03 / V-05 | Différés | Exposent du capital + corrélation crypto ; attendre autorisation spend + triangulation protocole. |
| V-07 / V-08 / V-09 | Vague 2 | Funnel attention utile, mais conversion plus lente que cash services sur 14 j. |
| V-10 | Différé | Illiquidité + ticket spéculatif ; hors priorité J0. |
| V-12 | Backup | Si V-06/V-04 saturés sans lead ; 0 capital. |

**Hypothèse challengée** : « diversifier dès J0 dans 3 paniers dont DeFi ».  
**Verdict** : à ~200 € et objectif 2×/30 j, empiler du DeFi dilue le temps sans upside matériel. Diversification **par canal de revenu** (freelance / bounty / brief) d’abord ; ouvrir le panier préservation (V-01) quand un résiduel idle existe **et** que les ops capital sont autorisées.

## 2. Allocation brouillon (€ / ETH) — 0 spend tant que non autorisé

| Poste | % NAV | ≈ € | ≈ ETH | Statut |
|-------|-------|-----|-------|--------|
| Réserve (gas + buffer) | ≥ 30 % | ≥ ~61 | ≥ ~0,041 | **Obligatoire** — ne pas toucher |
| Floor gas L1 | (dans réserve) | ~15 | **0,01** | Floor dur |
| V-06 | 0 % | 0 | 0 | Temps seulement |
| V-04 / Mech (si un jour autorisé) | ≤ ~2,5 % (≪ cap 10 %) | **≤ ~5** (Mech gas) ; ≤ ~10 total V-04 | ≤ ~0,0035 | Voir [`pilots/olas-mech.md`](pilots/olas-mech.md) ; gas Gnosis only |
| V-11 (si un jour autorisé) | ≤ 5 % | ≤ ~10 | ≤ ~0,007 | Outils / API free-tier d’abord |
| **Engage pilotes max** | **≤ ~10 %** | **≤ ~20** | **≤ ~0,014** | Sous risk-limits |
| Non alloué / opportunité | reste | ~122+ | ~0,08+ | Reste liquide |

Toute activation capital exige : autorisation explicite + ledger rempli + triangulation + respect [`risk-limits.md`](risk-limits.md).

## 3. Critères succès / échec (fenêtre J0–J14)

### Succès (au moins 2 sur 3 pilotes « verts »)

| Pilote | Vert si… |
|--------|----------|
| V-06 | ≥ 1 offre publiée sur **2 canaux agent-friendly GO** (ACP / Skyfire / Olas) **et** ≥ 3 conversations qualifiées **ou** 1 job funded / proposition chiffrée |
| V-04 | Shortlist ≥ 5 opportunités triangulées (Mech tools / bounties escrow) **et** ≥ 1 draft soumis **ou** 1 payout |
| V-11 | 1 brief sample public publié **et** proposition format+prix sur ≥ 2 canaux GO agent-markets |

**Succès capital (hors scope spend actuel)** : si spend autorisé plus tard — 0 violation des caps ; PnL vecteur ≥ 0 après frais sur la fenêtre.

### Échec / pivot

| Pilote | Rouge si… | Pivot |
|--------|-----------|-------|
| V-06 | 14 j outreach documenté sans lead qualifié | Renforcer V-04/V-11 ; tester V-12 |
| V-04 | 3 sources « pay to apply » ou 0 bounty crédible après 20 scrutés | Pause V-04 ; temps → V-06/V-11 |
| V-11 | Demande de shill **ou** 14 j sans intérêt après sample | Temps → V-04/V-06 ; sample reste portfolio |

Kill individuels du catalogue restent applicables immédiatement (scam, seed, garde de fonds).

## 4. Checklist Jour 1 (sans spend)

À cocher dans le rapport du jour et/ou les ledgers. **Aucune tx, aucun achat, aucun bridge.**  
**Exécution Agent 4 :** 2026-11-21 — détail [`reports/daily/2026-11-21.md`](../reports/daily/2026-11-21.md) + ledgers V-06/V-04/V-11.

### Transversal

- [x] Relire [`AGENTS.md`](../AGENTS.md), [`risk-limits.md`](risk-limits.md), [`secrets.md`](secrets.md)
- [x] Confirmer NAV approximatif (etherscan lecture seule) **sans** exposer de clé
- [x] Bitwarden collection `Agent 4` : item WALLET-01 accessible ; soft-delete discipline OK
- [x] Ouvrir / mettre à jour ledgers `ops/ledgers/V-06.md`, `V-04.md`, `V-11.md` (statut → `recherche`)
- [x] Noter 1 hypothèse du jour + ≥ 2 sources web externes (règle challenge)

### V-06 — Freelance / agent markets

- [x] Rédiger 1 offre claire (stack, délai, prix cible 200–400 € ou TJM)
- [x] Choisir 2 canaux légitimes (pas de « pay to apply ») — **pivot 2026-11-21** : Free-Work + Freelance-informatique → **Virtuals ACP** + **Skyfire seller** ([`agent-markets.md`](agent-markets.md) GO)
- [x] Lister 5 cibles / mots-clés de recherche
- [x] Anti-scam : template escrow / acompte (+ escrow on-chain ACP/Skyfire)
- [ ] Publier l’offre / ouvrir les comptes agent — **bloqué** : runtime / wallet agent / éventuel compte Virtuals ; Free-Work email humain = backup seulement

### V-04 — Bounties / Mech

- [x] Inventorier 5 bounties / boards (scrutés + triangulation) — liens officiels seulement
- [x] Trianguler org + liveness / paiement (OnlyDust fermé, Algora 404, Opire minuscule)
- [x] Shortlist marchés agents (Olas Mech **GO**, Opire WATCH) — [`agent-markets.md`](agent-markets.md)
- [x] Estimer €/h ; écarter si frais d’entrée ou hors éthique
- [x] Préparer 1 draft de soumission (texte) **sans** claim on-chain
- [ ] Soumettre / claim / déployer Mech — **non** (0 spend ; GitHub humain ; infra Mech non bootstrap)

### V-11 — Recherche

- [x] Choisir 1 protocole blue-chip pour sample — Lido / stETH
- [x] Outline brief (sources publiques, disclaimer « pas un conseil financier »)
- [x] Définir prix + format (1–2 pages, 180–250 €)
- [x] Identifier 2 canaux de proposition — **pivot** : LaborX + Free-Work → **Virtuals ACP** + **Olas/Skyfire**
- [ ] Publier sample public + propositions — **bloqué** comptes agent / rédaction J2

### Fin de J1

- [x] Rapport `reports/daily/2026-11-21.md` (même si avant le créneau 07:00 suivant)
- [x] Aucune clé / adresse privée / seed dans git
- [x] PR / notes : confirmer **0 spend**

## 5. Semaine 1–2 (aperçu, toujours sous autorisation)

| Jour | Focus |
|------|--------|
| J1 | Checklist §4 |
| J2–J3 | Outreach V-06 + shortlist V-04 + draft sample V-11 |
| J4–J7 | Soumissions / conversations ; première revue succès-échec partielle |
| J8–J14 | Doubler le canal qui convertit ; pivot si rouge ; **pas** d’ouverture DeFi sans autorisation |

## 6. Recherche & challenge (obligatoire)

Pour chaque décision « on garde / on drop ce pilote » :

1. Énoncer l’hypothèse.
2. Citer ≥ 2 sources externes (docs officielles, rate cards, gas trackers, boards).
3. Trancher dans le ledger.

Exemples déjà utilisés pour ce plan (nov. 2026) :

- Gas / staking L1 : trackers gas + docs liquid staking (APR ~2 % net → V-01 non prioritaire).
- Rates freelance EU 2026 (bandes ~35–75 €/h junior/mid).
- Bounties Web3 : ordres de grandeur docs 50–200 USD, mid plus haut sur boards protocoles.
- Cadre risk retail : caps d’exposition + échelle de drawdown (voir risk-limits).

## 7. Pilote Olas Mech (pointeur)

Fiche opérationnelle Day-0 : [`pilots/olas-mech.md`](pilots/olas-mech.md).

| Décision | Contenu |
|----------|---------|
| Phase 1 | **GO** — recherche + checklist + cap ≤ **5 €** |
| Phase 2 | **NO** spend live (2026-11-21) — Docker absent, bridge L1→Gnosis non autorisé, ops capital non ouvertes |
| Prochaine | Dry-run free (§6.B de la fiche) ; escalade infra/bridge si priorité earn agent |

## 8. Hors scope de ce plan

- Tout spend / trade / bridge / stake (sauf si autorisation ultérieure sous caps).
- Merge de PR sans opérateur (sauf préférence opérateur contraire documentée).
- Ouverture V-01…V-03, V-05, V-10 sans nouvelle décision documentée.
- Virtuals fund-transfer · Skyfire (vague suivante) · game bots · Free-Work signup.
