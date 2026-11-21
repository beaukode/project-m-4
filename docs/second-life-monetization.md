# Second Life — potentiel de monétisation (Agent 4)

Recherche approfondie pour l’opérateur. **Aucun spend / ops capital** dans ce document.  
Langue : FR. Synthèse : **2026-11-21**.  
Contexte court : [`game-paths.md`](game-paths.md) §A2 · vecteur [`V-13`](vecteurs.md) · prefs (multi-chaîne OK, self-spend sous risk-limits, lenteur 30 j ≠ kill seul).

**Verdict** → **WATCH** (candidat **GO conditionnel** après KYC humain + pilote service LSL). Voir [§6](#6-verdict-agent-4).

---

## 1. Méthode

| Règle | Application |
|-------|-------------|
| Triangulation | ≥ 2 sources indépendantes par claim majeur (officiel Linden/wiki/KB + source secondaire) |
| Anti-scam | LindeX / Tilia officiels seulement ; pas d’échange L$ tiers |
| Capital | Fit vs ~200 € NAV + caps [`risk-limits.md`](risk-limits.md) ; **0 engage** ici |
| Prefs 2026-11-21 | Multi-chaîne OK (fiat→ETH) ; self-spend possible sous risk-limits ; ne pas tuer un vecteur **seulement** parce qu’il est trop lent pour 2×/30 j |

---

## 2. Économie L$ → USD (cashout)

### 2.1 Flux

```
Gagner L$ (ventes / services)
    → (option) Marketplace −10 % commission
    → Vendre L$ sur LindeX (−5 % sell fee)
    → Crédit USD sur wallet Tilia
    → Process Credit / payout (−5 % payout fee, min US$3 / max US$500)
    → PayPal / autre méthode selon localisation
```

| Étape | Détail | Sources |
|-------|--------|---------|
| Monnaie | **Linden Dollar (L$)** — monnaie virtuelle ; pas une crypto | [ToS §3–4](https://secondlife.com/app/tos/tos.php) |
| Marché | **LindeX** : marché officiel d’achat/vente L$↔USD | [Pricing](https://secondlife.com/corporate/pricing) |
| Taux indicatif | **~246 L$ / US$1** (feed LindeX, 2026-11-21) → ≈ **0,0041 USD / L$** | [api.secondlife.com/datafeeds/lindex.txt](https://api.secondlife.com/datafeeds/lindex.txt) |
| Frais achat L$ | **11 %** (min US$0,49 / max US$29,99) | [Pricing](https://secondlife.com/corporate/pricing) (au 12 nov 2026) |
| Frais vente L$ | **5 %** | idem |
| Frais payout USD | **5 %** (min US$3,00 / max US$500) sur la liste pricing ; frais effectifs aussi liés à la méthode Tilia (2026) | [Pricing](https://secondlife.com/corporate/pricing) · [Process Credit](https://lindenlab.freshdesk.com/support/solutions/articles/31000135224-process-credit-withdrawal-requests) |
| Minimum payout | **US$3 + frais** ; max **US$9 999 − frais** / tx | Process Credit KB |
| Délai payout | Typiquement **5–10 jours ouvrés** ; jusqu’à **30 j** | Process Credit KB · [ToS §4.3](https://secondlife.com/app/tos/tos.php) |
| Marketplace | Commission vendeur **10 %** du prix listé (depuis déc. 2019) | [Blog Marketplace](https://community.secondlife.com/blogs/entry/3016-the-return-of-last-names-and-changes-to-marketplace-events-premium) · [KB Selling](https://community.secondlife.com/knowledgebase/english/selling-in-the-marketplace-r88/) |

**Effet net approximatif** (vente LindeX + payout, hors Marketplace) :  
`USD reçu ≈ (L$ / taux) × 0,95 × 0,95` → ≈ **~90 %** du USD LindeX brut.  
Exemple : **L$25 000** ≈ US$101 brut → ≈ **US$91** après 2×5 % (ordre de grandeur ; frais min/méthode peuvent dégrader les petits montants).

### 2.2 KYC Tilia — Agent 4 peut-il cashouter seul ?

**Non.** Le *process credit* (sortie USD réelle) exige une **vérification d’identité humaine** via Tilia.

| Élément | Exigence | Source |
|---------|----------|--------|
| Qui | Nom, adresse, date de naissance, SSN (US) **ou** pièce d’identité gouvernementale (non-US) | [Tilia FAQ](https://community.secondlife.com/knowledgebase/english/tilia-faq-r1533/) |
| Preuve adresse | Facture / relevé ≤ 3 mois, etc. | Tilia FAQ |
| Âge | **≥ 18 ans** pour process credit | Tilia FAQ |
| Quand | À la **première** demande de payout (ou soumission volontaire avant) | Tilia FAQ |
| Sans KYC | On peut **acheter / dépenser / vendre L$** ; le **USD reste bloqué** sur le wallet Tilia | Tilia FAQ · [Account balance](https://community.secondlife.com/knowledgebase/english/account-balance-r1/) |
| Destinataire | Payout vers un compte **contrôlé par le titulaire** (pas un PayPal tiers) | Process Credit KB |

**Implication Agent 4**

| Action | Qui |
|--------|-----|
| Créer compte SL, builder/scripter, Marketplace, bots **déclarés** | Agent possible (ops docs + outils) |
| KYC Tilia / pièce d’identité / PayPal nominatif | **Opérateur humain uniquement** (escalade AGENTS.md) |
| W-8BEN / impôts (si seuils) | Opérateur + conseil fiscal perso |

Escalade **justifiée** au sens AGENTS.md : KYC personne **et** potentiel documenté (cashout officiel + bots légitimes + niche LSL/services).

### 2.3 Abonnements (coût d’entrée)

| Tier | Prix listé (USD) | Pertinence A4 |
|------|------------------|---------------|
| Basic (free) | 0 | Suffisant pour Marketplace + scripting freelance |
| Plus | 5,99 / mois | Optionnel |
| Premium | 12,99 / mois (ou ~119,88 / an) | Land Mainland, stipends, avantages créateur |
| Premium Plus | 29,99 / mois | Régions / land scale — **hors budget** ~200 € |

Sources : [Pricing](https://secondlife.com/corporate/pricing) · [Premium](https://secondlife.com/premium).  
**Note risk-limits** : Premium ~13 USD/mois **dépasse** le cap V-13 outils (~10 €) → soit rester en **Basic**, soit **réviser le cap / ledger** avant subscribe.

---

## 3. Chemins d’earn légitimes

### 3.1 Cartographie (légal vs interdit)

| Path | Légitime ? | Notes | Sources |
|------|------------|-------|---------|
| Contenu (mesh, clothes, textures, anims) + Marketplace / boutique | Oui | Compétition forte ; portfolio + releases régulières | [KB Selling](https://community.secondlife.com/knowledgebase/english/selling-in-the-marketplace-r88/) · forums Merchants |
| Scripting LSL (vendors, HUDs, rental boxes, security) | Oui | Très aligné compétence agent ; commissions L$5k–50k citées | [SL Entrepreneur Guide — scripting](https://harmony-group.gitbook.io/sl-entrepreneurs-guide/content-creation-and-digital-artistry) |
| Services (builds custom, consulting, events ops) | Oui | Humain + agent assist | Communauté / Reddit 2025 |
| Locations / land rental | Oui (si Premium+/capital) | Ticket élevé (région ~US$349 + tier mensuel) | [Pricing](https://secondlife.com/corporate/pricing) · guide earnings |
| Scripted Agents (NPC, greeter, service bot) **déclarés** | Oui si usages légitimes | Voir §4 | [Scripted Agent Policy](https://wiki.secondlife.com/wiki/Linden_Lab_Official:Scripted_Agent_Policy) |
| Camping / traffic boost (bots ou pads pour gamer le search) | **Non** | Ban / ToS | Scripted Agent Policy · [T&C §5.i](https://lindenlab.com/legal/second-life-terms-and-conditions) · [Mainland policies](https://wiki.secondlife.com/wiki/Linden_Lab_Official:Mainland_policies) |
| Jeux de hasard / « banks » virtuelles | **Non** | Policies dédiées | T&C §5.ii–iii |
| CopyBot / vol de contenu | **Non** | Ban + copyright | [Bot wiki](https://wiki.secondlife.com/wiki/Bot) |
| Échange L$ hors LindeX | **À éviter** | Scam / ToS risk | Pratique anti-scam A4 |

### 3.2 Fit Agent 4 (ordre de priorité)

1. **Services LSL / tooling** (rental box, vendor, NPC service, automation **autorisée**) — faible capital, skill stack agent.  
2. **Micro-produits Marketplace** (scripts packaged, outils creators) — Basic OK.  
3. **Assist contenu** (docs, marketing listings) pour un créateur humain — Track B.  
4. **Land / club / région** — **NO** à cette taille de NAV (tier + CAPEX).

---

## 4. Bots / Scripted Agents — autorisé vs banni

### Autorisé (sous conditions)

- Bots / NPC / inviters / services automatisés pour usages **légitimes**.
- Compte **principalement** scripted → **déclarer** le statut sur la page Scripted Agent Status.
- Respect privacy controls ; pas de contournement.
- Charge raisonnable sur régions / search.

Sources : [Scripted Agent Policy](https://wiki.secondlife.com/wiki/Linden_Lab_Official:Scripted_Agent_Policy) · [Bot wiki](https://wiki.secondlife.com/wiki/Bot) · [AGENT_AUTOMATED](https://wiki.secondlife.com/wiki/AGENT_AUTOMATED).

### Interdit (extrait)

| Interdit | Détail |
|----------|--------|
| Traffic gaming | Bots / camping pour gonfler le score Traffic / search |
| Spam | \> **5 000** messages / jour calendaire (tous bots du même user agrégés) |
| Mainland sniping | Automation d’achat de parcelles Mainland |
| Privacy bypass | Contournement des contrôles de confidentialité |
| Charge abusive | Bots coincés InfoHubs, load search, nuisance |

Sanction : suspension / terminaison de compte (policy).

**Prefs jeux A4** : bots seulement si ToS l’autorisent → SL **oui**, pour usages listés ; **jamais** camping / traffic / spam.

---

## 5. Ordres de grandeur € / mois, time-to-first-euro, capital

> Les fourchettes ci-dessous viennent de **guides / forums / Reddit**, pas de Linden Lab. Traiter comme **ordres de grandeur**, pas comme prévision.

### 5.1 Fourchettes (brut L$, puis € approximatif)

Taux de travail : **~246 L$ = 1 USD** ; **1 USD ≈ 0,92 €** (ordre ; ne pas figer FX).  
Après stack frais (~10 % Marketplace éventuel + 5 % sell + 5 % payout), diviser encore.

| Activité | L$/mois (guide) | ≈ USD brut | ≈ € net cashout (ordre) | Source |
|----------|-----------------|------------|-------------------------|--------|
| Surveys / entry tasks | 2k–10k | 8–40 | ~5–30 | [Earnings overview](https://harmony-group.gitbook.io/sl-entrepreneurs-guide/earnings-overview-summary-by-activity) |
| Host / dancer | 5k–60k | 20–240 | ~15–180 | idem |
| Scripter établi | 20k–500k+ | 80–2 000+ | ~60–1 500+ | idem + page scripting |
| Store Marketplace (créateur) | 50k–5M+ | 200–20k+ | très large | idem |
| Land rental 1 région | 50k–150k | 200–600 | après tier USD | idem |

**Réalité communauté (2025)** : gagner de « vrais » USD est **possible** mais **lent** ; beaucoup ne couvrent que leurs dépenses SL ; les full-time ont des années d’expérience / niche ([r/secondlife](https://www.reddit.com/r/secondlife/comments/1i80s8w/waitcan_you_actually_make_real_money_from_here/) ; [Merchants forum](https://community.secondlife.com/forums/topic/519138-is-it-still-worth-it/)).

### 5.2 Time-to-first-euro (scénario Agent 4)

| Étape | Délai typique |
|-------|----------------|
| Compte + payment info + store Marketplace (≥ 5 j d’âge) | 5–10 j |
| KYC Tilia (opérateur) | 1–3 j typ. ; jusqu’à 30 j | 
| Premier L$ gagné (si skill LSL/service déjà prêt) | jours–semaines |
| Première vente LindeX + process credit reçu | +5–10 j ouvrés après vente |
| **Premier € sur PayPal** | **souvent 2–6+ semaines** si exécution serrée ; **mois** si apprentissage / niche à trouver |

### 5.3 Capital nécessaire

| Mode | Capital | Fit ~200 € |
|------|---------|------------|
| Basic + scripting / Marketplace | ~0–20 € (uploads, outils) | **Oui** (sous cap V-13 / outils) |
| Premium | ~13 USD/mois | Borderline vs cap 10 € V-13 |
| Boutique in-world + parcel | dizaines–centaines USD/mois | **Non** prioritaire |
| Région privée | US$349 + ~60–199+/mois | **NO** à cette NAV |

---

## 6. Risques

| Risque | Niveau | Mitigation |
|--------|--------|------------|
| Ban ToS (camping, spam, gambling, CopyBot) | Élevé si dérive | Stick Scripted Agent Policy ; déclarer bots ; 0 traffic farming |
| Scams L$ / phishing viewer / « double money » | Élevé | LindeX + viewers officiels / TPV whitelist ; jamais seed |
| KYC impossible / opérateur refuse | Bloquant cashout | Documenter ; garder L$ pour fees SL ou abandonner path |
| Fiscalité (US 1099-K / W-8BEN ; impôts locaux FR) | Moyen à volume | High-level seulement : Linden collecte W-9 / W-8BEN aux seuils ; **pas un conseil fiscal** — [Tax FAQ](https://wiki.secondlife.com/wiki/Linden_Lab_Official:Required_Tax_Documentation_FAQ) · [blog](https://community.secondlife.com/blogs/entry/1094-required-tax-documentation) |
| Illiquidité / temps | Moyen | Prefs : lenteur OK si EV+ ; kill sur 0 traction mesurable |
| Conversion fiat→ETH | Faible ops | Prefs multi-chaîne OK ; frais CEX à budgéter |
| Contenu Adult / maturité | Réputation / ToS | Éviter niches Adult pour A4 sauf décision opérateur |

---

## 7. Verdict Agent 4

### **WATCH** — pas **NO**, pas **GO** plein

| Critère | Lecture |
|---------|---------|
| ToS bots | **Favorable** (scripted agents légitimes + déclaration) |
| Cashout réel | **Oui** via LindeX/Tilia — rare parmi les « game paths » |
| Autonomie agent | **Cassée sur KYC** → humain obligatoire pour € |
| EV vs 2×/30 j | Faible en 30 j ; **prefs** : ne pas kill pour lenteur seule |
| Capital | Basic/services OK ; land/Premium+ non |
| Rang vs autres agents (mois) | Peut contribuer si niche LSL + KYC fait |

**Conditions pour passer en GO (pilote)**

1. Opérateur accepte d’être **titulaire KYC / PayPal** (compte à son nom).  
2. Pilote **Basic** : 1 offre service LSL ou 1 produit Marketplace (pas de land).  
3. Spend ≤ caps (uploads/outils) ; **pas** Premium tant que cap V-13 non révisé.  
4. Bots éventuels : **déclarés** + usages service/NPC uniquement.  
5. Kill : 21 j post-lancement sans L$ gagnés **ou** pression camping/scam **ou** KYC refusé.

**Pourquoi pas NO** : path monétisable officiel, bots autorisés, prefs acceptent l’horizon multi-mois.  
**Pourquoi pas GO immédiat** : dépendance KYC humain + courbe métier + EV 30 j faible + Premium/land hors budget.

---

## 8. Prochaines étapes concrètes (si WATCH poursuivi)

| # | Action | Owner | Bitwarden / notes |
|---|--------|-------|-------------------|
| 1 | Décision opérateur : **oui/non KYC Tilia** pour cashout | Humain | — |
| 2 | Créer compte Second Life (Basic) + payment info (sans payout) | Agent + humain email | Item proposé : `SL-01 Second Life account` (login only ; **pas** KYC docs dans git) |
| 3 | Soumettre KYC Tilia + lier PayPal **contrôle opérateur** | Humain | Item : `SL-02 Tilia/PayPal payout (réf.)` — métadonnées seulement, **jamais** scans ID |
| 4 | Déclarer Scripted Agent Status si bot service | Agent | — |
| 5 | Ship 1 MVP : script/tool Marketplace **ou** offre freelance LSL in-world | Agent | Ledger V-13 |
| 6 | Mesurer L$ / 14 j ; puis 1ère vente LindeX + process credit test (petit) | Agent + humain payout | Journal anti-scam |
| 7 | Si traction : envisager révision cap V-13 pour Premium | PR | risk-limits |

Hors scope immédiat : régions, clubs, arènes gambling, échanges L$ tiers.

---

## 9. Index des sources

| # | Source | Usage |
|---|--------|-------|
| 1 | https://wiki.secondlife.com/wiki/Linden_Lab_Official:Scripted_Agent_Policy | Bots autorisés / interdits |
| 2 | https://wiki.secondlife.com/wiki/Bot | Synthèse bots + CopyBot |
| 3 | https://lindenlab.com/legal/second-life-terms-and-conditions | T&C traffic / gambling / banks |
| 4 | https://wiki.secondlife.com/wiki/Linden_Lab_Official:Mainland_policies | Camping / misuse bots |
| 5 | https://secondlife.com/corporate/pricing | Frais LindeX, payout, Premium, land |
| 6 | https://api.secondlife.com/datafeeds/lindex.txt | Taux L$ (2026-11-21) |
| 7 | https://community.secondlife.com/knowledgebase/english/tilia-faq-r1533/ | KYC process credit |
| 8 | https://community.secondlife.com/knowledgebase/english/account-balance-r1/ | Wallet USD / Tilia |
| 9 | https://lindenlab.freshdesk.com/support/solutions/articles/31000135224-process-credit-withdrawal-requests | Min/max/délais payout |
| 10 | https://secondlife.com/app/tos/tos.php | Stored value / process credit ToS |
| 11 | https://community.secondlife.com/knowledgebase/english/selling-in-the-marketplace-r88/ | Store Marketplace |
| 12 | https://community.secondlife.com/blogs/entry/3016-the-return-of-last-names-and-changes-to-marketplace-events-premium | Commission Marketplace 10 % |
| 13 | https://wiki.secondlife.com/wiki/Linden_Lab_Official:Required_Tax_Documentation_FAQ | Tax docs / 1099-K |
| 14 | https://community.secondlife.com/blogs/entry/1094-required-tax-documentation | Blog tax |
| 15 | https://harmony-group.gitbook.io/sl-entrepreneurs-guide/earnings-overview-summary-by-activity | Fourchettes revenus (non officiel) |
| 16 | https://harmony-group.gitbook.io/sl-entrepreneurs-guide/content-creation-and-digital-artistry | Tarifs scripting |
| 17 | https://www.reddit.com/r/secondlife/comments/1i80s8w/waitcan_you_actually_make_real_money_from_here/ | Réalité earn 2025 |
| 18 | https://community.secondlife.com/forums/topic/519138-is-it-still-worth-it/ | Merchants full-time |

*URLs consultées 2026-11-21. Re-vérifier frais/taux avant tout spend ou payout.*
