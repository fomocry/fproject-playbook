# 📏 Transfer Ranges

Les **Transfer Ranges** filtrent les transferts en fonction du **montant de SOL** envoyé. Vous pouvez configurer jusqu'à **3 ranges**.

### Comment ça marche

Chaque range définit un intervalle (minimum — maximum). Quand le bot détecte un transfert, il vérifie si le montant tombe dans l'une de vos ranges.

**Exemple** : Votre rugger envoie toujours exactement 1.49 SOL.
→ Configurez : **Min = 1.48 SOL** / **Max = 1.50 SOL**

### Plusieurs ranges

Si votre rugger utilise plusieurs montants différents :

| Range | Min | Max |
|---|---|---|
| Range 1 | 1.48 SOL | 1.50 SOL |
| Range 2 | 5.66 SOL | 5.68 SOL |
| Range 3 | 6.44 SOL | 6.46 SOL |

Le bot n'ajoutera que les wallets recevant un montant correspondant à l'une de ces ranges.

### Quand les utiliser ?

| Situation | Transfer Ranges |
|---|---|
| Wallet mère avec montants fixes | ✅ Indispensable |
| Dev qui vide son wallet en une seule fois | ❌ Pas nécessaire |
| Vous voulez être plus précis | ✅ Recommandé |

> 💡 **Conseil** : Analysez les transferts passés de votre rugger. Mettez une marge de ± 0.01-0.02 SOL pour absorber les variations de gas fees.
