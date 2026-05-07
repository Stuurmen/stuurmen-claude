---
name: stuurmen-case
description: Schrijf een strategie-gestuurde case voor de Stuurmen-website op basis van bronmateriaal (Brand Concept, Documentatie, transcripts). Gebruik wanneer een teamlid een case wil maken of vernieuwen. Output is een ingevulde markdown-case (NL eerst, EN op aanvraag), meta title/description, gap-list, en hulp bij Google Search Console URL-indexing en IndexNow. Trigger: "case schrijven", "case [klantnaam]", "case vernieuwen", "/stuurmen-case".
---

# Stuurmen Case Writer

Schrijf cases voor stuur.men die Stuurmens propositie waarmaken. Strategie-led. Met pijn, verschuiving, bewijs, quote, resultaat. Niet design-led.

---

## Wanneer deze skill gebruiken

- Een teamlid wil een nieuwe case schrijven of een bestaande herschrijven
- Bronmateriaal staat klaar in `context/cases/[klant]/` of wordt aangeleverd
- Doel: publicatie op stuur.men (NL eerst, EN later)

Niet voor:
- Een interne projectsamenvatting (gebruik `/stuurmen-linkedin` voor extern, of laat het projectteam dit doen)
- Een blog of artikel (andere structuur)
- Een proposal (gebruik `/hundred-million-offers` voor offerwerk)

---

## Volg dit proces

### Fase 1 — Inventarisatie

1. Vraag (of detecteer): **welke klant?**
2. Check `context/cases/[klant]/` voor bestanden. Lees titels en inhoud:
   - Brand Concept Presentatie (PDF) — strategie en positionering
   - Documentatie (PDF) — workshop-output, hopes & fears, klantfeedback, strategie in één zin
   - Project Plan — scope, looptijd, jaar
   - Brand Summary — definitieve narratief
   - Web Strategy — als er een site bij hoort
   - Transcripts (txt/md) — letterlijke quotes uit gesprekken
3. **Bepaal type:**
   - Type A (branding) als er Brand Concept Presentatie + Documentatie zijn
   - Type B (web) als alleen Web Strategy + Project Plan, zonder merkstrategie-traject
   - Twijfel? Type A
4. Vraag het teamlid:
   - **Welke taal eerst?** (default: NL)
   - **Is er al een klantquote beschikbaar?** Zo niet, markeer als gat
   - **Is de URL al bekend?** (voor meta + indexing later)
   - **Zijn er resultaten/cijfers bekend (3-6 mnd na oplevering)?** Zo niet, gat

### Fase 2 — Genereer de case

Lees de relevante template:
- Type A: `references/case-template-branding.md`
- Type B: `references/case-template-web.md`

Vul de modules in volgorde. Voor elke module:
- **Bron is leidend.** Schrijf wat in het materiaal staat, niet wat plausibel klinkt.
- **Stuurmen-toon:** je/jij, direct, geen filler, geen em dashes (—), geen "ontzorgen" / "klantgericht" / "full-service" / "quality first".
- **Geen verzonnen feiten.** Als iets niet in de bron staat, laat het leeg en zet het in de gap-list.
- **De strategische verschuiving (Module 5) is het anker.** Alle andere modules ondersteunen die verschuiving.

Schrijf de case als één markdown-bestand met YAML-frontmatter:

```yaml
---
klant: <naam>
type: branding | web
taal: nl
slug: <kebab-case-slug>
url: https://stuur.men/project/<slug>  # NL is root, EN op /en/project/<slug>
meta_title: <max 60 karakters>
meta_description: <140-160 karakters>
og_image: <pad of placeholder>
gepubliceerd: <YYYY-MM-DD of "concept">
cta_persoon: stijn | barend  # branding=stijn, web=barend
faq_active: true | false  # default true voor branding, false voor web
case_card:
  card_titel: <max 50 karakters>
  card_klantnaam: <bedrijfsnaam>
  card_categorie: [tag, tag, tag]  # max 3
  card_thumbnail_alt: <beschrijvende alt-tekst>
gaps:
  - <wat ontbreekt nog>
---

# <H1: strategische verschuiving>

<!-- module-1: Case header -->
<modulen in volgorde, elk met een HTML-comment die de Figma-component noemt -->
```

Elke module krijgt een HTML-comment-header `<!-- module-X: ComponentNaam -->` zodat de developer of het importscript later weet welk Storyblok-component erbij hoort.

### Fase 3 — Toon de case + gap-list

Toon het teamlid:
1. **De volledige case** in het chatvenster
2. **Gap-list:** wat ontbreekt nog. Concreet, niet vaag. Bijvoorbeeld:
   - "Klantquote: bel Joris met de vijf vragen uit de playbook"
   - "Resultaten Module 8: nog geen cijfers beschikbaar — bel klant na 3 maanden"
   - "Hero-beeld: vraag het designteam om een geschikt beeld"
