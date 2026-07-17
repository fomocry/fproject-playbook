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
| **🔔 Tracking Mode** | Choisir ce que le bot surveille |
| **💰 Buy Config** | Paramètres d'achat (+ Buy The Dip) |
| **📈 Sell Config** | Paramètres de vente (+ Copier le % de Vente) |
| **🛡️ Protection** | Rugger Protection |
| **⚡ Gas** | Frais de priorité |
| **🛑 Protection Auto-Achat** | Couper l'auto-buy après X pertes consécutives |
| **🔗 Héritage des Paramètres** | Contrôler si les adresses enfants héritent du parent |
| **📋 Save Preset** | Sauvegarder cette config comme Preset |
| **🔄 Reset** | Remettre tous les réglages à zéro |
| **✏️ Rename** | Donner un nom personnalisé |
| **🗑 Delete** | Supprimer ce rugger |

### Auto-Buy et Auto-Sell

Ces deux toggles sont **indépendants par rugger**. Vous pouvez avoir un rugger avec Auto-Buy activé et Auto-Sell désactivé — dans ce cas, le bot achètera automatiquement mais ne vendra pas.

> 💡 **Conseil** : Désactivez Auto-Sell si vous préférez gérer vos ventes manuellement ou si vous voulez observer le comportement d'un rugger avant de lui faire confiance.

---

### 🛑 Protection Auto-Achat

Cette fonctionnalité protège votre wallet contre les pertes en série pendant votre absence (la nuit par exemple).

**Comment ça marche :** Le bot compte les pertes consécutives sur ce rugger. Quand le nombre de pertes consécutives atteint le seuil que vous avez défini, le bot **désactive automatiquement l'auto-achat** pour ce rugger uniquement. Vos autres ruggers restent actifs.

**Configuration :**
* Seuil par défaut : **10 pertes consécutives**
* Configurable de **2 à 20** pertes
* Fonctionne **par rugger** — si un rugger atteint le seuil, seul celui-ci est désactivé

**Exemple :** Vous dormez. Votre rugger "DevSniper" enchaîne 10 trades perdants d'affilée. Le bot désactive automatiquement l'auto-buy sur "DevSniper". Le lendemain matin, vous voyez que l'auto-buy a été coupé, vous vérifiez ce qui s'est passé, et vous décidez de le réactiver ou pas.

> 💡 **Conseil** : Mettez un seuil bas (3-5) si vous snipez un nouveau rugger que vous ne connaissez pas encore. Montez à 10-15 pour un rugger de confiance qui peut avoir des séries de mauvais tokens de temps en temps.

---

### 🔗 Héritage des Paramètres

Ce toggle contrôle ce qui se passe quand la **Rugger Protection** détecte un transfert et ajoute une nouvelle adresse (adresse enfant) au monitoring.

* **Héritage ON (par défaut)** — L'adresse enfant hérite des paramètres du parent (le rugger qui a fait le transfert)
* **Héritage OFF** — L'adresse enfant reçoit **vos propres paramètres** personnalisés au lieu d'hériter du parent

**Pourquoi désactiver l'héritage ?** Si votre rugger parent a **Keep Address ON** dans la Rugger Protection, chaque transfert ajoute une nouvelle adresse SANS supprimer l'ancienne. Si l'héritage est activé, chaque adresse enfant aura aussi Keep Address ON, ce qui crée une réaction en chaîne qui peut remplir vos 30 slots en quelques minutes.

En désactivant l'héritage, les adresses enfants reçoivent des paramètres "propres" — vous gardez le contrôle.

**⚙️ Child Address Defaults — vos paramètres pour les enfants**

Quand l'héritage est OFF, les adresses enfants reçoivent les valeurs définies dans **Child Address Defaults** (accessible depuis le menu Protection). Vous y contrôlez :

* **Keep Address** et **Fresh Wallet** — les règles de Protection des enfants
* **Protection ON/OFF** et son **Mode**
* **Auto-Buy** et **Auto-Sell**
* **🧹 Remove if no launch** — la durée de probation propre aux adresses enfants
* **Transfer Ranges**

Comme le Remove if no launch se règle aussi ici, une adresse parent et ses enfants peuvent avoir des durées de probation **différentes** — par exemple 24h sur le parent que vous connaissez, 2h sur les enfants à l'essai.

> 💡 **Tip anti-cascade** : mettez Keep Address OFF et Protection OFF dans les Child Address Defaults — les adresses enfants sont snipées une fois, puis retirées. Combiné avec un Remove if no launch court, votre liste reste toujours propre.


> ⚠️ **Important** : Si vous utilisez Keep Address ON, pensez à désactiver l'héritage pour éviter de remplir tous vos slots automatiquement.
