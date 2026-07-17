# 🛡️ Rugger Protection — Vue d'ensemble

La Rugger Protection permet au bot de **suivre automatiquement les changements de wallets** de vos ruggers.

### Pourquoi c'est nécessaire ?

Quand vous snipez un développeur de tokens, celui-ci change régulièrement de wallet pour brouiller les pistes. Il transfère ses SOL d'un wallet A vers un wallet B, puis crée ses prochains tokens depuis le wallet B.

Sans Rugger Protection, vous perdriez la trace du dev. Avec, le bot détecte le transfert et ajoute automatiquement la nouvelle adresse.

### Qui en a besoin ?

| Situation | Protection nécessaire ? |
|---|---|
| Sniping de développeurs qui changent de wallet | ✅ Oui |
| Sniping de développeurs qui gardent le même wallet | ❌ Non |
| Copy trading de wallets de traders | ❌ Non (en général) |

### Les paramètres

| Paramètre | Description |
|---|---|
| **🔀 Mode** | Comment le bot détecte les changements de wallet ([détails](modes.md)) |
| **📌 Keep Address** | Garder l'ancienne adresse en plus de la nouvelle |
| **🆕 Fresh Wallet** | N'ajouter que les wallets neufs ([détails](fresh-wallet.md)) |
| **📏 Transfer Ranges** | Filtrer par montants de transfert précis ([détails](transfer-ranges.md)) |
| **🧹 Remove if no launch** | Supprimer automatiquement les adresses inactives après X heures |

### 🧹 Remove if no launch

Cette fonctionnalité **supprime automatiquement du monitoring** les adresses qui n'ont **ni créé ni acheté de token** pendant la durée que vous définissez.

**Le problème que ça résout :** avec la Rugger Protection qui ajoute des adresses au fil des transferts, votre liste peut vite se remplir d'adresses "mortes" — des wallets qui ne lancent jamais rien. Elles occupent vos slots pour rien.

**Comment ça marche :** vous définissez une période de probation en **heures (1 à 168**, soit 7 jours ; **0 = désactivé)**. Si l'adresse n'a produit aucune création de token ni aucun achat pendant cette période, le bot la retire automatiquement du monitoring.

**Exemple :** Remove if no launch réglé sur **2h**. La Protection détecte un transfert et ajoute le Wallet B. Si le Wallet B ne crée ni n'achète rien pendant 2 heures, il est supprimé automatiquement — votre liste reste propre.

> 💡 **Par adresse enfant** : si l'**Héritage des Paramètres est OFF**, chaque adresse enfant reçoit le Remove if no launch défini dans vos **Child Address Defaults** — vous pouvez donc avoir des durées différentes d'une adresse à l'autre (voir [Config par Rugger](../ruggers/config-rugger.md)).

### Héritage des Paramètres

Quand la Rugger Protection ajoute une nouvelle adresse (adresse enfant), cette adresse peut soit **hériter des paramètres du parent**, soit recevoir **vos paramètres personnalisés**.

Ce comportement est contrôlé par le toggle **Héritage des Paramètres** dans la config du rugger parent. Voir la page [Config par Rugger](../ruggers/config-rugger.md) pour les détails.

> ⚠️ **Important** : Si vous utilisez **Keep Address ON**, pensez à **désactiver l'héritage** pour éviter que les adresses enfants héritent du Keep Address ON et remplissent tous vos 30 slots en quelques minutes.

### Schéma de fonctionnement

```
Votre rugger (Wallet A) envoie 2.3 SOL → Wallet B
                  ↓
      Le bot détecte le transfert
                  ↓
      Le bot vérifie les critères :
      ✓ Montant dans les Transfer Ranges ?
      ✓ Wallet B est un Fresh Wallet ? (si activé)
                  ↓
      ✅ Critères OK → Wallet B ajouté au monitoring
      Keep Address OFF → Wallet A supprimé
      Keep Address ON → Wallet A gardé + Wallet B ajouté
                  ↓
      Héritage ON → Wallet B reçoit les paramètres de Wallet A
      Héritage OFF → Wallet B reçoit vos paramètres personnalisés
```

Vous recevez une notification Rugger Protection avec le détail du transfert et l'action prise par le bot.
