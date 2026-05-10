# 🛑 Max Loss Counter

Coupe automatiquement le copytrade sur un rugger après un nombre défini de **pertes consécutives**. Évite de continuer à perdre sur un rugger qui s'est dégradé.

## Comment ça marche

Le système compte les positions perdantes consécutives sur chaque rugger. Quand le compteur atteint le seuil que tu as défini, l'auto-buy se désactive sur ce rugger spécifique. Tes positions ouvertes restent intactes — seuls les nouveaux copytrade sont bloqués.

Le compteur **reset à zéro dès qu'une position est gagnante**. Donc une suite de 3 pertes → 1 win → 3 pertes ne déclenche pas le seuil de 5 pertes consécutives. C'est uniquement une vraie série de pertes qui te sort.

Tu reçois une notification quand le seuil est hit, et le rugger passe en status `PAUSED`. Tu peux le réactiver manuellement quand tu veux.

## Configuration

Par rugger, dans **Config par Rugger → Max Loss Counter** :

```
Max Consecutive Losses:   3
Action:                   Auto-disable copytrade
```

**Paramètre** :
- **Max Consecutive Losses** — seuil de pertes d'affilée avant déclenchement (ex: 3, 5, 10)

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
