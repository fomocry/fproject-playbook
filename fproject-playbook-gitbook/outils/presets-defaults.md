# 📋 Presets & Réglages par Défaut

### Presets

Un **Preset** est une configuration sauvegardée que vous pouvez appliquer en un clic à n'importe quel rugger.

**Sauvegarder un Preset :**

1. Configurez un rugger exactement comme vous le souhaitez
2. Depuis sa page de config, appuyez sur **📋 Save Preset**
3. Donnez un nom au Preset (ex : "Dev Sniper Standard", "Copy Trade Safe")

**Appliquer un Preset :**

1. Depuis la page **🎯 Ruggers**, appuyez sur **📋 Presets**
2. Appuyez sur le Preset voulu
3. Il s'applique au rugger sélectionné

**Ce qui est sauvegardé dans un Preset :**

* Tracking Mode
* Buy Config (montant, delay, market cap, buy only once)
* Sell Config (TP/SL, Trailing SL, No Activity)
* Protection (mode, keep address, fresh wallet, transfer ranges)
* Gas Settings

Les Presets sont **indépendants du wallet** — vous pouvez appliquer un Preset créé sur le Wallet A à un rugger du Wallet B.

> 💡 **Conseil** : Créez 2-3 Presets pour vos cas d'usage principaux. Par exemple :
>
> * **"Sniper Agressif"** — New Tokens, 0.5 SOL, Trailing SL -20%, Protection ON
> * **"Copy Safe"** — Track Buys, 0.1 SOL, TP +20% / SL -50%, Protection OFF

***

### Réglages par Défaut

Les réglages par défaut sont les valeurs qui s'appliquent **automatiquement à chaque nouveau rugger** que vous ajoutez.

Depuis le menu principal, appuyez sur **⚙️ Settings** pour configurer :

* **Default Buy Settings** — Montant, delay, market cap
* **Default Sell Settings** — TP/SL, Trailing SL, No Activity
* **Default Protection** — Mode, Keep Address, Fresh Wallet, Transfer Ranges

**Comment ça fonctionne :**

1. Vous configurez vos réglages par défaut une fois
2. Chaque nouveau rugger ajouté hérite automatiquement de ces valeurs
3. Vous pouvez ensuite personnaliser chaque rugger individuellement si nécessaire

> ⚠️ **Important** : Modifier les réglages par défaut ne change **pas** les ruggers existants. Seuls les nouveaux ruggers ajoutés après la modification hériteront des nouvelles valeurs.

### Presets vs Réglages par Défaut

|                | Presets                         | Réglages par Défaut                 |
| -------------- | ------------------------------- | ----------------------------------- |
| **Quand ?**    | Appliqué manuellement           | Appliqué automatiquement à l'ajout  |
| **Sur quoi ?** | Un rugger existant              | Les nouveaux ruggers                |
| **Combien ?**  | Plusieurs Presets possibles     | Un seul jeu de défauts              |
| **Usage**      | Changer rapidement de stratégie | Ne plus reconfigurer à chaque ajout |
