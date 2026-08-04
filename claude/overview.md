# 🤖 Vue d'ensemble & Connexion

Claude x F Project, c'est la possibilité de **parler à ton compte F Project comme tu parlerais à un analyste** assis à côté de toi.

Tu écris « analyse ce token » ou « trouve-moi un rugger à sniper », et Claude fait le travail : il fouille les financements, remonte les chaînes de wallets, calcule les stats, et te répond en français normal. Pas de commandes à apprendre, pas de syntaxe. Tu demandes, il creuse.

## C'est quoi, exactement ?

Claude est une IA (comme ChatGPT, mais celle d'Anthropic). F Project lui a donné deux choses :

1. **Des mains** — un accès direct à ton compte F Project : tes wallets, tes trackers, tes positions. Le même compte que le bot Telegram. Si Claude modifie un tracker, tu le vois instantanément dans le bot, et inversement.
2. **Un cerveau** — toute la méthode F Project est chargée dans sa tête : la physique de la courbe PumpFun, le SL naturel, la méthode exchange, les bandes hair-thin, la qualification des ruggers. Il ne devine pas, il applique ce qu'on enseigne dans la formation.

> 💡 Imagine le bot Telegram comme le **volant** de la voiture, et Claude comme le **copilote** qui lit la carte, vérifie l'itinéraire et peut tenir le volant si tu lui demandes. C'est la même voiture.

## Connexion — 4 étapes

1. Ouvre Claude ([claude.ai](https://claude.ai) ou l'application), puis va dans **Paramètres → Connecteurs**
2. Clique sur **Ajouter un connecteur personnalisé**
3. Colle cette adresse :

```
https://mcp.fproject.gg/mcp
```

4. Connecte-toi avec **Telegram** quand on te le demande

C'est tout. Pour vérifier que ça marche, écris simplement :

> « Comment va mon portefeuille ? »

Si Claude te répond avec tes soldes et tes positions, tu es connecté.

## Lecture seule ou écriture ?

Au moment de la connexion, Claude te demande quelles **permissions** tu veux lui donner. Il y en a deux niveaux :

| Niveau | Ce que Claude peut faire |
|---|---|
| **Lecture** (par défaut) | Analyser, chercher, calculer, te conseiller. Il voit tout, il ne touche à rien. |
| **Écriture** | En plus : configurer tes trackers, ajuster tes réglages, et passer des ordres — toujours après **ta** confirmation. |

> 💡 **Conseil pour débuter** : commence en lecture seule. Utilise Claude pour analyser et apprendre pendant quelques jours. Quand tu es à l'aise, reconnecte-toi en accordant l'écriture.

## Ce que Claude ne pourra jamais faire

Ce ne sont pas des promesses, ce sont des **règles bloquées côté serveur** — même si tu le lui demandes, c'est impossible :

* ❌ Voir, demander ou exporter tes **clés privées** ou ta **seed phrase**
* ❌ **Retirer** des SOL de tes wallets
* ❌ Créer ou importer des wallets (ça reste exclusivement sur le bot Telegram)
* ❌ Agir sur le compte de quelqu'un d'autre

> ⚠️ L'équipe F Project ne te demandera **JAMAIS** ta clé privée. Ni sur Discord, ni sur Telegram, ni via Claude. Si quelqu'un le fait, c'est un scam — signale-le.

Pages suivantes :

* [💬 Comment parler à Claude](utilisation.md)
* [🔐 Trades, confirmations & bonnes pratiques](securite.md)
