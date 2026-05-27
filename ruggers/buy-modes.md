# 🔥 Buy Modes — Simple vs Hardcore

Tu as désormais deux modes d'exécution pour tes buys, configurables par rugger : **Simple** (par défaut) et **Hardcore**. Les deux modes utilisent la même infrastructure multi-nonce — la différence est uniquement dans l'agressivité fees et compute.

## L'infrastructure derrière : le Multi-Nonce

Avant de parler des modes, comprendre l'infra. Sur Solana, le rôle de leader (le validateur qui produit le prochain bloc) tourne géographiquement toutes les **~400ms** entre les validateurs du monde entier. Si ta transaction est envoyée depuis un serveur loin du leader actuel, tu perds la race face à quelqu'un de mieux placé.

F Project résout ce problème avec une infrastructure **multi-nonce sur 5 serveurs bare-metal** répartis dans toutes les zones de validateurs :

```
🇺🇸 US-NW    (New York)
🇺🇸 US-LAX   (Los Angeles)
🇩🇪 EU-FRA   (Frankfurt)
🇳🇱 EU-AMS   (Amsterdam)
🇯🇵 ASIA-TYO (Tokyo)
```

À chaque buy, **5 transactions sont envoyées en parallèle** — une depuis chaque serveur, chacune avec son propre durable nonce. La première qui atteint le leader Solana actuel passe et consomme son nonce. Les 4 autres deviennent automatiquement invalides (leur nonce ne correspond plus) → **pas de double-fill possible, pas de risque de buy en double**.

Au lieu d'1 chance d'être le plus rapide, tu en as **5**. À chaque snipe.

⚡ Le multi-nonce est actif partout — new token creation, copytrade, quick buy. C'est l'infra de base. Les buy modes décrivent juste avec quelle agressivité tu envoies tes transactions par-dessus cette infra.

## Simple vs Hardcore — le récap

| | **🎯 Simple** | **🔥 Hardcore** |
|---|---|---|
| **Multi-nonce 5 serveurs** | ✅ | ✅ |
| **Priority fee + tip** | Tes valeurs configurées (fixes) | Outbid auto des autres snipers |
| **Priority max par buy** | Tes settings | **0.025 SOL** (cap) |
| **Tip max par buy** | Tes settings | **0.002 SOL** (cap) |
| **Compute Unit sur PumpFun** | 120 000 (généreux) | **95 000** (serré) |
| **Compute Unit sur PumpSwap** | 150 000 | 150 000 |
| **Taux de transactions qui fail** | Faible | Plus élevé (CU exceeded) |

**One-liner** : Simple = vitesse multi-région à **tes** frais. Hardcore = vitesse multi-région à **agressivité maximale** (outbid auto + CU réduit sur PumpFun pour passer plus vite).

## 🎯 Simple Mode (par défaut)

C'est le mode par défaut sur tous tes ruggers. Tes frais sont **fixes** — exactement ce que tu as configuré dans les settings du rugger (`priorityFee` + `buyTip`). Aucun outbid automatique, aucune modification dynamique.

Le compute unit limit est **généreux** : 120 000 CU sur PumpFun, 150 000 sur PumpSwap. Ça veut dire que tes transactions ont assez de budget pour s'exécuter même si le path est lourd (cashback, Token-2022, etc.).

**Pour qui** : trading "tranquille". Tu acceptes de pas toujours gagner la race face aux snipers les plus agressifs, mais tu veux que **tes buys passent**. Idéal pour les copytrades de wallets dont tu suis la performance long terme, où louper un trade ne casse pas la thèse.

## 🔥 Hardcore Mode

Hardcore, c'est l'agressivité maximale.

**Ce qui change** :

1. **Outbid dynamique** — le système monitore en temps réel les fees des autres snipers sur le token et **te place toujours au-dessus**. Bump minimum : +15% ou +0.0005 SOL (selon ce qui est plus élevé), par-dessus tes floors configurés.

