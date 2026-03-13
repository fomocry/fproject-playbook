# 💰 Buy Config

La Buy Config contrôle **comment le bot achète** pour un rugger spécifique. Depuis la config d'un rugger, appuyez sur **💰 Buy Config**.

### Les paramètres

---

### 💵 Buy Amount

Le montant en SOL que le bot dépensera pour chaque achat déclenché par ce rugger.

**Exemple** : Si vous mettez 0.1 SOL, chaque achat automatique coûtera 0.1 SOL (hors gas fees).

> ⚠️ **Minimum recommandé : 0.1 SOL.** Les frais de gas par défaut sont de ~0.012 SOL par transaction (achat + vente = ~0.024 SOL au total). Si vous snipez avec 0.05 SOL, vous dépenserez presque la moitié en frais, ce qui réduit fortement votre rentabilité. Voir la section Gas Fees ci-dessous.

---

### ⏱ Snipe Delay

Le délai en secondes entre le moment où le bot détecte un événement et le moment où il exécute l'achat.

**0 secondes** = le bot achète immédiatement.

**Cas d'usage — Filtrer les mauvais tokens :** Imaginons un rugger qui fait 3 bons tokens sur 10. Les 7 mauvais rug en 2-3 secondes, alors que les 3 bons montent en continu. En mettant un delay de 5 secondes, les mauvais tokens auront déjà rug au moment de l'achat — vous les achetez au plus bas, ce qui limite la perte. Et encore mieux : **combinez Snipe Delay + Min MC**. Avec un delay de 5 secondes et un Min MC à $5,000, le bot attendra 5 secondes puis n'achètera que si le token est au-dessus de $5,000 — ce qui filtre les tokens "fails" qui sont retombés bas.

---

### 🔂 Buy Only Once

Quand activé, le bot ne copiera que le **premier achat** du wallet et ignorera les suivants sur le même token.

Ce paramètre n'apparaît que si **Track Buys** est activé dans le Tracking Mode.

**Cas d'usage** : Un trader que vous suivez DCA (achète en plusieurs fois). Vous voulez entrer une seule fois et pas multiplier les achats sur le même token.

---

### 📉 Min MC / 📈 Max MC

Le market cap minimum et maximum pour qu'un achat soit exécuté.

**Exemple** : Min MC = $5,000, Max MC = $50,000. Le bot n'achètera que si le market cap du token est entre $5,000 et $50,000 au moment de l'achat.

> ⚠️ **Important** : Ces filtres sont vérifiés **après** le Snipe Delay. Si vous mettez un delay de 5 secondes et un Min MC de $5,000, le bot attendra 5 secondes puis vérifiera si le market cap est au-dessus de $5,000 avant d'acheter.

### Combinaison de paramètres

Tous les paramètres se combinent. Exemple complet :

* Buy Amount : 0.1 SOL
* Snipe Delay : 5s
* Min MC : $5,000
* Max MC : $50,000
* Buy Only Once : ON

→ Le bot attend 5 secondes après l'événement détecté, vérifie que le MC est entre $5K et $50K, achète 0.1 SOL, puis ignore les prochains achats de ce wallet sur ce token.

---

### ⚡ Gas Fees (Achat)

Les frais de gas déterminent la vitesse et la priorité de vos transactions. Ils sont identiques pour l'achat et la vente.

| Frais | Montant par défaut | Description |
|---|---|---|
| **Priority Fee** | 0.001 SOL | Frais payés directement à la blockchain Solana |
| **Tip** | 0.001 SOL | Pourboire donné à nos validateurs |
| **Bribe** | 0.01 SOL | Détermine votre ordre de priorité dans notre infrastructure. Plus c'est élevé, plus vous passez en premier |

**Total par défaut : ~0.012 SOL par transaction** (achat ou vente).

> 💡 Vous pouvez baisser les frais (minimum 0.01 SOL total) mais c'est **déconseillé** — vous perdrez l'étiquette PRIORITAIRE dans l'ordre de traitement des transactions, ce qui affectera votre vitesse d'achat et de vente.
