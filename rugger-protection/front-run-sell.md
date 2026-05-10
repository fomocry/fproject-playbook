# ⚡ Front Run Sell

Détecte la consolidation de la supply vers un wallet unique et te sort **dans le même bloc que le transfer** — avant même que le dev ait le temps de soumettre sa transaction de dump.

## Le pattern qu'on chasse

Avant de dump leur supply sur PumpFun, les ruggers font presque toujours le même mouvement préparatoire : ils ont distribué la supply à plusieurs wallets liés (mère, funder, linked wallets) pendant le run, et au moment du dump ils consolident tout vers un seul wallet pour exécuter le sell en une seule transaction.

Ce regroupement est un **signal béton** d'un dump imminent. La fenêtre entre la consolidation et le dump est de quelques secondes — souvent moins.

## Le trigger exact

Le système monitore en permanence tous les transfers de tokens entre les wallets liés au dev. Dès qu'un transfer arrive vers un wallet unique et que le **pourcentage de supply consolidée atteint ou dépasse ton threshold configuré**, l'ordre de vente est déclenché immédiatement.

```
1. Dev distribue la supply à N wallets pendant le run
2. Au moment du dump, transfers vers wallet X (consolidation)
3. Le système détecte: "60% de la supply est sur wallet X"
4. Si 60% >= ton threshold (ex: 50%) → SELL TRIGGERED
```

On n'attend **pas** que le dev exécute son sell. On vend au même bloc que le transfer de consolidation.

## Pourquoi c'est un edge

Sur Solana, les blocs durent ~400ms. Sans Front Run Sell, le scenario classique est :

```
Block N    : Dev consolide ses tokens
Block N+1  : Dev exécute SELL → prix dump
Block N+2  : Tu détectes le dump et tu vends → tu sors en bas
```

Avec Front Run Sell :

```
Block N    : Dev consolide ses tokens + TON SELL est dans le même bloc
Block N+1  : Dev exécute SELL → prix dump (mais toi t'es déjà sorti)
```

Tu sors avant que la pression vendeuse arrive. Au pire dans le même bloc que le dump, au mieux un bloc avant. Dans tous les cas, tu n'es plus exposé quand le prix s'effondre.

## Configuration

Sur chaque rugger, dans **Rugger Protection → Front Run Sell** :

```
Status:                    ON / OFF
Consolidation Threshold:   50% (default)
Sell Action:               100% of position
```

**Le threshold de consolidation** = pourcentage de la supply totale du dev qui doit se retrouver sur un seul wallet pour déclencher la vente.

- **Threshold bas** (ex: 30%) → système plus réactif, mais plus de faux positifs (un dev peut consolider 30% sans intention de dump immédiat)
- **Threshold haut** (ex: 70%) → conservateur, mais risque de rater le dump si le dev consolide vite et envoie son sell dans la foulée

50% est le bon défaut — agressif sans être trop trigger-happy.

## Use case

C'est ton edge ultime sur les ruggers qui font le shuffle classique :

```
Distribution → Consolidation → Dump
```

La fenêtre entre la consolidation et le dump est de quelques secondes — humainement impossible à catch. Le système le fait pour toi, dans le même bloc.

## ⚠️ Beta — testée légèrement

Cette feature est sortie après des tests légers. Quelques dysfonctionnements sont possibles les premiers jours :
- Sortie qui ne se déclenche pas alors qu'elle aurait dû
- Sortie qui se déclenche à tort (faux positif sur consolidation non-suivie d'un dump)
- Latence d'exécution plus longue que prévu

**Si tu en croises un**, ouvre un ticket dans `#support` sur le Discord avec :
- Le CA du token concerné
- L'heure approximative du déclenchement (ou non-déclenchement)
- Un screenshot de ta position si possible

On corrige au plus vite.

Pages liées :
- [🛡️ Vue d'ensemble Rugger Protection](overview.md)
- [🔀 Modes de Protection](modes.md)
- [📏 Transfer Ranges](transfer-ranges.md)
- [🐳 Auto-Sell on Big Buy](../ruggers/auto-sell-big-buy.md) — autre exit signal
