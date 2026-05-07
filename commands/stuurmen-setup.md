---
name: stuurmen-setup
description: Koppelt de Stuurmen CLAUDE.md als globale context. Eenmalig uitvoeren na installatie. Updates worden daarna automatisch opgepikt.
---

Voer het volgende bash-commando uit om de Stuurmen-context te activeren:

```bash
DEST=~/.claude/CLAUDE.stuurmen.md

# Stap 1: probeer plugin lokaal te vinden (werkt als marketplace al is gesynchroniseerd)
PLUGIN_CLAUDE=$(find ~/.claude/plugins -name "CLAUDE.md" -path "*/stuurmen*" 2>/dev/null | head -1)

if [ -n "$PLUGIN_CLAUDE" ]; then
  # Gevonden in lokale plugin-installatie: symlink ernaar zodat updates automatisch doorkomen
  LINK_TARGET="$PLUGIN_CLAUDE"
  echo "Plugin gevonden via marketplace: $PLUGIN_CLAUDE"
else
  # Niet lokaal gevonden: download direct van GitHub
  echo "Plugin niet lokaal gevonden. Downloaden via GitHub..."
  if ! command -v gh &>/dev/null; then
    echo "GitHub CLI (gh) is niet geïnstalleerd. Installeer via: brew install gh"
    exit 1
  fi
  gh api repos/Stuurmen/stuurmen-claude/contents/CLAUDE.md --jq '.content' | base64 -d > "$DEST"
  if [ $? -ne 0 ] || [ ! -s "$DEST" ]; then
    echo "Download mislukt. Check of je toegang hebt tot Stuurmen/stuurmen-claude op GitHub (gh auth login)."
    exit 1
  fi
  LINK_TARGET="$DEST"
  echo "CLAUDE.md gedownload naar $DEST"
fi

# Stap 2: bewaar bestaande CLAUDE.md als die niet van Stuurmen is
if [ -f ~/.claude/CLAUDE.md ] && ! grep -q "Kill off the average" ~/.claude/CLAUDE.md; then
  mv ~/.claude/CLAUDE.md ~/.claude/CLAUDE.personal.md
  echo "Bestaande CLAUDE.md bewaard als ~/.claude/CLAUDE.personal.md"
fi

# Stap 3: symlink zetten
ln -sf "$LINK_TARGET" ~/.claude/CLAUDE.md
echo "Stuurmen context actief."

# Stap 4: verplichte skills installeren
echo ""
echo "Skills installeren..."

if ! command -v npx &>/dev/null; then
  echo "! npx niet gevonden. Installeer Node.js via https://nodejs.org en draai dit script opnieuw."
else
  # google-search-console: vereist voor de stuurmen-case indexing-workflow
  if [ -f ~/.agents/skills/google-search-console/SKILL.md ] || [ -f ~/.claude/skills/google-search-console/SKILL.md ]; then
    echo "✓ google-search-console al geïnstalleerd"
  else
    echo "→ google-search-console installeren..."
    npx skills add kostja94/marketing-skills@google-search-console -g -y
    echo "✓ google-search-console geïnstalleerd"
  fi
fi
```

Klaar. De context is nu actief in elke Claude Code-sessie op deze machine.

Heb je geen toegang tot GitHub? Vraag dan een collega om het `CLAUDE.md` bestand uit de plugin te sturen en sla het op als `~/.claude/CLAUDE.md`.
