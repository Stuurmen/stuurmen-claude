# Component Spec — Case-pagina

Briefing voor Barend (digital design) en Mike/Sven (developers) over welke componenten op de case-pagina worden gebruikt en in welke volgorde. Gebaseerd op het Stuurmen design system in Figma file `rKfdC0nPDTzFRcWu28s6eS`.

Doel: één keer afstemmen wat een case-pagina uit het CMS samenstelt, zodat teamleden via de skill cases kunnen produceren die 1-op-1 in Storyblok passen zonder hertypen of redesignen.

---

## Goed nieuws: alle modules zijn dekbaar met bestaande componenten

Geen nieuwe componenten nodig. Wat we nu doen is een paar bestaande componenten op een nieuwe plek inzetten en een paar nieuwe content-velden definiëren.

---

## Volgorde van blokken op een branding-case (Type A)

| # | Module | Figma-component(en) | Verplicht? |
|---|---|---|---|
| 1 | Hero | `Case header` | Ja |
| 2 | Snelfeiten | `Rows` + `Tag container` | Ja |
| 3 | Het kantelpunt | `Text component` (Chapeau + Heading + Large paragraph) | Ja |
| 4 | Wat we zagen (pijnpunten) | `Pains slider` | Ja |
| 5 | De verschuiving | `Heading` Large + `Large paragraph` | Ja |
| 6 | De positionering | `Text component` | Ja |
| 7 | Hoe we dat zichtbaar maakten | Afwisseling `Text component` + `Normal image` + `Double image` | Ja |
| 8 | Wat het opleverde | `Benefits card` (grid 2-4) | Ja, als cijfers |
| 9 | Wat de klant zegt | `Quote` | Ja |
| 10 | Wat dit voor de markt betekent | `Text component` | Ja |
| 11 | FAQ | `Accordion` | Ja voor branding, optioneel voor web |
| 12 | Verwante cases + CTA | `Volgende cases` + `CTA card` Large | Ja |

## Volgorde voor web-only case (Type B)

Modules 3 en 4 worden samengevoegd, Module 4 wordt "De digitale verschuiving", Modules 6 en 10 vallen weg.

---

## Aandachtspunten per component

### Case header
**Wat aanpassen:** Het tagline-veld krijgt een nieuwe inhoudelijke definitie. Dit is **niet** de marketing-tagline van de klant ("Innovation driven by trust" stijl), maar de **strategische verschuiving** die Stuurmen heeft gemaakt ("Van schaduwdoek-leverancier naar textiel-architect").

In Figma laten zoals het is, alleen het content-voorbeeld in placeholder-state aanpassen zodat de bedoeling duidelijker wordt.

### Rows (voor Snelfeiten)
**Wat aanpassen:** uitbreiden met velden die Case header nu compact toont. Snelfeiten worden:
- Klant
- Branche
- Omvang (FTE of omzet)
- Regio
- Scope
- Jaar
- Looptijd

In Storyblok worden dit dynamische label/waarde-paren. In Figma is `Rows` al generiek genoeg, hoeft niets aan.

### Tag container
**Wat aanpassen:** een Tag-container direct onder Snelfeiten of in de Case header voor categorisering. Wordt ook gebruikt op de Case-overzichtspagina voor filtering.

Tags zijn niet vrij in te vullen, maar uit een gedefinieerde lijst:
- Type werk: Branding, Merknaam, Visuele identiteit, Website, Tone of voice, Communicatie, Employer brand, Sales tools
- Branche: Industrie, B2B, B2C, Services, Maatwerk, Productie, Architectuur, Bouw, Health, Tech
- Scope: Brand Strategy, Brand Design, Brand in practice
- Andere: Internationaal, Familiebedrijf, Founder-led

### Pains slider
**Wat checken:** ondersteunt het component al een variabel aantal cards (3-5)? En de `cta_label` ("Lees het pijnpunt") opent dat een lightbox of in-page expansion? Dat moet helder zijn voor content-mensen.

Als de klik nu naar een diepere pagina gaat, suggesteer ik in-page expand. Een case-pagina splitsen in extra subpagina's per pijnpunt is overkill.

### Benefits card (voor Wat het opleverde)
**Wat aanpassen:** layout-variant voor "in grid" toevoegen als die er nog niet is. Doel: 3-4 Benefits cards naast elkaar in één rij of 2x2 grid.

