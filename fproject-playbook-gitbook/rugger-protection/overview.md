# 🛡️ Rugger Protection — Vue d'ensemble

La Rugger Protection est un système qui permet au bot de **suivre automatiquement les changements de wallets** de vos ruggers.

### Pourquoi c'est nécessaire ?

Quand vous snipez un développeur de tokens, celui-ci change régulièrement de wallet pour brouiller les pistes. Il transfère ses SOL d'un wallet A vers un wallet B, puis crée ses prochains tokens depuis le wallet B.

Sans Rugger Protection, vous perdriez la trace du dev à chaque changement de wallet. Avec la Rugger Protection, le bot détecte le transfert et ajoute automatiquement la nouvelle adresse à votre monitoring.

### Qui en a besoin ?

| Situation | Protection nécessaire ? |
|---|---|
| Sniping de développeurs qui changent de wallet | ✅ Oui |
| Sniping de développeurs qui gardent le même wallet | ❌ Non |
| Copy trading de wallets de traders | ❌ Non (en général) |

### Activer / Désactiver

Depuis la config d'un rugger, appuyez sur **🛡️ Protection**. Le toggle **🛡️ Protection: ON/OFF** en haut de la page active ou désactive toute la protection. Quand c'est désactivé, tous les paramètres en dessous sont ignorés.

### Les paramètres

| Paramètre | Description |
|---|---|
| **🔀 Mode** | Comment le bot détecte les changements de wallet ([détails](modes.md)) |
| **📌 Keep Address** | Garder l'ancienne adresse en plus de la nouvelle |
| **🆕 Fresh Wallet** | N'ajouter que les wallets neufs ([détails](fresh-wallet.md)) |
| **📏 Transfer Ranges** | Filtrer par montants de transfert précis ([détails](transfer-ranges.md)) |

### Comment ça fonctionne (schéma simple)

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
```

Vous recevez une notification Rugger Protection avec le détail du transfert et l'action prise par le bot.
