# Stuurmen Claude Plugin

Claude Code plugin voor het Stuurmen-team. Voegt Stuurmen-context en schrijfskills toe aan elke Claude-sessie.

## Wat er in zit

- **CLAUDE.md** — altijd-actieve context: wie Stuurmen is, doelgroep, diensten, aanpak, team
- **stuurmen-linkedin** — schrijft LinkedIn posts in de stem van Stuurmen

## Installatie

### Stap 1 — Plugin installeren
De plugin wordt org-wide geïnstalleerd via de Claude admin-instellingen. Automatisch actief voor iedereen.

### Stap 2 — Context activeren (eenmalig per machine)
Open Claude Code en voer uit:
```
/stuurmen-setup
```
Dit maakt een symlink van jouw globale CLAUDE.md naar de plugin. Daarna krijg je updates automatisch — je hoeft dit maar één keer te doen.

Heb je al een eigen CLAUDE.md? Die wordt bewaard als `~/.claude/CLAUDE.personal.md`.

## Skills gebruiken

```
/stuurmen-linkedin [onderwerp]
```

## Updates

Als de plugin wordt bijgewerkt door de admin, is de nieuwe CLAUDE.md direct actief op jouw machine. Geen actie nodig.
