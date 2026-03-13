# 🆕 Fresh Wallet

Le paramètre **Fresh Wallet** est un filtre de sécurité dans la Rugger Protection. Quand il est activé, le bot n'ajoutera au monitoring que les wallets **qui n'ont jamais eu d'activité** auparavant.

### Comment ça marche

Quand le bot détecte un transfert de votre rugger vers un nouveau wallet :

* **Fresh Wallet OFF** → Le bot ajoute le nouveau wallet, qu'il soit neuf ou non
* **Fresh Wallet ON** → Le bot vérifie si le nouveau wallet a déjà eu de l'activité. Si oui, il l'ignore. Si non (wallet vierge), il l'ajoute.

### Pourquoi c'est utile

Les développeurs de tokens créent souvent un nouveau wallet frais pour chaque session de création de tokens. Un wallet frais = un wallet qui n'a jamais fait de transaction avant d'être fund.

En activant Fresh Wallet, vous filtrez les transferts "parasites" — par exemple, si votre rugger envoie des SOL à un exchange, à un ami, ou à un wallet qu'il utilise pour autre chose. Ces wallets ont déjà de l'activité, donc le bot les ignore.

### Quand l'utiliser ?

| Situation | Fresh Wallet |
|---|---|
| Le dev crée toujours depuis des wallets neufs | ✅ Activé |
| Le dev réutilise parfois des wallets existants | ❌ Désactivé |
| Vous n'êtes pas sûr du comportement du dev | ❌ Désactivé (pour ne pas rater de wallets) |

> 💡 **Conseil** : Observez le comportement de votre rugger avant d'activer Fresh Wallet. Si tous ses wallets de création sont des wallets frais, activez-le. Sinon, gardez-le désactivé.
