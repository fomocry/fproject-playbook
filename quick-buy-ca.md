# ⚡ Quick Buy by CA

Colle un Contract Address dans le bot → menu de buy instantané avec choix du montant. Plus rapide que naviguer dans les menus, plus safe qu'un buy automatique.

## Comment ça marche

Tu envoies un CA Solana au bot — pas de commande, juste l'adresse copiée-collée. Le système détecte automatiquement que c'est un CA et te répond immédiatement avec un menu de confirmation :

```
🔍 Token Detected!
9ki4MjbQdWYiQRiY7bZjGLvyR3TSb7jd9waNo4icpump

Select amount to buy:
[0.1 SOL] [0.5 SOL] [1 SOL] [2 SOL]
[✏️ Custom]
[❌ Cancel]
```

Tu cliques sur le montant → buy exécuté instantanément avec ta config de slippage et priority fee. Si tu veux un montant non-standard, **Custom** te laisse taper la valeur exacte. Si tu as collé par erreur, **Cancel** ferme le menu sans rien acheter.

## Configuration

Les montants des boutons et les paramètres de buy se règlent dans **Outils → Presets & Réglages par Défaut → Quick Buy** :

```
Quick Buy Buttons:    0.1 / 0.5 / 1 / 2 SOL
Slippage:             15%
Priority Fee:         0.005 SOL
Default Wallet:       Wallet 1
```

Les 4 montants des boutons sont customisables — adapte-les à tes tailles de position habituelles. Si tu joues souvent en 0.3 SOL, mets `0.1 / 0.3 / 0.5 / 1` par exemple.

## Use case

Idéal quand tu chases un call rapide ou que tu veux rentrer manuellement sur un token découvert ailleurs (Telegram, Twitter, Discord, etc.). Pas besoin de naviguer dans les menus de recherche, pas besoin de chercher le token — tu colles, tu choisis le montant, tu rentres.

```
1. Tu vois un call sur Twitter avec un CA
2. Tu copies le CA
3. Tu le colles dans le bot
4. Le bot affiche le menu Quick Buy
5. Tu cliques 0.5 SOL → buy fired
```

Le step de confirmation te protège contre les paste accidentels — tu peux copier des CA pour les consulter ailleurs sans risque de buy par erreur. Toujours possible de cancel.

## 💡 Tip

Combine avec le wallet par défaut configuré sur un wallet "scout" (petite balance dédiée aux entrées rapides). Ça te garantit que tes Quick Buy ne touchent pas tes wallets principaux et que l'exposure reste contrôlée.

Pages liées :
- [📋 Presets & Réglages par Défaut](presets-defaults.md)
- [👜 Créer & Gérer ses Wallets](../get-started/wallets.md)
- [📊 Positions](positions.md)
