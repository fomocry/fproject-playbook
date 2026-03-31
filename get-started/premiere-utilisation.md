# 🐣 Première utilisation

### Étape 1 — Lancer le bot

Ouvrez Telegram et recherchez **F Project** ou cliquez sur le lien direct fourni lors de votre inscription. Tapez `/start` pour démarrer.

Le bot affichera le **Dashboard** avec un résumé de votre compte : wallet, solde, nombre de ruggers monitorés et statut auto-buy/auto-sell.

### Étape 2 — Créer ou importer un wallet

Avant de pouvoir utiliser le bot, vous avez besoin d'un wallet Solana.

Depuis le menu principal, allez dans **💰 Wallets** :
* **Generate Wallet** — Le bot crée un nouveau wallet pour vous. Sauvegardez la clé privée en lieu sûr.
* **Import Wallet** — Collez la clé privée d'un wallet existant.

> ⚠️ Ne partagez **jamais** votre clé privée avec qui que ce soit. L'équipe F Project ne vous la demandera jamais.

### Étape 3 — Alimenter votre wallet

Envoyez du SOL sur l'adresse de votre wallet F Project. Il vous faut du SOL pour :
* Acheter des tokens (le montant que vous configurez dans Buy Amount)
* Payer les frais de transaction (gas fees)

Un minimum de **0.2 SOL** est recommandé pour commencer (0.1 SOL pour le Buy Amount + les gas fees qui s'ajoutent à chaque transaction).

### Étape 4 — Ajouter votre premier rugger

Allez dans **🎯 Ruggers** → **➕ Add Rugger** et collez l'adresse du wallet que vous souhaitez monitorer.

Le rugger sera ajouté sans aucun réglage — il est "nu". C'est à vous de le configurer en cliquant dessus pour définir vos paramètres d'achat, de vente, de tracking et de protection.

> 💡 **Conseil** : Si vous avez déjà un **Preset** sauvegardé, vous pouvez l'appliquer en un clic après l'ajout pour ne pas tout reconfigurer manuellement.

### Étape 5 — Configurer votre rugger

Appuyez sur votre rugger pour accéder à sa config. Les éléments essentiels à configurer :
* **🔔 Tracking Mode** — Que doit surveiller le bot ? (New Tokens, Track Buys, etc.)
* **💰 Buy Config** — Combien acheter, avec quel delay, quelles limites de market cap
* **📈 Sell Config** — TP/SL, Trailing SL, No Activity
* **🟢 Auto-Buy / Auto-Sell** — Activer l'achat et la vente automatiques

### C'est parti !

Dès que votre rugger est configuré et que Auto-Buy est activé, le bot surveillera l'adresse et exécutera des achats automatiquement selon vos critères.
