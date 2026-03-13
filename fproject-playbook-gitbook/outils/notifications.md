# 🔔 Notifications

Le bot envoie des notifications pour chaque événement important.

### ⏳ Achat en cours

Envoyée quand le bot détecte un événement et lance un achat. Affiche le token, le wallet, le rugger qui a déclenché l'achat, le montant et le market cap. Cette notification se met à jour automatiquement une fois l'achat confirmé ou échoué.

### ✅ Achat confirmé

Envoyée quand l'achat est confirmé on-chain. Affiche le token, le montant dépensé, le market cap à l'entrée, et le nom du rugger qui a déclenché l'achat.

Le **type de déclenchement** est visible :
* 🆕 New Token — Création de token détectée
* 📦 Copy Trade — Achat copié
* 🔄 Dev Sell — Achat déclenché par une vente du dev

**Boutons disponibles** : Refresh (met à jour le P&L), Buy More, Sell (25%/50%/75%/100%), Axiom (chart), TX (transaction on-chain).

### ⏳ Vente en cours

Envoyée quand une vente est déclenchée. Affiche la **raison** de la vente :
* 🎯 Take Profit
* 🛑 Stop Loss
* 📊 Trailing SL
* ⏳ No Activity
* ✋ Manual (vous avez appuyé sur Sell)

### 🚀 Vente confirmée (Profit)

Envoyée quand une vente est confirmée avec un profit. Le **P&L** est affiché en grand : montant en SOL et pourcentage.

### 📉 Vente confirmée (Perte)

Même format que la vente en profit, mais avec le P&L négatif.

### ❌ Achat / Vente échoué

Envoyée quand une transaction échoue. Affiche le message d'erreur et un conseil pour résoudre le problème.

### 🛡️ Rugger Protection

Envoyée quand le bot détecte un transfert correspondant à vos critères de protection. Affiche un schéma visuel du transfert (adresse source → montant → adresse destination) et l'action prise par le bot.

**Boutons disponibles** : Old Address (Solscan), New Address (Solscan), View Rugger Config, Pause Monitoring.

---

### 📊 PnL Cards

Quand l'**intégralité** d'une position sur un token est vendue (plus aucun token détenu), le bot génère automatiquement une **PnL Card** — un récapitulatif visuel de votre trade.

Les PnL Cards sont calculées **frais inclus** :
* Le montant d'achat inclut les gas fees payés pour l'achat
* Le montant de vente déduit les gas fees payés pour la vente
* Le P&L affiché est donc votre **gain ou perte réel**, net de tous les frais

> ⚠️ **Important** : La PnL Card ne se génère que quand **100% de la position** est vendue. Si vous avez 3 niveaux de TP et que seuls 2 se sont déclenchés, la PnL Card ne se génèrera qu'une fois le dernier TP atteint ou la position vendue manuellement.

> ⚠️ **Les ventes manuelles** (via les boutons Sell dans les notifications ou les Positions) **ne génèrent pas de PnL Card**.
