# 🐳 Auto-Sell on Big Buy

Vente automatique progressive déclenchée par un gros achat détecté on-chain sur ton token. Tu définis 3 paliers — le système exécute.

## Comment ça marche

Le système monitore tous les buys sur les tokens où tu as une position ouverte. Quand un wallet achète gros (au-dessus d'un seuil que tu définis en SOL), le palier correspondant déclenche une vente automatique d'une partie de ta position.

Chaque palier se déclenche **une seule fois** par token. Une fois L1 fired, il ne se redéclenche pas — c'est L2 qui prend le relais sur le prochain big buy plus gros.

## Configuration

Par rugger, dans **Sell Config → Auto-Sell on Big Buy**, configure jusqu'à 3 paliers :

```
Level 1: 2.5–3 SOL buy → Sell 50%
Level 2: 4–10 SOL buy  → Sell 100%
Level 3: 10–25 SOL buy → Sell 100%
```

**Chaque palier nécessite** :
- **Range SOL** — montant min et max du buy détecté pour déclencher ce palier
- **% à vendre** — combien de ta position est liquidée

Les ranges ne doivent pas se chevaucher — chaque buy détecté ne peut activer qu'un seul palier.

## Use case

Sur PumpFun, les gros buys signalent souvent l'une de ces deux choses :
- **Un whale qui rentre** (bullish — tu peux scale out un peu pour sécuriser)
- **Un insider qui pump avant son exit** (bearish — tu sors complètement)

Avec 3 paliers configurés, tu joues les deux scénarios :
- Petit buy (L1) → petit scale out, tu gardes la position
- Gros buy (L2 / L3) → exit total avant que le whale dump

## 💡 Setup recommandé

`L1 large (50% sur 2-3 SOL)` + `L2 strict (100% sur 4+ SOL)` + `L3 catch-all (100% sur 10+ SOL)`

Tu sécurises ton initial sur les buys moyens et tu sors complètement sur les très gros. C'est l'un des edge les plus rentables sur PumpFun pour scaler les profits sans timing manuel.

Pages liées :
- [📈 Sell Config](sell-config.md) — TP/SL classiques
- [⚡ Front Run Sell](../rugger-protection/front-run-sell.md) — sortie sur dump pattern dev
- [📊 Positions](../outils/positions.md) — vue de tes positions ouvertes
