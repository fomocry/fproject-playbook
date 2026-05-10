# 💸 Sell Initials

Récupère ta mise initiale en un clic. Le reste devient ton moonbag free-ride.

## Comment ça marche

Sur chaque position ouverte, un bouton **`SELL INITIALS`** est désormais disponible. Quand tu cliques :

1. Le système calcule combien de SOL tu as investi initialement (entry cost)
2. Vend exactement la quantité de tokens nécessaire pour récupérer ce montant en SOL
3. Le reste de la position reste ouverte — c'est ton free-ride

Plus de calcul mental sous pression, plus de risque d'erreur de calcul à 3h du matin.

## Exemple

```
Avant clic:  Position 4.5 SOL  (entry: 1.5 SOL)  ← +200%
Action:      SELL INITIALS
Après clic:  Position 3.0 SOL  + 1.5 SOL extracted (free-ride)
```

Tu as récupéré exactement ta mise. Les 3 SOL restants sont en pure plus-value — peu importe ce qui arrive ensuite, tu es à l'équilibre.

## Use case

Scenario classique : tu rentres à 1.5 SOL sur un token, le prix x3, ta position vaut 4.5 SOL. Tu veux sécuriser tes initiaux mais garder de l'expo au cas où ça continue de monter. Au lieu de calculer "combien de % je dois vendre pour récupérer 1.5 SOL", tu cliques `SELL INITIALS` et c'est fait.

## 💡 Setup zero-risk classique

`SELL INITIALS` + `Trailing SL sur le moonbag restant`

Tu sécurises ton initial, tu trail le reste pour maximiser le upside. Si ça dump, le trailing SL te sort avec un peu de profit. Si ça moon, tu profites de la suite. Setup imparable.

Pages liées :
- [📊 Positions](positions.md) — gestion globale de tes positions
- [📈 Sell Config](../ruggers/sell-config.md) — TP/SL et Trailing SL
