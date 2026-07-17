# 💰 Buy Config

La Buy Config contrôle **comment le bot achète** pour un rugger spécifique. Depuis la config d'un rugger, appuyez sur **💰 Buy Config**.

### Les paramètres

---

### 💵 Buy Amount

Le montant en SOL que le bot dépensera pour chaque achat déclenché par ce rugger.

**Exemple** : Si vous mettez 0.1 SOL, chaque achat automatique coûtera 0.1 SOL (hors gas fees).

> ⚠️ **Minimum recommandé : 0.1 SOL.** Les frais de gas par défaut sont de ~0.022 SOL par transaction (achat + vente = ~0.044 SOL au total). Si vous snipez avec 0.05 SOL, vous dépenserez presque la totalité en frais, ce qui réduit fortement votre rentabilité. Voir la section Gas Fees ci-dessous.

---

### ⏱ Snipe Delay

Le délai en secondes entre le moment où le bot détecte un événement et le moment où il exécute l'achat.

**0 secondes** = le bot achète immédiatement.

**Cas d'usage — Filtrer les mauvais tokens :** Imaginons un rugger qui fait 3 bons tokens sur 10. Les 7 mauvais rug en 2-3 secondes, alors que les 3 bons montent en continu. En mettant un delay de 5 secondes, les mauvais tokens auront déjà rug au moment de l'achat — vous les achetez au plus bas, ce qui limite la perte. Et encore mieux : **combinez Snipe Delay + Min MC**. Avec un delay de 5 secondes et un Min MC à $5,000, le bot attendra 5 secondes puis n'achètera que si le token est au-dessus de $5,000 — ce qui filtre les tokens "fails" qui sont retombés bas.

---

### 🌕 Max Token Age (copytrade uniquement)

L'âge maximum, en **minutes**, qu'un token peut avoir pour que le bot copie un achat.

**Le problème que ça résout :** en copytrading, le wallet que vous suivez peut acheter un token qui existe depuis longtemps — 50 minutes, 3 heures, une journée. Ces entrées tardives ne correspondent souvent pas à votre stratégie : le token a déjà fait son mouvement.

**Comment ça marche :** si vous réglez Max Token Age à **10 min** et que votre rugger achète un token créé il y a 50 minutes, le bot **ignore cet achat**. Il ne copie que les achats sur des tokens plus récents que votre limite.

**Configuration :**
* Valeur en minutes, de 1 à **1440** (24 heures)
* **0 = OFF** (aucun filtre d'âge)

> ⚠️ Ce filtre ne fonctionne qu'en **copytrading** (Track Buys). Il n'a aucun effet en sniping — un token snipé en Block 0 a par définition 0 minute d'âge.

> 💡 **Conseil** : Un Max Token Age court (5-15 min) vous aligne sur les entrées précoces de votre rugger et filtre ses trades "hors stratégie". Si vous copiez un trader qui fait aussi du swing sur des tokens établis, montez la limite ou laissez OFF.

---

### 🔂 Buy Only Once

Quand activé, le bot ne copiera que le **premier achat** du wallet et ignorera les suivants sur le même token.

Ce paramètre n'apparaît que si **Track Buys** est activé dans le Tracking Mode.

---

### 📉 Min MC / 📈 Max MC

Le market cap minimum et maximum pour qu'un achat soit exécuté.

**Exemple** : Min MC = $5,000, Max MC = $50,000. Le bot n'achètera que si le market cap du token est entre $5,000 et $50,000 au moment de l'achat.

> ⚠️ **Important** : Ces filtres sont vérifiés **après** le Snipe Delay.

---

### 📉 Buy The Dip (Acheter la Baisse)

Cette fonctionnalité vous permet d'acheter automatiquement quand un token **baisse depuis son ATH** (All-Time High). Vous pouvez configurer jusqu'à **3 niveaux** d'achat.

Chaque niveau a deux valeurs :
* Le **pourcentage de baisse** depuis l'ATH
* Le **montant** à acheter

**Exemple avec 3 niveaux :**

| Niveau | Baisse depuis ATH | Montant |
|---|---|---|
| Niveau 1 | -20% | 0.5 SOL |
| Niveau 2 | -40% | 1 SOL |
| Niveau 3 | -60% | 2 SOL |

→ Le token atteint $100K de MC puis chute de 20% → le bot achète 0.5 SOL. Si le token continue à chuter et atteint -40% depuis l'ATH → le bot achète 1 SOL supplémentaire. Si ça descend à -60% → le bot achète encore 2 SOL.

**Règles importantes :**
* Chaque niveau ne se déclenche **qu'une seule fois** par token
* Fonctionne aussi bien en **sniping** qu'en **copy trading**
* Les niveaux sont indépendants les uns des autres — si le token ne baisse que de 25%, seul le niveau 1 se déclenche

> 💡 **Conseil** : Le Buy The Dip est particulièrement puissant combiné avec un Trailing SL. Vous achetez les dips, et le Trailing SL protège votre position si le token continue à chuter au-delà de vos niveaux.

---

### Combinaison de paramètres

Tous les paramètres se combinent. Exemple complet :

* Buy Amount : 0.1 SOL
* Snipe Delay : 5s
* Min MC : $5,000
* Max MC : $50,000
* Buy The Dip : -20% → 0.5 SOL, -40% → 1 SOL

→ Le bot attend 5 secondes après l'événement, vérifie que le MC est entre $5K et $50K, achète 0.1 SOL. Ensuite, si le token baisse de 20% depuis son ATH, le bot rachète 0.5 SOL. Si -40%, il rachète 1 SOL.

---

### ⚡ Gas Fees (Achat)

Les frais de gas déterminent la vitesse et la priorité de vos transactions. Ils sont identiques pour l'achat et la vente.

| Frais | Montant par défaut | Description |
|---|---|---|
| **Priority Fee** | 0.001 SOL | Frais payés directement à la blockchain Solana |
| **Tip** | 0.001 SOL | Pourboire donné à nos validateurs |
| **Bribe** | 0.02 SOL | Détermine votre ordre de priorité dans notre infrastructure. Plus c'est élevé, plus vous passez en premier (minimum : 0.01 SOL) |

**Total par défaut : ~0.022 SOL par transaction** (achat ou vente).

> 💡 Vous pouvez baisser les frais (minimum 0.01 SOL total) mais c'est **déconseillé** — vous perdrez l'étiquette PRIORITAIRE dans l'ordre de traitement des transactions, ce qui affectera votre vitesse d'achat et de vente.
