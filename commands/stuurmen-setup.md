---
name: stuurmen-setup
description: Koppelt de Stuurmen CLAUDE.md als globale context. Eenmalig uitvoeren na installatie. Updates worden daarna automatisch opgepikt.
---

Voer het volgende bash-commando uit om de Stuurmen-context te activeren:

```bash
# Zoek het plugin CLAUDE.md bestand
PLUGIN_CLAUDE=$(find ~/.claude/plugins -name "CLAUDE.md" -path "*/stuurmen/*" 2>/dev/null | head -1)

if [ -z "$PLUGIN_CLAUDE" ]; then
  echo "Stuurmen plugin CLAUDE.md niet gevonden. Is de plugin geïnstalleerd?"
  exit 1
fi

# Als er al een CLAUDE.md is die niet van Stuurmen is: bewaar die
if [ -f ~/.claude/CLAUDE.md ] && ! grep -q "Kill off the average" ~/.claude/CLAUDE.md; then
  mv ~/.claude/CLAUDE.md ~/.claude/CLAUDE.personal.md
  echo "Bestaande CLAUDE.md bewaard als ~/.claude/CLAUDE.personal.md"
fi

# Maak een symlink zodat updates automatisch doorkomen
ln -sf "$PLUGIN_CLAUDE" ~/.claude/CLAUDE.md
echo "Stuurmen context actief. Updates via de plugin komen voortaan automatisch door."
```

Klaar. De context is nu actief in elke Claude Code-sessie op deze machine.
