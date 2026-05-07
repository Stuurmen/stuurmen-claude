# Case Template — Web (Type B)

Voor cases waarin Stuurmen alleen een website heeft geleverd, zonder volledige merkstrategie ervoor. Voorbeeld: ZZDP.

Kortere variant met dezelfde DNA. 7 verplichte modules + optionele FAQ. De kern blijft: strategie-led, geen losse design-modules.

Gebruikt dezelfde Figma-componenten als Type A (file `rKfdC0nPDTzFRcWu28s6eS`).

---

## Module 1 — Hero

**Figma-component:** `Case header`

Zelfde als Type A, maar de "verschuiving" zit in het digitale verhaal.

**Velden:**
- `eyebrow` — "Architectuur, Website" of "[Branche], Website"
- `titel` — wat de site nu doet wat hij eerst niet deed. Bijvoorbeeld: "Een website die het portfolio laat doen wat de presentaties al deden"
- `subzin` — wat het doel was van de site
- `hero_beeld` — screenshot of mockup van de site

---

## Module 2 — Snelfeiten

**Figma-component:** `Rows` + optioneel `Tag container`

```
Klant: ZZDP
Branche: Architectuur
Omvang: ~30 FTE
Regio: Amsterdam
Scope: Web strategie, ontwerp, ontwikkeling
Jaar: 2024
Looptijd: 8 weken
Stack: Storyblok, Next.js (alleen vermelden als relevant voor SEO)
Tags: Website, Architectuur, Internationaal
```

---

## Module 3 — Wat speelde er

**Figma-component:** `Text component` (Chapeau "De situatie" + `Heading` Medium + `Large paragraph`)

Combineert kantelpunt + spanning uit Type A in één blok. 60-100 woorden.

**Wat erin:**
- Wat lukte er niet meer met de oude site?
- Wat had de klant nodig dat een nieuwe site moest oplossen?
- Eventueel: hoe zag de markt het bedrijf via de oude site?

**Voorbeeld-opening:**
> Het werk van ZZDP was internationaal en herkenbaar. De website was Nederlands en algemeen. Internationale klanten landden op een site die het bureau kleiner liet voelen dan het was...

---

## Module 4 — De digitale verschuiving

**Figma-component:** `Heading` Large + `Large paragraph`

Het hart van de case, korter dan Type A.

**Vorm:** één regel + één alinea.

**Format:** "Van [oude site-functie] naar [nieuwe site-functie]."

**Voorbeeld:**
> "Van portfolio-archief naar internationale visitekaart."
>
> De nieuwe site zet projecten neer als verhalen, niet als plaatjes. Bezoekers begrijpen binnen één scroll wat het bureau onderscheidt en welk type opdracht het zoekt. De internationale lezer is leidend in de architectuur van de site, niet de Nederlandse archiefgebruiker.

---

## Module 5 — Hoe we dat hebben gebouwd

**Figma-componenten:** afwisseling van `Text component`, `Normal image`, `Double image`

Vergelijkbaar met Module 7 uit Type A, maar puur digitaal.

**Sub-modules (kies wat van toepassing is):**
- Sitemap-keuzes (welke prioriteit voor welke pagina)
- Content-architectuur
- Visuele richting van de site (typografie, kleur, beeld)
- Interactie (animaties, configurator, filtering)
- Technische stack en waarom

Per sub-module: 2-4 zinnen + screenshots/visuals.

---

## Module 6 — Wat het opleverde

**Figma-component:** `Benefits card` in grid (2-4 naast elkaar) of `Rows` voor zachtere observaties

Zelfde als Type A maar met digitale metrics als prioriteit.

**Categorieën:**
- **Performance:** Core Web Vitals, laadtijd, bounce rate
- **Conversie:** aanvragen, contactformulier-invullingen, scroll-depth
- **SEO:** rankings op kernzoekwoorden, organisch verkeer
- **Internationaal:** verkeer per land, indexering in andere talen
- **Zacht:** wat zegt het sales-team over hoe leads binnenkomen

**Voorbeeld Benefits card:**
```
Titel: 2x internationaal
Body: Internationale aanvragen verdubbeld in eerste 6 maanden, bounce rate van Engelstalige bezoekers van 68% naar 31%.
```

---

## Module 7 — Quote + services + CTA

**Figma-componenten:** `Quote` + `Volgende cases` + `CTA card`

Eén compacter blok aan het einde:
- Klantquote (`Quote` component, zelfde regels als Type A Module 9)
- Geleverde diensten (web strategie, ontwerp, ontwikkeling, eventueel onderhoud)
- 2 verwante cases via `Volgende cases`
- `CTA card` — voor web-only cases: "Plan een call met Barend" (digital owner)

---

## Module 8 — FAQ (optioneel)

**Figma-component:** `Accordion` (3-5 vragen)

Voor web-only cases optioneel. Aanzetten als de case veel sales-vragen oproept of als er veel zoekvolume zit op het type vraag.

Zie Module 11 in `case-template-branding.md` voor regels en voorbeelden. Aanpassen op web-context (bijvoorbeeld: "Wat als wij al een Storyblok-site hebben?").

---

## Output: Case-card content

**Figma-component:** `Case card`

```
card_titel: <kortere variant van de hero-titel, max 50 chars>
card_klantnaam: <bedrijfsnaam>
card_categorie: <max 3 tags>
card_thumbnail_alt: <beschrijvende alt-tekst>
card_thumbnail: <beeld of placeholder>
```

---

## Meta + schema.org

Identiek aan Type A. Zie `case-template-branding.md` voor formats.

---

## Wanneer Type B en niet Type A?

Gebruik Type B als:
- Stuurmen geen merkstrategie heeft geleverd
- De positionering al stond en de website implementeerde die
- Looptijd korter dan 8 weken
- Geen workshops, geen safaridag, geen brand book als output

Twijfelgeval? Type A. Liever te veel strategisch frame dan te weinig.
