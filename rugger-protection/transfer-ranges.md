# 📏 Transfer Ranges

Les **Transfer Ranges** filtrent les transferts en fonction du **montant de SOL** envoyé. Vous pouvez configurer jusqu'à **5 ranges**.

### Comment ça marche

Chaque range définit un intervalle (minimum — maximum, et le max doit être supérieur au min). Quand le bot détecte un transfert, il vérifie si le montant tombe dans l'une de vos ranges. **Seuls les wallets financés dans l'une de ces bandes sont suivis.** Si vous ne mettez aucune range, il n'y a pas de filtre par montant.

**Exemple** : Votre rugger envoie toujours exactement 1.49 SOL.
→ Configurez : **Min = 1.48 SOL** / **Max = 1.50 SOL**

### Plusieurs ranges

Si votre rugger utilise plusieurs montants différents :

| Range | Min | Max |
|---|---|---|
| Range 1 | 1.48 SOL | 1.50 SOL |
| Range 2 | 5.66 SOL | 5.68 SOL |
| Range 3 | 6.44 SOL | 6.46 SOL |
| Range 4 | … | … |
| Range 5 | … | … |

Le bot n'ajoutera que les wallets recevant un montant correspondant à l'une de ces ranges. Vous avez donc jusqu'à **5 montants différents** couverts en même temps.

### Quand les utiliser ?

| Situation | Transfer Ranges |
|---|---|
| Wallet mère avec montants fixes | ✅ Indispensable |
| Dev qui vide son wallet en une seule fois | ❌ Pas nécessaire |
| Vous voulez être plus précis | ✅ Recommandé |

> 💡 **Conseil** : Analysez les transferts passés de votre rugger. Pour un **wallet mère** (montants fixes avec variation de gas), une marge de ± 0.01-0.02 SOL est parfaite. Mais pour une **adresse d'exchange** (hot wallet), il faut une bande **ultra-fine de ± 0.0001 SOL** — un exchange envoie des milliers de transferts, une bande large ramènerait plein d'inconnus et fausserait tout. Ne mettez jamais ± 0.01 sur un exchange.
