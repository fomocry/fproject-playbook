# 🗺️ Naviguer dans le Bot

Le bot F Project est organisé autour de **5 boutons principaux** accessibles depuis le menu principal.

### Menu Principal

| Bouton | Description |
|---|---|
| **🎯 Ruggers** | Voir, ajouter et configurer vos adresses monitorées |
| **⚙️ Settings** | Réglages par défaut pour les nouveaux ruggers |
| **💰 Wallets** | Gérer vos wallets (créer, importer, supprimer) |
| **📊 Positions** | Voir vos positions ouvertes (tokens détenus) |
| **••• More** | Referral, langue, liens externes, Multi Buy |

En haut du menu, le **Dashboard** affiche un résumé de votre compte : nom du wallet actif, solde SOL, statut auto-buy/auto-sell, et nombre de ruggers monitorés.

### Logique de navigation

La navigation suit une logique simple :

```
Menu Principal
├── 🎯 Ruggers (liste des adresses)
│   ├── ➕ Add Rugger
│   ├── 📋 Presets
│   └── ⚙️ [Clic sur un rugger] → Config du Rugger
│       ├── 🔔 Tracking Mode
│       ├── 💰 Buy Config
│       ├── 📈 Sell Config
│       └── 🛡️ Protection
│           └── 🔀 Mode de Protection
├── ⚙️ Settings (réglages par défaut)
│   ├── Default Buy Settings
│   ├── Default Sell Settings
│   └── Default Protection
├── 💰 Wallets
├── 📊 Positions
└── ••• More
```

### Un seul bouton Back

Chaque page dispose d'un seul bouton **← Back** qui vous ramène à la page précédente. Il n'y a plus de double navigation "Back + Main Menu" — c'est plus simple et plus rapide.

### Settings par Défaut vs Config par Rugger

C'est un point important à comprendre :

* **⚙️ Settings** = les réglages **par défaut**. Ils s'appliquent automatiquement quand vous ajoutez un **nouveau** rugger.
* **Config du Rugger** = les réglages **spécifiques** à une adresse. Ils écrasent les réglages par défaut pour ce rugger uniquement.

Quand vous modifiez les Settings par défaut, les ruggers déjà existants ne sont **pas** affectés. Seuls les nouveaux ruggers hériteront des nouvelles valeurs.
