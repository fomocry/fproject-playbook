# 🔔 Notifications

Reste informé en temps réel de tout ce qui se passe sur ton infra : buys exécutés, ventes confirmées, alertes ruggers, etc. Tu choisis maintenant **précisément** quelles notifs tu reçois — sauf les critiques, qui restent toujours ON.

## Notification Preferences

Accessible depuis le menu principal → **Settings → Notifications**, ce panel te permet de toggle individuellement chaque type de notif.

### 📦 Transactions

- **`Buy Confirmed`** — chaque achat exécuté avec succès (montant, token, TX)
- **`Sell Success`** — chaque vente exécutée avec succès (montant, P&L)

### 🛡️ Rugger Protection

- **`Rugger Alert`** — quand le système détecte une activité suspecte (consolidation, dump pattern, fresh wallet flag, etc.)

### 📋 Post-Snipe

- **`Buy Skipped`** — quand le système skip un copytrade (filtre Rugger Protection, Max Loss Counter atteint, etc.)
- **`Processing Buy`** — quand un buy est en cours de traitement, avant confirmation on-chain

### 🔒 Notifications critiques (verrouillées ON)

Ces notifs ne peuvent **pas** être désactivées — elles t'alertent quand quelque chose va mal. C'est pas négociable parce que rater ces alertes peut te coûter cher.

- **`Buy Failed`** — un achat a échoué (slippage, RPC down, insufficient SOL, etc.)
- **`Sell Failed`** — une vente a échoué
- **`Bot Errors`** — erreurs critiques du système

## Format des notifs

Chaque notif inclut :
- Type d'event (avec emoji + couleur)
- Token concerné (CA tronqué + nom si dispo)
- Montant en SOL
- Timestamp
- Bouton d'action rapide (View, Sell, etc.)

## Use case

Tu peux drastiquement réduire le bruit en désactivant les notifs de transactions courantes (`Buy Confirmed`, `Sell Success`, `Processing Buy`) et garder uniquement les events qui demandent ton attention (`Rugger Alerts`, `Buy Skipped`). Particulièrement utile si tu trades sur 20+ ruggers en parallèle — sans ça, ton chat devient illisible.

## 💡 Setups recommandés

**Solo trader actif** → tout ON, tu veux tout voir
- Tu as une visibilité totale, tu peux intervenir manuellement si besoin

**Multi-ruggers en autopilot** → seulement les Critiques + Rugger Alerts + Buy Skipped
- Tu laisses tourner, tu n'interviens que sur les events qui le méritent

**Mode discret** → seulement les Critiques
- Tu veux la paix, tu reviens checker tes positions quand tu veux

Pages liées :
- [📊 Positions](positions.md) — vue détaillée de tes positions
- [🛡️ Vue d'ensemble Rugger Protection](../rugger-protection/overview.md)
- [⚡ Front Run Sell](../rugger-protection/front-run-sell.md)
