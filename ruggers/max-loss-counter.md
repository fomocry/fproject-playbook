# 🛑 Max Loss Counter

Coupe automatiquement le copytrade sur un rugger après un nombre défini de **pertes consécutives**. Évite de continuer à perdre sur un rugger qui s'est dégradé.

## Comment ça marche

Le système compte les ventes perdantes. Quand le compteur atteint le seuil que tu as défini, l'auto-buy se met en pause. Tes positions ouvertes restent intactes — seuls les nouveaux copytrade sont bloqués.

**Le comptage se fait sur la racine, pas sur chaque enfant.** Quand la Rugger Protection ajoute des adresses enfants à partir d'un rugger, les pertes sont additionnées **sur le rugger mère (racine)**, jamais séparément enfant par enfant. Quand ce total atteint le max, l'auto-buy se met en pause pour **toute la chaîne** — la mère et tous ses enfants d'un coup.

Le compteur **reset à zéro dès qu'une vente est gagnante**, sur **n'importe quel enfant** de la chaîne. Une victoire quelque part dans la famille remet toute la racine à zéro. C'est uniquement une vraie série de pertes accumulées qui te sort.

Tu reçois une notification quand le seuil est hit, et le rugger passe en status `PAUSED`. Tu peux le réactiver manuellement quand tu veux.

## Configuration

Par rugger, dans **Config par Rugger → Max Loss Counter** :

```
Max Losses:   10   (défaut — configurable de 1 à 20)
Action:       Pause auto-buy sur toute la chaîne
```

**Paramètre** :
- **Max Losses** — seuil de pertes accumulées sur la racine avant déclenchement (défaut 10, de 1 à 20)

Le seuil idéal dépend de l'agressivité du rugger. Pour un rugger qui scalpe avec 30-40% de win rate, configure plus large (5-7). Pour un rugger qui devrait avoir un win rate élevé, configure serré (2-3).

## Use case

Beaucoup de ruggers ont des phases de chaleur puis se refroidissent. Au lieu de devoir surveiller manuellement leurs perfs, le système coupe la perte pour toi. Tu reviens, tu check si le rugger a recover ou si tu le retires complètement.

## 💡 Combo recommandé

`Max Consecutive Losses: 3` + `Notification "Rugger Auto-Disabled"` ON

Tu sais immédiatement quand un rugger s'éteint, tu peux décider de le purge ou de le mettre en observation. Particulièrement puissant si tu trades 20+ ruggers en parallèle — impossible de tout surveiller à l'œil.

Pages liées :
- [⚙️ Config par Rugger](config-rugger.md) — vue d'ensemble des settings par rugger
- [📉 Buy the Dip](buy-the-dip.md) — combo pour limiter les pertes en dip
- [🔔 Notifications](../outils/notifications.md) — config des alertes
