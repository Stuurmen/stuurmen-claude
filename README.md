# Stuurmen Claude Plugin

Dit is de officiële Claude-plugin voor het Stuurmen-team. Het doel: Claude werkt direct als een verlengstuk van Stuurmen, zonder dat je elke keer context hoeft te geven over wie we zijn, wat we doen, voor wie we het doen en hoe we dat verwoorden.

De plugin laadt automatisch de Stuurmen-identiteit in elke sessie — doelgroep, methode, diensten, pricing, toon, team. Bovenop die basis zitten skills voor terugkerende taken: van LinkedIn posts tot voorstelstructuren.

## Wat er in zit

**CLAUDE.md — altijd-actieve context**
Wie Stuurmen is, voor wie we werken, hoe we werken, hoe we schrijven, hoe we voorstellen structureren, wat we kosten en met wie. Dit wordt automatisch geladen in elke Claude-sessie.

**Skills — op aanvraag**
- `/stuurmen-linkedin` — schrijft een LinkedIn post in de stem van Stijn/Stuurmen, inclusief scorekaart op thought leadership, pijn en doelgroep fit
- `/hundred-million-offers` — structureert een onweerstaanbaar aanbod via de Value Equation, price anchoring, bonus stacking en risk reversal. Gebruik bij het bouwen van voorstellen of het bepalen van pricing.

**Commands**
- `/stuurmen-setup` — eenmalig uitvoeren in Claude Code om de Stuurmen-context te activeren als globale CLAUDE.md

## Installatie

### Voor Claude web (claude.ai)
Niets te doen. De plugin is org-wide geïnstalleerd en actief in elk gesprek.

### Voor Claude Code
Voer eenmalig uit na installatie van de plugin:
```
/stuurmen-setup
```
Dit koppelt de Stuurmen CLAUDE.md als je globale context. Updates komen daarna automatisch door — je hoeft dit maar één keer te doen.

Heb je al een eigen CLAUDE.md? Die wordt bewaard als `~/.claude/CLAUDE.personal.md`.

## Updates

Als de plugin wordt bijgewerkt, is de nieuwe versie direct actief. Geen actie nodig.