3. **Volgende stappen:**
   - Akkoord op de NL versie? → vertaling EN
   - Akkoord op beide versies? → live zetten + indexing-stap

### Fase 4 — EN vertaling (alleen op verzoek na NL-akkoord)

Als het teamlid akkoord geeft op NL:
1. Vertaal de hele case naar Engels
2. Behoud de strategische verschuiving (Module 5) — vaak vraagt dit een herformulering, geen letterlijke vertaling
3. Genereer EN meta title + description (geen letterlijke vertaling van NL — denk vanuit Engelse zoekwoorden)
4. Pas pad aan: `/en/project/<slug>` (slug mag identiek blijven aan NL voor consistentie, of vertaald, kies consistent voor de hele site)
5. Voeg hreflang-instructie toe in frontmatter

### Fase 5 — Indexing (alleen na live)

Als het teamlid bevestigt dat de URL live is:

1. Lees `references/indexing-instructions.md`
2. Voer de stappen uit:
   - Sitemap re-submit via GSC API (gebruik `google-search-console` skill als beschikbaar)
   - URL Inspection: NL en EN versie checken
   - IndexNow POST naar Bing/Yandex (vraag of de IndexNow-key al is gezet; zo niet, eerste setup vereist)
3. Rapporteer: status per URL, eventuele blockers (404, robots, noindex)
4. Adviseer: monitor over 2-4 weken via GSC

---

## Belangrijke regels

### Wat je nooit doet

- **Geen losse design-modules** zonder strategische context. "Brand design" als kop is verboden. Wel: "Hoe we de verschuiving zichtbaar maakten."
- **Geen verzonnen quotes.** Als de quote er niet is, zet hem in de gap-list. Schrijf nooit een fake quote.
- **Geen em dashes** (—). Vervang door punt of komma.
- **Geen filler:** "ontzorgen", "klantgericht", "full-service", "quality first", "client-centric".
- **Geen "u".** Altijd "je/jij".
- **Geen overdrijving.** "Aanvragen verdrievoudigd" alleen als dat écht zo is. Anders: "Aanvragen merkbaar gestegen" of "wat we tot nu toe zien".
- **Geen marketing-slogan in de hero-titel.** Wel de strategische verschuiving (van X naar Y).

### Wat je altijd doet

- **Bron-checken.** Als iets niet in het materiaal staat, vraag of markeer als gat.
- **De verschuiving als anker.** Module 5 staat. Alles ondersteunt die zin.
- **Klant-eigen taal in Module 4** ("klanten zien ons als..." citeert letterlijk uit het workshop-materiaal).
- **Module 10 standaard aan** voor Type A (GEO-bait).
- **Module 11 (FAQ Accordion) standaard aan** voor Type A. Optioneel voor Type B.
- **Meta title + description** altijd genereren, beide talen.
- **Case-card content altijd genereren** (titel, klantnaam, categorie-tags, thumbnail-alt) zodat de case ook op de overzichtspagina past zonder hertypen.
- **Figma-componentnaam vermelden per module** in de output zodat porteren naar Storyblok 1-op-1 werkt.
- **Schema.org markup** snippet meeleveren voor de developer (`Article` + `FAQPage` als Accordion aanwezig).

---

## Persoon in CTA card

Default per case-type:
- **Branding-cases (Type A):** Stijn (founder, strategie-eigenaar)
- **Web-only cases (Type B):** Barend (digital owner, eindverantwoordelijk voor digital design)

Nooit standaard Nick voor digital cases. Nick is verantwoordelijk voor brand identity, drukwerk en fotografie, niet voor web of digital.

---

## Bestanden in deze skill

- `SKILL.md` — dit bestand, het proces
- `references/case-template-branding.md` — Type A, 12 modules + meta + case-card
- `references/case-template-web.md` — Type B, 7 modules + optioneel FAQ + case-card
- `references/playbook.md` — handleiding voor teamleden, 5 vragen voor klantquote, do/don'ts
- `references/seo-geo-checklist.md` — SEO + GEO optimalisaties per case
- `references/indexing-instructions.md` — GSC, IndexNow, monitoring
- `references/component-spec.md` — Figma-component mapping per module (briefing voor design en development)

---

## Voorbeeld-aanroep

```
/stuurmen-case mobuline
```

Of in vrije tekst:
```
Schrijf een case voor Mobuline. Bronnen staan in context/cases/mobuline:mantaroofs/.
```

---

## Output-locatie

Schrijf de gegenereerde case naar `context/cases/[klant]/case-[taal].md`.

Bijvoorbeeld:
- `context/cases/mobuline:mantaroofs/case-nl.md`
- `context/cases/mobuline:mantaroofs/case-en.md`

Zo blijft de case bij het bronmateriaal staan en is herschrijven later eenvoudig.
