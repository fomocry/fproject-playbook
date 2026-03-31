# 🆕 Fresh Wallet

Le paramètre **Fresh Wallet** est un filtre de sécurité. Quand il est activé, le bot n'ajoutera au monitoring que les wallets **qui n'ont jamais eu d'activité**.

### Comment ça marche

* **Fresh Wallet OFF** → Le bot ajoute le nouveau wallet, qu'il soit neuf ou non
* **Fresh Wallet ON** → Le bot vérifie si le nouveau wallet a déjà eu de l'activité. Si oui, il l'ignore. Si non, il l'ajoute.

### Pourquoi c'est utile

Les développeurs créent souvent un wallet frais pour chaque session. En activant Fresh Wallet, vous filtrez les transferts "parasites" — envois à un exchange, à un ami, ou à un wallet utilisé pour autre chose.

### Quand l'utiliser ?

| Situation | Fresh Wallet |
|---|---|
| Le dev crée toujours depuis des wallets neufs | ✅ Activé |
| Le dev réutilise parfois des wallets existants | ❌ Désactivé |
| Vous n'êtes pas sûr | ❌ Désactivé (pour ne pas rater de wallets) |

> 💡 **Conseil** : Observez le comportement de votre rugger avant d'activer Fresh Wallet.
