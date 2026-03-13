# ⚙️ Config par Rugger

La page de configuration d'un rugger est le **centre névralgique** du bot. C'est ici que vous contrôlez tout ce qui concerne une adresse spécifique.

### Accéder à la config

Depuis **🎯 Ruggers**, appuyez sur n'importe quel rugger dans la liste pour ouvrir sa config.

### Ce que vous voyez

En haut de la page, un **résumé compact** affiche les paramètres clés :
* **Buy** — Le montant d'achat configuré
* **Mode** — Le mode de tracking actif
* **TP** — Le premier niveau de Take Profit
* **SL** — Le premier niveau de Stop Loss

### Les actions disponibles

| Bouton | Description |
|---|---|
| **🟢 Auto-Buy: ON/OFF** | Active ou désactive l'achat automatique pour ce rugger |
| **🟢 Auto-Sell: ON/OFF** | Active ou désactive la vente automatique pour ce rugger |
| **🔔 Tracking Mode** | Choisir ce que le bot surveille (création de tokens, achats, ventes...) |
| **💰 Buy Config** | Paramètres d'achat (montant, delay, market cap) |
| **📈 Sell Config** | Paramètres de vente (TP/SL, Trailing SL, No Activity) |
| **🛡️ Protection** | Rugger Protection (Fresh Wallet, Transfer Ranges, modes) |
| **⚡ Gas** | Frais de priorité pour les transactions |
| **📋 Save Preset** | Sauvegarder cette configuration comme Preset réutilisable |
| **🔄 Reset** | Remettre tous les réglages à zéro |
| **✏️ Rename** | Donner un nom personnalisé au rugger |
| **🗑 Delete** | Supprimer ce rugger du monitoring |

### Auto-Buy et Auto-Sell

Ces deux toggles sont **indépendants par rugger**. Vous pouvez avoir un rugger avec Auto-Buy activé et Auto-Sell désactivé — dans ce cas, le bot achètera automatiquement mais ne vendra pas (vous devrez vendre manuellement depuis les notifications ou les positions).

> 💡 **Conseil** : Désactivez Auto-Sell si vous préférez gérer vos ventes manuellement ou si vous voulez observer le comportement d'un rugger avant de lui faire confiance.
