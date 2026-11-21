# Repass verdicts — multi-chaîne / spend autonome / horizon

**Date :** 2026-11-21 · **Docs only** (0 spend dans ce PR).  
**Prefs :** multi-chaîne OK · spend juge agent sous [`risk-limits.md`](risk-limits.md) · 2×/30 j primaire mais **pas** de kill « trop lent » seul · clés → Bitwarden `Agent 4`.

Légende : **REOPEN** = réactiver recherche / path sous caps · **WATCH** = garder en veille active (rang, pas discard) · **KEEP CLOSED** = motif scam / ToS / EV négative / blocker non-préférences inchangé.

## Table

| Item | Ancien motif de fermeture / pénalité | Nouveau verdict | Raison (1 ligne) |
|------|--------------------------------------|-----------------|------------------|
| Bridge L1 → L2 / autres chaînes (global) | « Bridge sans auth opérateur » | **REOPEN** | Multi-chaîne + spend autonome OK si triangulation + floor gas L1. |
| V-01 Yield | Différé : trop lent / APR << 2×30 j | **WATCH** | Parcage idle utile ; re-rang, pas kill horizon. |
| V-02 Points / airdrop | Attendre auth spend | **REOPEN** | Recherche + micro-spend sous caps/juge agent ; rester triangulé. |
| V-03 Écarts / info-arb | Attendre auth spend | **REOPEN** | Idem ; stop net après frais inchangé. |
| V-05 LP prudent | Attendre auth spend | **REOPEN** | Idem ; IL kill soft inchangé. |
| V-04 / Olas Mech Phase 2 | Bridge + spend « non autorisés » | **REOPEN** (bridge/spend) / **KEEP CLOSED** live | Auth spend n’est plus un blocker ; **Docker** reste le NO live. |
| V-06 / ACP spend ≤ 5 € | « Autoriser spend » opérateur | **REOPEN** (policy) / **KEEP CLOSED** live | Caps OK sans auth spend ; **OAuth/compte humain** reste blocker. |
| V-07 Contenu | Vague 2 / lent | **WATCH** | Horizon multi-mois OK ; priorité basse vs cash services. |
| V-08 Micro-produit | Vague 2 / lent | **WATCH** | Idem. |
| V-09 Affiliation | Vague 2 / lent | **WATCH** | Idem ; kill faux avis inchangé. |
| V-10 Domaines | Illiquidité / ticket spéculatif | **KEEP CLOSED** (vague 1) | Motif EV/illiquidité, pas L1 ; réévaluer plus tard. |
| V-12 Modération | Backup | **WATCH** | Toujours 0 capital ; kill garde de fonds. |
| V-13 Jeux (catalogue) | Spend non autorisé + biais L1 | **WATCH** | Multi-chaîne OK ; kills = ToS / scam / EV. |
| Lichess bots | Fit 30 j faible | **WATCH** | Économie faible ≠ kill ; rang bas. |
| Second Life | « hors ETH L1 » + KYC + lent | **WATCH** / **GO conditionnel** | Fiat≠ETH n’est plus un kill ; post-KYC + pilote LSL/Marketplace Basic — détail [`second-life-monetization.md`](second-life-monetization.md). |
| Arènes crypto (bandforband, PIVArena, etc.) | « ≠ ETH L1 » + stake/scam | **KEEP CLOSED** | Motif réel = gambling / scam / EV stake — **pas** la chaîne. |
| Pawtato Land bots (A) | ToS + « hors L1 » | **KEEP CLOSED** (A) | ToS no-bot ; Sui n’est plus un kill. |
| Pawtato assist (B) | Fit 30 j / hors L1 | **WATCH** | Assist OK ; lenteur → rang, pas discard. |
| Pawtato capital | Spend non auth + EV | **KEEP CLOSED** | NFT gate + liq. fine + EV 2× faible (≠ auth spend). |
| Clash of Coins Agentic (A) | Spend non auth + EV Risk-to-Earn | **WATCH** | API officielle OK ; micro-spend possible sous caps **après** preuve cashout — pas GO. |
| Clash assist (B) | Temps / 30 j | **WATCH** | Aligné prefs ; pas moteur 2× seul. |
| Clash capital / passes | Spend non auth + Risk-to-Earn | **KEEP CLOSED** | EV / token risk — pas le biais L1 ni l’auth spend. |
| Olas Mech earn 30 j | « NOT VIABLE 30 j » | **WATCH** | Rails OK ; earn lent → rang long horizon, pas discard. |
| Skyfire seller | NOT VIABLE earn 30 j | **WATCH** | Rail confirmé ; trafic non prouvé ; horizon long OK. |
| Opire / Agrenting / GetAgentic | Faible fit 30 j | **WATCH** | Inchangé : maturité/payouts ; re-probe, pas kill vitesse. |
| Agentverse earn / nullpath / Vangrid buyer | NO earn | **KEEP CLOSED** | Monetization absente / mort / mauvais côté — inchangé. |
| Free-Work / LaborX / Malt / Upwork | Prefs / KYC | **KEEP CLOSED** | Prefs opérateur inchangées. |

## Implications ops (docs)

1. Mettre à jour [`AGENTS.md`](../AGENTS.md), [`risk-limits.md`](risk-limits.md), [`operating.md`](operating.md), [`pilot-plan.md`](pilot-plan.md).
2. Ajuster wording dans [`game-paths.md`](game-paths.md), [`game-targets-pawtato-clash.md`](game-targets-pawtato-clash.md), [`agent-markets.md`](agent-markets.md), [`vecteurs.md`](vecteurs.md), pilotes.
3. **Aucun** live spend / bridge dans ce PR.
4. Prochaines spends hors PR : ledger + triangulation + caps uniquement.

## Challenge (prefs)

| Hypothèse | Verdict |
|-----------|---------|
| « L1-only protégeait le NAV » | **Rejetée comme règle dure** — floor gas L1 + caps suffisent ; multi-chaîne triangulée OK. |
| « Chaque spend exige l’opérateur » | **Rejetée** — juge agent sous risk-limits. |
| « Trop lent pour 30 j ⇒ abandon » | **Rejetée** — re-rang / classement multi-mois. |
