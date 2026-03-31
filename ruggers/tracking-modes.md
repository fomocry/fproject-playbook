# 🔔 Modes de Tracking

Le mode de tracking détermine **ce que le bot surveille** sur l'adresse de votre rugger. C'est le choix le plus fondamental que vous ferez pour chaque rugger.

Depuis la config d'un rugger, appuyez sur **🔔 Tracking Mode**.

### 🆕 New Token Creations

Le bot surveille si le wallet **crée ou lance un nouveau token**. Dès qu'une création est détectée, le bot achète automatiquement.

**Cas d'usage** : Vous avez repéré un développeur qui crée régulièrement des tokens rentables. Vous voulez être parmi les premiers à acheter à chaque nouveau lancement.

---

### 📦 Track Buys (Copy Trade)

Le bot surveille les **achats** effectués par le wallet. Quand le wallet achète un token, le bot copie l'achat.

**Cas d'usage** : Vous avez identifié un trader rentable et vous voulez reproduire ses achats en temps réel.

> 💡 Quand Track Buys est activé, l'option **Buy Only Once** devient disponible dans Buy Config. Si activée, le bot ne copiera que le premier achat du wallet.

---

### 📤 Track Sells

Le bot surveille les **ventes** effectuées par le wallet. Quand le wallet vend un token que vous détenez aussi, le bot vend automatiquement.

**Cas d'usage** : Vous copy tradez un wallet et voulez aussi copier ses sorties de position.

> 💡 En combinant Track Sells avec le toggle **Copier le % de Vente** dans Sell Config, le bot copiera exactement le pourcentage vendu par le wallet suivi (au lieu de vendre 100%).

---

### 🔄 Buy on Dev Sell

Le bot surveille les **ventes** du développeur et **achète** quand le dev commence à vendre ses tokens.

**Cas d'usage** : Certains développeurs vendent une partie de leurs tokens pour prendre des profits, ce qui peut signaler un certain niveau de market cap.

---

### Comment choisir ?

| Objectif | Modes recommandés |
|---|---|
| Sniper les tokens d'un dev | 🆕 New Token Creations |
| Copy trader un wallet | 📦 Track Buys (+ 📤 Track Sells avec Copier le % de Vente) |
| Stratégie avancée sur un dev | 🆕 New Token Creations + 🔄 Buy on Dev Sell |
