# 🔀 Modes de Protection

Le mode de protection détermine **comment le bot détecte les changements de wallet** de vos ruggers. Un seul mode peut être actif à la fois.

Depuis la page Protection d'un rugger, appuyez sur **🔀 Mode** pour changer de mode.

---

### 📤 Last Transfer (par défaut)

Le bot surveille si le wallet envoie **la totalité de ses SOL** vers une nouvelle adresse.

**Comment ça marche :**
1. Votre rugger (Wallet A) a 2.5 SOL
2. Wallet A envoie 2.5 SOL → Wallet B (le wallet est vidé)
3. Le bot détecte que Wallet A est maintenant vide
4. Le bot supprime Wallet A et ajoute Wallet B au monitoring

**C'est le schéma le plus courant** : le développeur vide son wallet actuel pour en utiliser un nouveau. C'est le mode recommandé par défaut.

---

### 📊 Exchange Pattern

Le bot surveille les transferts qui correspondent à des **montants précis** définis dans vos Transfer Ranges.

**Comment ça marche :**
1. Vous avez configuré une Transfer Range : 1.48 SOL — 1.50 SOL
2. Votre rugger (Wallet Mère) envoie 1.49 SOL → Wallet C
3. Le montant est dans votre range → le bot ajoute Wallet C au monitoring
4. Plus tard, le wallet mère envoie 1.49 SOL → Wallet D
5. Le bot ajoute aussi Wallet D

**Ce mode est conçu pour les schémas "mère"** : un wallet central (la mère) qui fund plusieurs wallets enfants avec des montants fixes. Chaque wallet enfant crée ensuite un token.

> ⚠️ **Ce mode nécessite des Transfer Ranges configurées** pour fonctionner. Sans ranges, le bot ne saura pas quels montants surveiller.

---

### Quel mode choisir ?

| Comportement du rugger | Mode recommandé |
|---|---|
| Le dev vide un wallet et passe au suivant | 📤 Last Transfer |
| Le dev a un wallet mère qui fund des wallets enfants | 📊 Exchange Pattern |
| Vous n'êtes pas sûr | 📤 Last Transfer (c'est le plus courant) |
