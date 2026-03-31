# 🔀 Modes de Protection

Le mode détermine **comment le bot détecte les changements de wallet**. Un seul mode peut être actif à la fois.

---

### 📤 Last Transfer (par défaut)

Le bot surveille si le wallet envoie **la totalité de ses SOL** vers une nouvelle adresse.

**Comment ça marche :**
1. Votre rugger (Wallet A) a 2.5 SOL
2. Wallet A envoie 2.5 SOL → Wallet B (le wallet est vidé)
3. Le bot détecte que Wallet A est maintenant vide
4. Le bot supprime Wallet A et ajoute Wallet B

**C'est le schéma le plus courant** : le dev vide son wallet actuel pour en utiliser un nouveau.

---

### 📊 Exchange Pattern

Le bot surveille les transferts correspondant à des **montants précis** définis dans vos Transfer Ranges.

**Comment ça marche :**
1. Vous avez configuré une Transfer Range : 1.48 — 1.50 SOL
2. Votre rugger (Wallet Mère) envoie 1.49 SOL → Wallet C
3. Le montant est dans votre range → Wallet C ajouté au monitoring

**Ce mode est conçu pour les schémas "mère"** : un wallet central qui fund plusieurs wallets enfants avec des montants fixes.

> ⚠️ Ce mode **nécessite des Transfer Ranges** configurées pour fonctionner.

---

### Quel mode choisir ?

| Comportement du rugger | Mode recommandé |
|---|---|
| Le dev vide un wallet et passe au suivant | 📤 Last Transfer |
| Le dev a un wallet mère qui fund des wallets enfants | 📊 Exchange Pattern |
| Vous n'êtes pas sûr | 📤 Last Transfer (le plus courant) |
