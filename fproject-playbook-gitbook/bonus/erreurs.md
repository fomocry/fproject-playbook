# ⁉️ Messages d'erreur

Voici les erreurs les plus fréquentes et comment les résoudre.

***

### Transaction failed on-chain

**Signification** : La transaction a été envoyée mais a échoué sur la blockchain.

**Causes possibles** :

* Solde insuffisant sur votre wallet
* Le token a déjà été acheté/vendu entre-temps
* Congestion du réseau Solana

**Solution** : Vérifiez votre solde. Si le solde est suffisant, relancez un achat ou une vente manuellement.

***

### Blockhash expired

**Signification** : La transaction a pris trop de temps à être confirmée et a expiré.

**Causes possibles** :

* Congestion du réseau Solana
* Gas fees trop bas

**Solution** : Relancez la transaction. Si le problème persiste, essayez d'augmenter le "Priority Fees" dans les gas fees pour obtenir une meilleure priorité.

***

### Insufficient balance

**Signification** : Votre wallet n'a pas assez de SOL pour exécuter la transaction.

**Solution** : Envoyez du SOL sur votre wallet. N'oubliez pas que chaque transaction nécessite environ 0.022 SOL de gas fees en plus du montant d'achat.

***

### Auto-Sell Skipped

**Signification** : Les conditions de vente automatique ont été remplies mais la vente n'a pas été exécutée.

**Solution** : Vérifiez vos paramètres de vente (Sell Config). Vous pouvez vendre manuellement depuis la notification ou la page Positions.

***

> 💡 **Conseil général** : La plupart des erreurs de transaction sont liées au solde ou à la congestion. Vérifiez d'abord votre solde, puis essayez d'ajuster les gas fees si le problème persiste.
