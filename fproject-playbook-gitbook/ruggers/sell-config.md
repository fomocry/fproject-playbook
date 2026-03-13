# 📈 Sell Config (TP/SL & Trailing)

La Sell Config contrôle **comment le bot vend** pour un rugger spécifique. Depuis la config d'un rugger, appuyez sur **📈 Sell Config**.

### Les paramètres

---

### 🎯 TP/SL Levels (Multi TP/SL)

Vous pouvez définir jusqu'à **5 niveaux** de Take Profit et Stop Loss.

**Take Profit (TP)** = le bot vend quand le prix monte d'un certain pourcentage.
**Stop Loss (SL)** = le bot vend quand le prix baisse d'un certain pourcentage.

Chaque niveau a deux valeurs :
* Le **seuil** de déclenchement (ex : +10%)
* Le **pourcentage de position** à vendre (ex : 50%)

**Exemple avec 2 niveaux TP :**

| Niveau | Seuil | Vente |
|---|---|---|
| TP 1 | +10% | Vendre 50% |
| TP 2 | +30% | Vendre 100% |

→ Quand le token fait +10%, le bot vend la moitié. Quand il fait +30%, le bot vend le reste.

**Exemple avec TP + SL :**

| Niveau | Seuil | Vente |
|---|---|---|
| TP 1 | +15% | Vendre 85% |
| SL 1 | -50% | Vendre 100% |

→ Si le token monte de 15%, le bot vend 85%. Si le token descend de 50%, le bot vend tout.

> 💡 **Conseil** : Vendez une grande partie au premier TP pour sécuriser vos gains, puis laissez courir le reste avec un deuxième TP plus élevé.

---

### 📊 Trailing Stop Loss (Multi Trailing SL)

Le Trailing SL suit le prix à la hausse et vend quand il y a un **drawdown** (baisse depuis le point le plus haut).

Vous pouvez définir jusqu'à **5 niveaux** de Trailing SL, chacun lié à un seuil de market cap.

**Exemple avec 2 niveaux :**

| Condition | Trailing SL |
|---|---|
| Par défaut | -20% depuis l'ATH |
| Au-dessus de 100K MC | -30% depuis l'ATH |

→ Au début, si le token baisse de 20% depuis son point le plus haut, le bot vend. Mais si le token atteint 100K de market cap, le trailing s'élargit à -30% pour laisser plus de marge au token.

**Comment ça marche concrètement :**

1. Vous achetez un token à $2K de market cap
2. Le token monte à $50K — le bot ne vend pas (pas de drawdown de -20%)
3. Le token dip à $42K (-16% depuis l'ATH de $50K) — le bot ne vend toujours pas
4. Le token remonte à $80K — nouveau ATH
5. Le token passe $100K — le Trailing SL passe à -30%
6. Le token dip à $75K (-25% depuis l'ATH de $100K) — le bot ne vend pas (le seuil est maintenant -30%)
7. Le token chute à $65K (-35% depuis l'ATH) — le bot vend

> ⚠️ **Important** : Quand le Trailing SL est activé (au moins 1 niveau configuré), les niveaux TP classiques sont **ignorés**. Le Trailing SL prend le contrôle total de la vente. Seul le SL (Stop Loss) reste actif comme filet de sécurité.

---

### ⏳ No Activity

Le bot vend automatiquement si **aucune transaction** (achat ou vente) n'a lieu sur le token pendant un certain nombre de secondes.

**Exemple** : No Activity = 20 secondes. Si personne n'achète ni ne vend le token pendant 20 secondes, le bot considère que le token est "mort" et vend votre position.

**Cas d'usage** : Très utile pour le sniping de tokens PumpFun qui peuvent mourir très rapidement. Un token sans activité pendant 20-30 secondes est souvent un token abandonné.

### Quelle stratégie choisir ?

| Profil | Configuration recommandée |
|---|---|
| **Prudent** | TP à +10% (100%), SL à -30% (100%) |
| **Équilibré** | TP1 à +15% (50%), TP2 à +50% (100%), SL à -40% |
| **Agressif** | Trailing SL à -25%, No Activity 30s |
| **Pro** | Multi TP + Trailing SL multi-niveaux selon le MC |
