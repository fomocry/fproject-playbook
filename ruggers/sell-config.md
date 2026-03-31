# 📈 Sell Config (TP/SL & Trailing)

La Sell Config contrôle **comment le bot vend** pour un rugger spécifique.

### 🎯 TP/SL Levels (Multi TP/SL)

Vous pouvez définir jusqu'à **5 niveaux** de Take Profit et Stop Loss.

Chaque niveau a deux valeurs :
* Le **seuil** de déclenchement (ex : +10%)
* Le **pourcentage de position** à vendre (ex : 50%)

**Exemple avec 2 niveaux TP :**

| Niveau | Seuil | Vente |
|---|---|---|
| TP 1 | +10% | Vendre 50% |
| TP 2 | +30% | Vendre 100% |

→ Quand le token fait +10%, le bot vend la moitié. Quand il fait +30%, le bot vend le reste.

> 💡 **Conseil** : Vendez une grande partie au premier TP pour sécuriser vos gains, puis laissez courir le reste.

---

### 📊 Trailing Stop Loss (Multi Trailing SL)

Le Trailing SL suit le prix à la hausse et vend quand il y a un **drawdown** depuis le point le plus haut. Vous pouvez définir jusqu'à **5 niveaux**, chacun lié à un seuil de market cap.

**Exemple avec 2 niveaux :**

| Condition | Trailing SL |
|---|---|
| Par défaut | -20% depuis l'ATH |
| Au-dessus de 100K MC | -30% depuis l'ATH |

**Concrètement :**
1. Vous achetez un token à $2K MC
2. Le token monte à $50K — pas de drawdown de -20% → pas de vente
3. Le token dip à $42K (-16% depuis ATH) → pas de vente
4. Le token remonte à $80K puis passe $100K → TSL passe à -30%
5. Le token chute à $65K (-35% depuis ATH) → le bot vend

> ⚠️ **Important** : Quand le Trailing SL est activé, les niveaux TP classiques sont **ignorés**. Seul le SL reste actif comme filet de sécurité.

---

### ⏳ No Activity

Le bot vend si **aucune transaction** n'a lieu sur le token pendant X secondes.

**Cas d'usage** : Un token PumpFun sans activité pendant 20-30 secondes est souvent un token abandonné.

---

### 📋 Copier le % de Vente

Ce toggle est disponible quand **Track Sells** est activé dans le Tracking Mode.

* **Copier le % OFF (par défaut)** — Quand le wallet suivi vend, le bot vend 100% de votre position
* **Copier le % ON** — Le bot copie **exactement le pourcentage** vendu par le wallet suivi

**Exemple :** Le wallet que vous suivez détient 1M de tokens et vend 100K (soit 10%). Avec Copier le % activé, le bot vendra 10% de VOTRE position — pas la totalité.

**Cas d'usage** : Vous copy tradez un wallet qui vend progressivement par paliers. Sans ce toggle, le bot vendrait tout à la première vente du wallet. Avec ce toggle, vous suivez exactement sa stratégie de sortie.

> 💡 **Conseil** : Activez Copier le % si vous faites du copy trading sérieux et que le wallet que vous suivez a une stratégie de vente progressive.

---

### Quelle stratégie choisir ?

| Profil | Configuration recommandée |
|---|---|
| **Prudent** | TP à +10% (100%), SL à -30% (100%) |
| **Équilibré** | TP1 à +15% (50%), TP2 à +50% (100%), SL à -40% |
| **Agressif** | Trailing SL à -25%, No Activity 30s |
| **Pro** | Multi TP + Trailing SL multi-niveaux selon le MC |
| **Copy Trader** | Copier le % de Vente ON + Track Sells |
