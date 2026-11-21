# Plan pilote — premiers vecteurs (J0–J14)

Capital : **~0,136 ETH ≈ 203 €** (WALLET-01).  
**Ce PR = docs seulement — aucun spend on-chain.**  
Plafonds : [`risk-limits.md`](risk-limits.md) · Catalogue : [`vecteurs.md`](vecteurs.md).

## 1. Pilotes retenus (3)

| Priorité | ID | Vecteur | Panier | Pourquoi maintenant |
|----------|----|---------|--------|---------------------|
| P0 | **V-06** | Freelance web / ops | Cash services | 0 € capital ; 1 mission 200–400 € ≈ objectif 2× ; taux EU junior/mid documentés ~35–75 €/h → un micro-gig de quelques heures suffit |
| P1 | **V-04** | Bounties / grants crypto | Cash services | Gas/outils seulement ; bounties docs/quests souvent 50–500 USD ; un bounty mid peut couvrir le 2× ; canal distinct du freelance classique |
| P2 | **V-11** | Recherche on-chain à façon | Cash services | Quasi 0 capital ; aligne compétences anti-scam / due diligence ; brief 150–300 € = levier fort ; sample public = actif réutilisable |

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
| V-04 (si un jour autorisé) | ≤ 5 % (≪ cap 10 %) | ≤ ~10 | ≤ ~0,007 | Gas quests / claims |
| V-11 (si un jour autorisé) | ≤ 5 % | ≤ ~10 | ≤ ~0,007 | Outils / API free-tier d’abord |
| **Engage pilotes max** | **≤ ~10 %** | **≤ ~20** | **≤ ~0,014** | Sous risk-limits |
| Non alloué / opportunité | reste | ~122+ | ~0,08+ | Reste liquide |

Toute activation capital exige : autorisation explicite + ledger rempli + triangulation + respect [`risk-limits.md`](risk-limits.md).

## 3. Critères succès / échec (fenêtre J0–J14)

### Succès (au moins 2 sur 3 pilotes « verts »)

| Pilote | Vert si… |
|--------|----------|
| V-06 | ≥ 1 offre publiée sur 2 canaux légitimes **et** ≥ 3 conversations qualifiées **ou** 1 proposition chiffrée envoyée |
| V-04 | Shortlist ≥ 5 bounties triangulées **et** ≥ 1 soumission / draft soumis **ou** 1 bounty won / paid |
| V-11 | 1 brief sample public publié **et** proposition format+prix sur ≥ 2 canaux |

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

### Transversal

- [ ] Relire [`AGENTS.md`](../AGENTS.md), [`risk-limits.md`](risk-limits.md), [`secrets.md`](secrets.md)
- [ ] Confirmer NAV approximatif (etherscan lecture seule) **sans** exposer de clé
- [ ] Bitwarden collection `Agent 4` : item WALLET-01 accessible ; soft-delete discipline OK
- [ ] Ouvrir / mettre à jour ledgers `ops/ledgers/V-06.md`, `V-04.md`, `V-11.md` (statut → `recherche`)
- [ ] Noter 1 hypothèse du jour + ≥ 2 sources web externes (règle challenge)

### V-06 — Freelance

- [ ] Rédiger 1 offre claire (stack, délai, prix cible 200–400 € ou TJM)
- [ ] Choisir 2 canaux légitimes (pas de « pay to apply »)
- [ ] Lister 5 cibles / mots-clés de recherche
- [ ] Anti-scam : template escrow / acompte

### V-04 — Bounties

- [ ] Inventorier 5 bounties ouvertes (Gitcoin / boards protocoles / docs) — liens officiels seulement
- [ ] Trianguler org + historique de paiement pour chacune
- [ ] Estimer €/h ; écarter si frais d’entrée
- [ ] Préparer 1 draft de soumission (texte) **sans** claim on-chain

### V-11 — Recherche

- [ ] Choisir 1 protocole blue-chip pour sample
- [ ] Outline brief (sources publiques, disclaimer « pas un conseil financier »)
- [ ] Définir prix + format (1–2 pages)
- [ ] Identifier 2 canaux de proposition

### Fin de J1

- [ ] Rapport `reports/daily/YYYY-MM-DD.md` (même si avant le créneau 07:00 suivant)
- [ ] Aucune clé / adresse privée / seed dans git
- [ ] PR / notes : confirmer **0 spend**

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

## 7. Hors scope de ce plan

- Tout spend / trade / bridge / stake.
- Merge de PR sans opérateur.
- Ouverture V-01…V-03, V-05, V-10 sans nouvelle décision documentée.
