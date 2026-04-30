# Stuurmen Claude Plugin

Dit is de officiële Claude-plugin voor het Stuurmen-team. Het doel: Claude werkt direct als een verlengstuk van Stuurmen, zonder dat je elke keer context hoeft te geven over wie we zijn, wat we doen, voor wie we het doen en hoe we dat verwoorden.

De plugin laadt automatisch de Stuurmen-identiteit in elke sessie — doelgroep, methode, diensten, pricing, toon, team. Bovenop die basis zitten skills voor terugkerende taken: van LinkedIn posts tot voorstelstructuren.

## Wat er in zit

**Altijd-actieve context**
Wie Stuurmen is, voor wie we werken, hoe we werken, hoe we schrijven, hoe we voorstellen structureren, wat we kosten en met wie.

**Skills — op aanvraag**
- `/stuurmen-linkedin` — schrijft een LinkedIn post in de stem van Stijn/Stuurmen, inclusief scorekaart op thought leadership, pijn en doelgroep fit
- `/hundred-million-offers` — structureert een onweerstaanbaar aanbod via de Value Equation, price anchoring, bonus stacking en risk reversal. Gebruik bij het bouwen van voorstellen of het bepalen van pricing.

## Gebruik

### Claude web (claude.ai)
Niets te doen. De context is actief in elk gesprek.

### Claude Code
Voer dit eenmalig uit in je terminal (niet in Claude zelf):

```bash
mkdir -p ~/.claude && gh api repos/Stuurmen/stuurmen-claude/contents/CLAUDE.md --jq '.content' | base64 -d > ~/.claude/CLAUDE.stuurmen.md && ([ -f ~/.claude/CLAUDE.md ] && ! grep -q "Kill off the average" ~/.claude/CLAUDE.md && mv ~/.claude/CLAUDE.md ~/.claude/CLAUDE.personal.md || true) && ln -sf ~/.claude/CLAUDE.stuurmen.md ~/.claude/CLAUDE.md && echo "Stuurmen context actief."
```

Dit vereist de [GitHub CLI](https://cli.github.com) (`gh`) en toegang tot de Stuurmen GitHub-organisatie. Heb je dat nog niet? Vraag Stijn.

Na deze stap is de context actief in elke Claude Code-sessie op jouw machine. Als de plugin wordt bijgewerkt, run je dit commando opnieuw om de nieuwste versie op te halen.
