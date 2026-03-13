# 📏 Transfer Ranges

Les **Transfer Ranges** permettent de filtrer les transferts détectés par la Rugger Protection en fonction du **montant de SOL** envoyé.

Vous pouvez configurer jusqu'à **3 ranges** différentes.

### Comment ça marche

Chaque range définit un intervalle de montant (minimum — maximum). Quand le bot détecte un transfert, il vérifie si le montant envoyé tombe dans l'une de vos ranges.

**Exemple** : Votre rugger envoie toujours exactement 1.49 SOL à ses nouveaux wallets.

→ Configurez une range : **Min = 1.48 SOL** / **Max = 1.50 SOL**

Le bot ne prendra en compte que les transferts entre 1.48 et 1.50 SOL. Tous les autres transferts (paiements d'exchange, envois à des amis, etc.) seront ignorés.

### Plusieurs ranges

Si votre rugger utilise plusieurs montants différents, vous pouvez mettre plusieurs ranges.

**Exemple** : Un wallet mère qui fund ses wallets enfants avec 3 montants différents :
* Parfois 1.49 SOL
* Parfois 5.67 SOL
* Parfois 6.45 SOL

→ Configurez 3 ranges :

| Range | Min | Max |
|---|---|---|
| Range 1 | 1.48 SOL | 1.50 SOL |
| Range 2 | 5.66 SOL | 5.68 SOL |
| Range 3 | 6.44 SOL | 6.46 SOL |

Le bot ajoutera au monitoring uniquement les wallets qui reçoivent un montant correspondant à l'une de ces 3 ranges.

### Quand utiliser les Transfer Ranges ?

Les Transfer Ranges sont particulièrement utiles avec le mode **Exchange Pattern**, mais fonctionnent aussi avec le mode **Last Transfer** pour filtrer les transferts pertinents.

| Situation | Transfer Ranges |
|---|---|
| Wallet mère avec montants fixes | ✅ Indispensable |
| Dev qui vide son wallet en une seule fois | ❌ Pas nécessaire (Last Transfer suffit) |
| Vous voulez être plus précis dans le filtrage | ✅ Recommandé |

> 💡 **Conseil** : Analysez les transferts passés de votre rugger pour identifier les montants récurrents. Mettez une petite marge (± 0.01-0.02 SOL) autour du montant exact pour absorber les variations de gas fees.
