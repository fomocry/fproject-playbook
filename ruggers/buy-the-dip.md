# 📉 Buy the Dip

Achète automatiquement quand le prix dump sous un seuil défini, en partant de l'ATH du token. Configure jusqu'à 3 paliers — le système exécute chaque buy une seule fois quand le seuil est touché.

## Comment ça marche

Quand tu achètes un token via copytrade, le bot enregistre l'ATH (All-Time High) en market cap dollars (`MC$`). Si le prix retombe ensuite sous tes paliers configurés, des buys additionnels se déclenchent automatiquement pour DCA dans le dip.

Chaque palier a son propre :
- **Trigger** — pourcentage de baisse depuis l'ATH (ex: -50%)
- **Montant** — SOL à acheter quand le palier se déclenche
- **Status** — se déclenche une seule fois par token, puis disabled

## Configuration

Sur chaque rugger, accède à **Buy Config → Buy the Dip** et ajoute jusqu'à 3 paliers :

```
Level 1: -30% ATH → Buy 0.5 SOL
Level 2: -50% ATH → Buy 1.0 SOL
Level 3: -70% ATH → Buy 2.0 SOL
```

L'ATH est calculé en MC$ (market cap dollars), pas en prix par token. Ça reste cohérent même si le supply change pendant le run.

## Use case

Idéal sur des ruggers connus pour faire des dips violents avant de recover. Tu rentres petit au copy initial, et le système moyennise ta position quand le dip arrive — sans que tu touches à rien.

## ⚠️ À savoir

Si le token continue de dump indéfiniment (rug réel), tu accumules de la perte. **Combine cette feature avec le Max Loss Counter** pour limiter les dégâts automatiquement.

Pages liées :
- [💰 Buy Config](buy-config.md) — config buy de base
- [🛑 Max Loss Counter](max-loss-counter.md) — coupe automatique
- [📈 Sell Config](sell-config.md) — TP/SL sur la position globale
