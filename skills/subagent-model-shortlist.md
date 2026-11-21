---
name: subagent-model-shortlist
description: Pour un sous-agent non trivial, évaluer une shortlist de modèles (score + coût), puis choisir soi-même — préférer le moins cher quand c’est suffisant. Pas d’attente de pick opérateur sauf décision à sens unique.
---

# Shortlist modèles sous-agents (choix autonome)

## Quand

Avant de lancer un worker / sous-agent pour une tâche non triviale.

Passer immédiatement avec le modèle courant pour : statut d’une ligne, auth, Q&A trivial, tweak simple, ou modèle déjà nommé par l’opérateur.

## Adaptation Project M / Agent 4

L’agent **choisit lui-même** le modèle. **Préférer le moins cher** dès que la qualité attendue est suffisante. Ne pas bloquer sur un pick humain.

Demander à l’opérateur seulement si le choix est une **décision à sens unique** (coût élevé irréversible, impact prod) — cas rare pour le choix de modèle.

## Résultat attendu

1. Top 5 candidats scorés (modèle, effort de raisonnement, score 0–10, bande de coût `low` | `medium` | `high`, raison courte).
2. **Choisir la ligne recommandée** (en pratique : meilleur rapport qualité/coût ; en cas d’égalité, le moins cher).
3. Lancer le sous-agent avec ce modèle.
4. Consinger le choix (et les alternatives écartées) dans le rapport final / décisions autonomes.

## Étapes

1. Estimer si un modèle spécialisé / un effort de raisonnement aide (UX, code, structuration, multimodal, vitesse…).
2. Candidats = modèles exposés par l’outil Agent. S’il n’y en a qu’un : l’utiliser sans shortlist.
3. Scorer 0–10 + une phrase de raison (langue de l’opérateur préférée).
4. Bande de coût (`low` | `medium` | `high`) — estimations approximatives.
5. Garder le top 5. Recommandation = ligne 1, marquée clairement.
6. **Lancer** avec le modèle choisi (pas d’attente). Si l’effort de raisonnement n’est pas configurable au launch, l’indiquer dans le brief.

## Heuristique coût

| Type de pièce | Bande cible |
|---------------|-------------|
| Docs, renommages, recherche mécanique, tests simples | `low` |
| Implémentation module clair, revue de diff standard | `low`–`medium` |
| Design ambigu, sécu, bugs subtils, revue critique | `medium`–`high` |

En cas de doute entre deux modèles « assez bons » : prendre le **moins cher**.

## Après coup

Noter dans le rapport : modèle retenu, effort, pourquoi, alternatives non retenues.