2. **Caps de sécurité** — même en outbid, tu es protégé :
   - Priority fee max par buy : **0.025 SOL**
   - Tip max par buy : **0.002 SOL**
   - Worst case par buy : ~**0.027 SOL** de frais (en plus du montant que tu veux acheter)

3. **Compute Unit réduit** — 95 000 CU sur PumpFun (au lieu de 120k). Une transaction plus légère = plus rapide à scheduler par le leader = tu gagnes la race plus souvent.

### Le trade-off : plus de transactions qui fail

Le revers de la médaille du CU réduit : sur PumpFun, **certaines transactions Hardcore vont fail**. Spécifiquement avec une erreur "compute budget exceeded" — la transaction n'a pas eu assez de budget pour s'exécuter parce que le path était plus lourd que prévu (token avec extensions, validations supplémentaires, etc.).

C'est le prix à payer pour avoir la transaction la plus légère possible et gagner la race en bloc 0.

### Tes fonds sont protégés

C'est le point le plus important à comprendre :

> **Une transaction qui fail = aucun SOL prélevé** (sauf ~0.000005 SOL de base fee Solana, négligeable).

Tu n'achètes pas le token, mais tu n'es pas non plus débité de ton montant de buy ni de tes priority fees. Tu peux retenter immédiatement ou switch sur Simple pour ce rugger.

### La confirmation Hardcore

Quand tu actives Hardcore pour la première fois sur un rugger, F Project t'affiche un écran de prévention qui te rappelle les trade-offs : frais plus élevés (cappés) + plus de buys qui fail à cause du CU réduit.

Tu confirmes avec **`Yes, I still want Hardcore mode`** ou tu retournes en Simple avec **`I go back to Simple mode`**.

> *📸 Screenshot à ajouter : `images/hardcore-confirmation.png` — l'écran de prévention*

## Où configurer

Le buy mode se règle **par rugger**, dans la section principale de config du rugger :

> *📸 Screenshot à ajouter : `images/rugger-config-simple.png` et `images/rugger-config-hardcore.png`*

Tu vois clairement dans le menu :
- `🎯 Buy Mode: Simple` (par défaut)
- `🔥 Buy Mode: Hardcore` (après activation)

Clique sur la ligne `Buy Mode` pour switcher. Si tu passes en Hardcore, l'écran de confirmation s'affiche avant validation.

## Quand utiliser quoi

**Reste sur Simple si** :
- Tu débutes sur F Project — c'est le mode safe, comprends la base avant d'aller plus loin
- Tu trades des ruggers "tranquilles" où le bloc 0 n'est pas critique
- Tu veux la prédictibilité maximale (tes fees, tes paramètres, pas de surprise)

**Passe en Hardcore si** :
- Tu es sur un rugger **race-to-block-zero** où les premières secondes font toute la différence
- Tu acceptes de perdre ~20-30% des trades pour gagner les plus juteux
- Tu trades des ruggers compétitifs où d'autres snipers utilisent aussi des engines agressifs

**Setup hybride courant** : Simple sur la plupart de tes ruggers, Hardcore sur les 2-3 ruggers les plus rentables où la race est serrée.

## ⚠️ À retenir

- ✅ Simple ET Hardcore utilisent les **5 serveurs multi-nonce** — pas de différence d'infra
- ✅ Une tx Hardcore qui fail = **tu n'es PAS débité** de ton montant de buy ni des fees
- ⚠️ Hardcore = plus de fails sur PumpFun à cause du CU 95k (vs 120k en Simple)
- ⚠️ Hardcore peut consommer jusqu'à **0.027 SOL de frais par buy** (cap absolu, hors Bribe)
- 🔧 Si tu vois trop de fails sur un rugger en Hardcore, repasse en Simple — c'est probablement un rugger dont les tokens ont des paths trop lourds pour 95k CU

Pages liées :
- [💰 Buy Config](buy-config.md) — montant, slippage, et les autres params de base
- [⚙️ Config par Rugger](config-rugger.md) — vue d'ensemble des settings
- [📉 Buy the Dip](buy-the-dip.md) — DCA automatique en cas de dump
