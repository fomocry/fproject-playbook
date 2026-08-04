# 🔐 Trades, confirmations & bonnes pratiques

## Comment un ordre se passe

Quand tu demandes à Claude d'acheter, de vendre ou de modifier un tracker (et que tu as accordé l'écriture), ça se passe **toujours** en trois temps :

```
1. Claude te récapitule TOUT en chiffres clairs :
   « Achat de 0.5 SOL sur [token] via le wallet W1,
     bribe 0.02, TP +100% qui vend 100%. On y va ? »
                    ↓
2. TU confirmes (ou pas)
                    ↓
3. Claude exécute, vérifie la transaction, et te dit ce qui s'est passé
```

Rien ne part sans ton « oui ». C'est une règle serveur, pas une politesse.

> ⚠️ **« Vends tout » = liste complète d'abord.** Si tu demandes de tout liquider, Claude te liste chaque position concernée et attend une confirmation sur l'ensemble. Pas de vente surprise.

## Le mode YOLO

Il existe un interrupteur qui **supprime l'étape de confirmation** : le mode YOLO. Une fois activé, Claude achète et vend sans te redemander.

* Il est **désactivé par défaut**
* Claude ne te proposera **jamais** de l'activer de lui-même
* Si tu l'actives, il te rappellera d'abord clairement ce que ça implique

> ⚠️ Le mode YOLO est fait pour les membres expérimentés qui enchaînent les ordres et savent exactement ce qu'ils font. Si tu te demandes si c'est pour toi, la réponse est non — pas encore.

## Les garde-fous automatiques

Même en écriture, des limites dures s'appliquent côté serveur :

| Limite | Valeur |
|---|---|
| Achat maximum par wallet | **10 SOL** |
| Wallets maximum par trade | **10** |
| Trackers maximum par wallet | **30** |
| Confirmation obligatoire | Tout ordre (sauf YOLO activé par toi) |

## Les bonnes pratiques

**1. Vérifie le buy amount après chaque ajout de tracker.** Un tracker ajouté sans montant d'achat ne fera **jamais** rien — c'est le piège silencieux classique. Claude te le signale systématiquement, mais prends l'habitude de vérifier : « montre-moi la config de ce tracker ».

**2. Relis le récapitulatif avant de dire oui.** Claude annonce le token, le montant, les wallets et les réglages avant chaque ordre. Ces 5 secondes de lecture sont ta vraie protection.

**3. Ne lui demande pas de garanties.** Claude ne te dira jamais « ce trade est sûr » — parce que ça n'existe pas dans ce business. S'il te donne une espérance de gain, c'est une statistique sur un échantillon, pas une promesse. Les pertes font structurellement partie du jeu.

**4. Un doute, une question.** Tu peux toujours demander « pourquoi tu proposes ça ? » avant de confirmer. Claude justifie chaque réglage par le mode opératoire du rugger analysé.

## 🐛 Un bug ? Un comportement bizarre ?

Ouvre un **ticket sur Discord**, tout de suite. Pas dans deux jours.

Dans le ticket, mets :

* Ce que tu as demandé à Claude, mot pour mot
* Ce qui s'est passé au lieu de ce qui aurait dû se passer
* Le CA concerné et l'heure approximative
* Une capture d'écran de la conversation

> 💡 **Ne bricole pas tes réglages en attendant la réponse.** Décris juste ce que tu as vu — si tu modifies tout, on perd l'état exact dans lequel le bug s'est produit, et il devient impossible à reproduire.

## En résumé

* Claude **voit** tout ton compte, **n'agit** qu'avec ta permission, et **ne touchera jamais** à tes clés
* Chaque ordre est confirmé en chiffres avant de partir
* Il applique la méthode F Project — y compris quand ça veut dire te dire non
* Le trading de memecoins reste à haut risque : Claude t'aide à décider, mais les décisions et le capital restent les tiens
