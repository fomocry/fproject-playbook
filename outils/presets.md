# 📋 Presets

Un **Preset** est une configuration complète sauvegardée que vous pouvez appliquer en un clic sur n'importe quel rugger.

### Pourquoi utiliser des Presets ?

Quand vous ajoutez un nouveau rugger, il est "nu" — sans aucun réglage. Au lieu de tout reconfigurer manuellement à chaque fois, vous pouvez sauvegarder vos configurations préférées en Presets et les appliquer en un clic.

### Sauvegarder un Preset

1. Configurez un rugger exactement comme vous le souhaitez
2. Depuis sa page de config, appuyez sur **📋 Save Preset**
3. Donnez un nom au Preset (ex : "Dev Sniper Standard", "Copy Trade Safe")

### Appliquer un Preset

1. Depuis la page **🎯 Ruggers**, appuyez sur **📋 Presets**
2. Appuyez sur le Preset voulu
3. Il s'applique au rugger sélectionné

Vous pouvez aussi appliquer un Preset directement à l'ajout d'un nouveau rugger en activant **📋 Apply Preset After Adding**.

### Ce qui est sauvegardé dans un Preset

Un Preset stocke **tous** les paramètres du rugger :
* Tracking Mode
* Buy Config (montant, delay, market cap, buy only once, Buy The Dip)
* Sell Config (TP/SL, Trailing SL, No Activity, Copier le % de Vente)
* Protection (mode, keep address, fresh wallet, transfer ranges)
* Protection Auto-Achat (seuil de pertes consécutives)
* Héritage des Paramètres
* Gas Settings

Les Presets sont **indépendants du wallet** — vous pouvez appliquer un Preset créé sur le Wallet A à un rugger du Wallet B.

### Exemples de Presets recommandés

> 💡 Créez 2-3 Presets pour couvrir vos cas d'usage principaux :

**"Sniper Agressif"**
* 🆕 New Token Creations
* Buy Amount : 0.1 SOL
* Trailing SL : -20%
* No Activity : 20s
* Protection ON, Last Transfer
* Protection Auto-Achat : 5 pertes

**"Copy Trade Safe"**
* 📦 Track Buys + 📤 Track Sells
* Buy Amount : 0.1 SOL
* TP : +10% → 50%, +30% → 100%
* SL : -50%
* Copier le % de Vente : ON
* Protection OFF

**"DCA Dip Buyer"**
* 🆕 New Token Creations
* Buy Amount : 0.05 SOL
* Buy The Dip : -20% → 0.1 SOL, -40% → 0.2 SOL
* Trailing SL : -25%
* Protection ON
