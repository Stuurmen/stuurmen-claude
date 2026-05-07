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
4. **Pre-flight: stel deze vragen ALTIJD aan het teamlid voordat je begint te schrijven.** Geen aannames maken. Niet schatten. Niet doortikken op basis van iets dat in een PDF staat — een PDF is interne documentatie, geen publicatieklaar materiaal.

   **Feiten die in de case komen:**
   - **FTE bij de klant** ten tijde van het traject (concrete getallen, geen ranges als "20-50 FTE" tenzij je het echt niet kan achterhalen)
   - **Looptijd traject** (van wanneer tot wanneer, in maanden of jaren — Stuurmen-trajecten zijn vaak ~1 jaar incl. fase 3)
   - **Jaartallen** — start en eind van het traject
   - **C-level contact bij de klant** (voornaam + achternaam + functie). Niet aannemen op basis van wie in de Documentatie staat als spreker.
   - **Wie heeft de naam bedacht?** (Stuurmen, klant zelf, externe partij). Zelden Stuurmen, vaak de klant.

   **Output-keuzes:**
   - **Welke taal eerst?** (default: NL)
   - **Welke CTA-persoon?** stijn / anne / round-robin (alleen deze drie, cal.com-integratie).
   - **Is de live URL al bekend?** (voor meta + indexing later)

   **Bewijslast:**
   - **Is er al een klantquote beschikbaar?** Zo niet, markeer als gat
   - **Zijn er resultaten/cijfers bekend (3-6 mnd na oplevering)?** Zo niet, gat
   - **Welke live-links zijn relevant?** Nieuwe website, configurator, app, drukwerk-PDF, persbericht
   - **Welke beelden zijn beschikbaar?** Vraag specifiek door:
     - Productfotografie of lifestyle-fotografie
     - Drukwerk (mockups of foto's van tastbaar werk)
     - Website screenshots (desktop + mobile)
     - Configurator/tool screenshots
     - Motion stills, social-uitingen, brand book pagina's
     Streef naar minimaal 8 beelden voor de "Het werk"-module.

   **Verifiëren:**
   - **Mogen alle in de Documentatie genoemde partners en samenwerkingen openbaar?** Specifiek vragen per derde-partij die je tegenkomt (engineers, leveranciers, samenwerkingspartners). Een naam die intern werd genoemd, mag niet automatisch naar buiten.
   - **Zijn er pijnpunten of citaten die je in de PDF zag, die de klant niet publiek wil zien?** Klanten hebben in interne workshops vaak verfrissend eerlijk gesproken. Op een publieke case moeten die uitspraken vaak geparafraseerd, gedempt, of weggelaten worden.

Live-links zijn niet alleen output-bewijs, maar ook waardevolle interne links voor SEO. Vermeld ze waar relevant in Module 7 (zichtbaar maken), Module 7.5 (Het werk) of Module 8 (resultaten).

### Fase 2 — Genereer de case

Lees de relevante template:
- Type A: `references/case-template-branding.md`
- Type B: `references/case-template-web.md`

Vul de modules in volgorde. Voor elke module:
- **Bron is leidend, maar niet blind.** Schrijf wat in het materiaal staat — maar denk altijd: mag dit naar buiten? Zou de klant zich hierin herkennen, of zou hij ervan schrikken?
- **Stuurmen-toon:** je/jij, direct, geen filler, geen em dashes (—), geen "ontzorgen" / "klantgericht" / "full-service" / "quality first".
- **Geen verzonnen feiten.** Als iets niet in de bron staat, laat het leeg en zet het in de gap-list. Niet schatten.
- **Geen aangenomen relaties of partners.** Een naam die in een interne PDF wordt genoemd is geen automatische publicatie-klare partner. Verifieer in pre-flight.
- **Klant beschermen.** Pijnpunten en citaten die in een interne workshop zijn opgehaald (zoals "is toch wel veel geld voor een doek met palen") horen niet letterlijk op een publieke case. Parafraseer naar het patroon erachter zonder de klant kleiner te maken. We tonen het inzicht, niet de schaamte.
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
cta_persoon: stijn | anne | round-robin  # default: stijn voor branding, round-robin voor web. Alleen Stijn en Anne hebben cal.com.
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
1. **Vertaal de NL versie.** De EN is een trouwe vertaling, geen zelfstandige herschrijving. Volg de NL zinstructuur, de NL argumentvolgorde, de NL moduleopbouw. Voeg geen nieuwe frames of Engelse invullingen toe die niet in de NL staan.
2. **Native Brits Engels.** Niet Amerikaans. "Colour" niet "color", "organisation" niet "organization", "recognisable", "centre", "enquiries". Schrijf alsof een Britse native speaker het heeft geschreven.
3. **Pay-offs vertaal je van NL naar EN.** "Meer buiten" wordt "More outside". Andersom mag niet: introduceer geen Engelse termen die dan terugvertaald worden naar het NL.
4. **Strategische verschuiving (Module 5)** mag licht worden aangepast voor Engelse leesbaarheid, maar de betekenis blijft identiek aan de NL.
5. Genereer EN meta title + description (denk vanuit Engelse zoekwoorden, geen letterlijke vertaling).
6. Pas pad aan: `/en/project/<slug>` (slug identiek aan NL).
7. Voeg hreflang-instructie toe in frontmatter.

### Fase 5 — Live + indexing (verplicht, niet overslaan)

Een case die niet vindbaar is, is een case die niet bestaat. Deze fase is geen optie maar een vast onderdeel van het traject.

**Wanneer:** zodra het teamlid bevestigt dat de URL live staat op productie.

**Wat de skill doet:**

1. Lees `references/indexing-instructions.md` voor de details.
2. Check eerst of dependencies aanwezig zijn (zie hieronder). Mis er één, geef instructies en stop tot het teamlid het regelt.
3. Voer in volgorde uit:
   - **Sitemap re-submit** via Google Search Console API. Vereist: de `google-search-console` skill geïnstalleerd, geauthenticeerd voor `stuur.men`.
   - **URL Inspection** voor zowel `/project/[slug]` als `/en/project/[slug]`. Status per URL: Indexed / Crawled but not indexed / Discovered / niet gevonden.
   - **IndexNow POST** naar Bing/Yandex/Seznam/Naver. Key `15fcfa2c42f1072d219d8f709c7e6402`, keyLocation `https://stuur.men/15fcfa2c42f1072d219d8f709c7e6402.txt`. Vereist: key-file live op stuur.men root.
4. Rapporteer: status per URL, eventuele blockers (404, robots, noindex, ontbrekende sitemap-entry).
5. Plan een herinnering om over 2-4 weken via GSC te checken op impressies en posities.

**Niets overslaan, ook niet als het teamlid haast heeft.** Een live URL die niet ingediend wordt is een blinde vlek. De skill mag niet eindigen voor deze fase is afgerond of expliciet uitgesteld door het teamlid (bijvoorbeeld: "we publiceren morgen, dan doe ik indexing").

---

## Dependencies en secrets voor Fase 5

Deze fase werkt alleen als de volgende dingen geregeld zijn. Als één ontbreekt: skill geeft heldere instructies en wacht tot het is opgelost.

### Stuurmen gebruikt één gedeeld service account, via 1Password CLI

Het team werkt met één gedeeld Google service account dat toegang heeft tot de stuur.men Search Console property. De service account JSON staat in 1Password. De skill leest de credentials runtime via de 1Password CLI (`op`). De JSON komt nooit als bestand op disk.

**Voor het teamlid betekent dit:**
- Eenmalige setup van Homebrew + 1Password CLI + `op signin` (5-15 min)
- Daarna: skill werkt automatisch, geen handmatige actie per case
- Geen GSC-uitnodiging, geen losse JSON-bestanden, geen API-keys

**Eenmalige setup-script:** `scripts/setup-gsc.sh` in deze skill-folder. Voert alles uit en faalt netjes als iets misgaat. Zie `references/indexing-instructions.md` voor de uitleg.

### Dependencies-checklist (skill checkt zelf)

**1. 1Password CLI (`op`) aanwezig en ingelogd**

Skill draait `op vault list`. Faalt: verwijs naar setup-script.

**2. Toegang tot het GSC service account-item in 1Password**

Skill draait `op item get "GSC Service Account" --vault "Stuurmen"`. Faalt: vraag teamlid om toegang tot de Stuurmen-vault aan Stijn.

**3. `google-search-console` skill geïnstalleerd**

Check of `/google-search-console` beschikbaar is in de skill-lijst. Zo niet: verwijs naar plugin-marketplace.

**4. IndexNow-key gepubliceerd op stuur.men root**

Eenmalige developer-taak (Mike of Sven). Key: `15fcfa2c42f1072d219d8f709c7e6402`. Setup-details in `references/indexing-instructions.md`.
Skill checkt: `curl -s https://stuur.men/15fcfa2c42f1072d219d8f709c7e6402.txt`. Niet bereikbaar: blocker voor IndexNow, GSC-stappen kunnen wel door.

**5. URL is bereikbaar en geeft 200**

Voor submit kan, checkt skill met `curl`:
- 200-status (geen redirect)
- Niet geblokkeerd in `robots.txt`
- Aanwezig in `sitemap.xml`
- Hreflang-tags tussen NL en EN

---

## Wat als dependencies ontbreken?

Skill geeft een rij actie-items en blijft wachten:

```
Voordat we kunnen indexeren:

[ ] 1Password CLI setup (jij, eenmalig 5-15 min)
    bash scripts/setup-gsc.sh
    Vraag Mike of Sven als je vastloopt
[ ] google-search-console skill installeren (jij)
    /plugin install google-search-console@stuurmen
[ ] IndexNow-key op stuur.men root (Mike of Sven, eenmalig)
    Zie indexing-instructions.md, paragraaf IndexNow

Geef seintje als dit klaar staat, dan ronden we de indexing af.
```

Geen blocker voor de eerste twee fases (case schrijven, EN-vertaling). Wel een blocker voor live + indexing.

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
- **Module 10.5 (Brand statement) standaard aan** voor Type A. Na "Het patroon", voor de FAQ. Altijd: "Kill off the average™" en "Shift the perspective." Nooit vertalen, ook niet in de EN-versie.
- **Module 11 (FAQ Accordion) standaard aan** voor Type A. Optioneel voor Type B.
- **Beelden verdelen over de hele pagina.** Niet clusteren. Het eerste beeld komt pas na de pains slider, nooit direct na de Case Header. Richting de afsluiting meer beelden, motion of video. Tekst-zware modules vroeg, beeld-zwaar naar het einde.
- **Meta title + description** altijd genereren, beide talen.
- **Case-card content altijd genereren** (titel, klantnaam, categorie-tags, thumbnail-alt) zodat de case ook op de overzichtspagina past zonder hertypen.
- **Figma-componentnaam vermelden per module** in de output zodat porteren naar Storyblok 1-op-1 werkt.
- **Schema.org markup** snippet meeleveren voor de developer (`Article` + `FAQPage` als Accordion aanwezig).

---

## H1 — de strategische verschuiving, niet de merknaam

De H1 van een case is altijd de strategische verschuiving.

**Waarom:** een nieuwe of onbekende merknaam als H1 levert nul SEO-waarde en nul GEO-waarde. Zoekmachines en LLMs gebruiken de H1 als de centrale claim van de pagina. "Van schaduwdoek tot textielarchitect" is vindbaar, citeerbaar en vertelbaar. "Mobuline" is dat niet, zeker niet in de eerste jaren na een naamswijziging.

**Één-woord H1 werkt alleen** als de merknaam al eigenstandige betekenis heeft voor de doelgroep (Keukenhof, ASML, Philips). Dat is zelden het geval bij de Stuurmen-doelgroep van 20-80 FTE-bedrijven.

**Als de designer visuele impact wil met één woord:** gebruik de merknaam als eyebrow (klein, boven de hero), de strategische verschuiving als de echte H1. Zo staat de merknaam visueel prominent en doet de DOM het SEO-werk met de verschuiving.

---

## Meta title-format

Voor meta titles op stuur.men:

**Format:** `[klantnaam] · [strategische verschuiving of H1] · Stuurmen`

**Belangrijk:**
- Scheidingsteken is de **middle dot** `·` (U+00B7), géén pipe `|` en géén em dash
- Laatste deel is `Stuurmen` (kort), niet `Stuurmen Branding Agency`
- Klantnaam komt **eerst**, niet de verschuiving

**Voorbeelden:**
- `Mobuline · Van schaduwdoek tot textielarchitect · Stuurmen`
- `Haven · Innovatie gedreven door vertrouwen · Stuurmen`
- `CAM Bioceramics · De naam achter beter bot · Stuurmen`

**Lengte:** Google knipt rond 60 karakters. Zoek een verschuiving die onder de 35 karakters blijft, dan past het geheel.

**Niet te verwarren met email-onderwerpen:** voor emails geldt een ander format: `[onderwerp] | Stuurmen Branding Agency` (pipe + volledige naam). Zie `feedback_email_subjects` in memory.

---

## Persoon in CTA card

Alleen **Stijn** en **Anne** mogen in de CTA-card staan. Zij zijn de enige twee met cal.com-integratie en boekbare agenda. Andere teamleden komen nooit in het persoon-veld van de CTA, ook niet voor design- of dev-vragen.

**Drie opties per case:**
- `stijn` — strategische cases, founder-conversaties, langere trajecten (default fallback)
- `anne` — commercieel-eerste gesprekken, kwalificatie-calls, intake (Anne is commercial lead vanaf juni 2026)
- `round-robin` — gezamenlijke agenda (Stijn én Anne), cal.com kiest beschikbare slot

**Default per case-type:**
- **Branding-cases (Type A):** `stijn` (strategie-eigenaar, klant verwacht founder-gesprek)
- **Web-only cases (Type B):** `round-robin` (lichter gesprek, beide kunnen)

Bij twijfel: vraag het teamlid of overschrijf in de frontmatter.

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

## Output-locatie en bestandsnaam

**Schrijf de output naar een aparte map zodat bron en output gescheiden blijven.**

Pad-conventie: `output/cases/[klant-slug]/[klant-slug]-[taal]-[YYYYMMDD].md`

Voorbeelden:
- `output/cases/mobuline/mobuline-nl-20260507.md`
- `output/cases/mobuline/mobuline-en-20260512.md`
- `output/cases/bergopwaarts/bergopwaarts-nl-20260507.md`

**Waarom deze conventie:**
- `output/` map gescheiden van `context/` (bronmateriaal blijft onaangeroerd)
- Klant-slug is consistent (kebab-case, geen `:`, geen spaties, geen oude namen — bijvoorbeeld `mobuline` niet `mobuline:mantaroofs`)
- Datum in bestandsnaam zodat versies herkenbaar zijn zonder Git
- Taal expliciet in bestandsnaam, geen verwarring tussen NL en EN

**Eerste keer voor een klant:** maak de folder `output/cases/[klant-slug]/` aan als hij niet bestaat. Toon het pad aan de gebruiker zodat zij de output kunnen vinden.