Content per kaart:
- `titel` (groot, vaak een cijfer of korte claim)
- `body` (1-2 regels uitleg)

Geen icoon nodig.

### Quote
**Wat aanpassen:** controleer dat het standaard variant is met portretfoto klein, naam, rol/bedrijf. Zie eerder afgekeurde Testimonial-card variant: te zwaar voor case-flow. Quote = standaard, Testimonial = uitzondering.

### Accordion (voor FAQ)
**Wat aanpassen:** geen specifieke aanpassing nodig. Component is al klaar. Wel: zorg dat schema.org `FAQPage` markup wordt geïnjecteerd in de HTML wanneer dit blok aanwezig is. Dat is een developer-taak voor SEO/GEO.

### CTA card
**Wat aanpassen:** nu standaard "Plan een call met Nick" hardcoded in design. Maak het persoon-veld dynamisch:
- Branding-cases: standaard Stijn (founder, strategie-eigenaar)
- Web-only cases: standaard Barend (digital owner)
- Optioneel: per case overschrijven

### Case card (voor overzichtspagina)
**Wat aanpassen:** zorg dat de fields uit de skill-output (card_titel, card_klantnaam, card_categorie, card_thumbnail) 1-op-1 in het Case card component passen.

---

## Storyblok schema (voorlopig advies)

In Storyblok wordt de case-pagina een `Page` met een `body` van blocks. Elke block heeft een component-type dat overeenkomt met de Figma-naamgeving. Suggestie:

```yaml
case_page:
  fields:
    klant_naam: string
    slug: string
    taal: select [nl, en]
    meta_title: string
    meta_description: string
    og_image: asset
    body: blocks  # array of allowed component types

allowed_blocks_in_body:
  - case_header
  - rows
  - tag_container
  - text_component
  - pains_slider
  - heading_large_with_paragraph
  - image_normal
  - image_double
  - benefits_grid
  - quote
  - accordion
  - cta_card
  - related_cases
```

Voordeel: Skill kan exact deze JSON-structuur produceren als hij weet welke component-types Storyblok accepteert. Als jij of Mike het schema vastlegt, kan ik in Phase 2 de auto-push bouwen.

---

## Voor de Case-overzichtspagina

**Figma-component:** `Cases Row` met daarin `Case card` instances in Small/Medium/Large.

Filtering op tags is een nice-to-have. SEO-overweging: voeg een korte intro-tekst toe boven de overzichtspagina ("Cases van bedrijven die kozen voor scherpere positionering en zichtbaar leiderschap") zodat de pagina ook organisch vindbaar is op intent-zoekwoorden.

---

## Dependencies en wie doet wat

**Barend** (digital design):
- Bekijk de mapping en de aandachtspunten per component
- Pas Case card variant aan zodat dynamisch persoon (Stijn/Barend) erin past
- Zorg dat Pains slider tussen 3-5 cards aankan
- Adviseer over Benefits card grid-layout

**Mike of Sven** (development):
- Implementeer schema.org markup voor `Article` (altijd) en `FAQPage` (bij Accordion)
- Maak hreflang tussen NL en EN versies werken
- Voeg URL toe aan sitemap.xml automatisch bij publicatie
- Implementeer IndexNow-key op stuur.men root (eenmalig)
- Definieer Storyblok schema voor case-page met de blocks hierboven

**Stijn / Marysa**:
- Eindredactie van content per case
- Klantquote-interview voeren (5 vragen uit playbook)
- Akkoord op publicatie

**Teamlid die case start** (iedereen):
- Bronmateriaal verzamelen in `context/cases/[klant]/`
- `/stuurmen-case [klant]` runnen
- Output reviewen, gap-list invullen
- Eindredactie aanvragen
- Live publicatie + indexing

---

## Wat ontbreekt nog (open vragen)

- **Pains slider interactie:** in-page expand of doorklik naar subpagina?
- **Tag-taxonomie:** wie beslist over de officiële lijst van tags? Voorstel hierboven, maar moet vastgesteld
- **CTA card persoon-keuze:** echt dynamisch per case of voorlopig hardcoded?
- **Benefits card grid:** bestaat dat al of moet Barend dat tekenen?

Beantwoorden voor de eerste case live gaat.
