# 🗺️ Naviguer dans le Bot

Le bot F Project est organisé autour de **5 boutons principaux** accessibles depuis le menu principal.

### Menu Principal

| Bouton | Description |
|---|---|
| **🎯 Ruggers** | Voir, ajouter et configurer vos adresses monitorées |
| **⚙️ Settings** | Gas Fees |
| **💰 Wallets** | Gérer vos wallets (créer, importer, supprimer) |
| **📊 Positions** | Voir vos positions ouvertes (tokens détenus) |
| **••• More** | Referral, langue, liens externes, Multi Buy |

En haut du menu, le **Dashboard** affiche un résumé de votre compte : nom du wallet actif, solde SOL, statut auto-buy/auto-sell, et nombre de ruggers monitorés.

### Logique de navigation

```
Menu Principal
├── 🎯 Ruggers (liste des adresses — jusqu'à 30 slots)
│   ├── 🟢 Global Auto-Buy ON/OFF
│   ├── 🟢 Global Auto-Sell ON/OFF
│   ├── ➕ Add Rugger
│   ├── 📋 Presets
│   └── ⚙️ [Clic sur un rugger] → Config du Rugger
│       ├── 🔔 Tracking Mode
│       ├── 💰 Buy Config (+ Buy The Dip)
│       ├── 📈 Sell Config (+ Copier le % de Vente)
│       └── 🛡️ Protection (+ Héritage des Paramètres)
│           └── 🔀 Mode de Protection
├── ⚙️ Settings (Gas Fees)
├── 💰 Wallets
├── 📊 Positions
└── ••• More
```

### Un seul bouton Back

Chaque page dispose d'un seul bouton **← Back** qui vous ramène à la page précédente.

### Toggles Globaux

Depuis la page **🎯 Ruggers**, les boutons **Global Auto-Buy ON/OFF** et **Global Auto-Sell ON/OFF** permettent d'activer ou désactiver l'auto-achat ou l'auto-vente pour **tous vos ruggers d'un coup**. Pratique quand vous voulez tout couper rapidement (la nuit par exemple) ou tout réactiver le matin.
