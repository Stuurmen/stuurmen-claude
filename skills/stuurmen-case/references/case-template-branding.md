# Case Template — Branding (Type A)

Voor cases waarin Stuurmen merkstrategie + merkontwerp heeft geleverd, met of zonder website.

Volg de modules in deze volgorde. Sla niets over. Vul je niet in, dan komt het in de "wat ontbreekt"-lijst.

Elke module is gemapt op een Figma-component uit het Stuurmen design system (file `rKfdC0nPDTzFRcWu28s6eS`). Output van de skill markeert per module welk component gebruikt moet worden, zodat overzetten naar Storyblok (later) of handmatig bouwen 1-op-1 werkt.

---

## Module 1 — Hero

**Figma-component:** `Case header`

**Doel:** lezer ziet binnen 3 seconden om welk type bedrijf het gaat en wat de strategische verschuiving was.

**Velden:**
- `eyebrow` — branche + scope, kort. Bijvoorbeeld: "Maatwerk overkappingen, Branding & Website" of "Bioceramics, Brand Strategy"
- `titel` — de strategische verschuiving in één zin. Niet de tagline van de klant. De verschuiving die Stuurmen heeft gemaakt. Bijvoorbeeld: "Van schaduwdoek-leverancier naar textiel-architect"
- `subzin` — één zin die uitlegt waarom die verschuiving nodig was, of wat het oplevert
- `hero_beeld` — beeld dat het nieuwe merk laat zien (geen logo)

**Wat NIET:**
- Geen poëtische klant-tagline ("Ervaar de luxe van textiel")
- Geen vage merk-claim ("Brand Strategy")
- Geen "Project header image" als alt-tekst

---

## Module 2 — Snelfeiten

**Figma-component:** `Rows` (label/waarde-rijen) + optioneel `Tag container` voor branche-tags

**Doel:** ICP-bezoeker herkent zichzelf. SEO en GEO krijgen citeerbare feiten.

**Verplichte velden:**
- `klant` — bedrijfsnaam
- `branche` — concreet, bijvoorbeeld "Buitenleven en maatwerk overkappingen", niet "B2B"
- `regio` — waar zit de klant
- `scope` — letterlijk wat Stuurmen heeft geleverd. Lijst, geen zinnen
- `looptijd` — periode van het traject (jaartallen of "2025-2026")

**Optionele velden (alleen opnemen als ze iets toevoegen):**
- `omvang` (FTE of omzet) — laat weg bij kleine teams (<5) of als het de klant kleiner doet voelen dan zijn werk
- `tags` (voor `Tag container`) — 3-6 tags voor categorisering en filtering

**Wat NIET in snelfeiten:**
- Geen FTE als het bedrag de claim van de case ondergraaft (3 mensen die werken op niveau van 30 mensen, dan vermeld je geen FTE)
- Geen jaar-getallen die suggereren dat het traject korter was dan het was
- Geen scope-onderdelen die niet daadwerkelijk geleverd zijn

**Voorbeeld (Mobuline):**
```
Klant: Mobuline (voorheen Manta Roofs)
Branche: Maatwerk textielarchitectuur
Regio: Nederland
Scope: Merkstrategie, visuele identiteit, website, configurator-strategie
Looptijd: 2025-2026
Tags: Branding, Visuele identiteit, Website, Buitenleven
```

---

## Module 3 — Het kantelpunt

**Figma-component:** `Text component` (Chapeau "De situatie" + `Heading` Medium + `Large paragraph`)

**Doel:** lezer ziet welk moment dit bedrijf rijp maakte voor merkwerk. Trigger-herkenning bij ICP.

**Vorm:** 80-120 woorden prose. Geen bullets.

**Wat erin:**
- Wat speelde er in het bedrijf op dat moment? (Nieuwe propositie, overname, nieuwe Head of Marketing, expansie, etc.)
- Wat zat er aan groei in het verschiet, en waarom kwam het merk daar in de weg te staan?
- Eventueel: wat had de klant zelf al geprobeerd?

**Bron in materiaal:** "Doelstellingen 3-5 jaar", "Hopes & Fears", project-intake, eerste workshop.

**Voorbeeld-opening voor Mobuline:**
> Mobuline (toen nog Manta Roofs) zat op een kantelpunt. Het product werkte: textiel-overkappingen tot 120 m² aan één stuk, ontworpen met software uit de zeilbouw, opgezet in tien minuten. Joris en zijn team wilden uit de prijsdiscussie en partners in Duitsland, Frankrijk en België aansluiten. Maar het merk vertelde een ander verhaal dan het product...

---

## Module 4 — Wat we zagen

**Figma-component:** `Pains slider` (chapeau-zin + slider-cards)

**Doel:** lezer voelt de spanning tussen wat het bedrijf is en hoe de markt het ziet. Dit is het "shift the perspective"-moment.

**Velden:**
- `inleidende_zin` — één zin context boven de slider
- `slides[]` — 3-5 cards. Elke card heeft:
  - `kop` — het pijnpunt in publicatie-toon (geen letterlijke pijn-quote van de klant zelf)
  - `cta_label` — meestal "Lees het pijnpunt"
  - `body` — 60-100 woorden uitleg met de werkelijkheid eronder

### Belangrijk: parafraseren, niet citeren

In de Documentatie staan vaak letterlijke uitspraken uit workshops, externe interviews of klantfeedback. Bijvoorbeeld: "is toch wel veel geld voor een doek met palen", of "ohja, ook veel op festivals toch?". Deze zinnen zijn waardevol als bron voor patronen, maar **horen niet letterlijk op een publieke case**.

**Reden:** een klant herkent zichzelf op een publieke pagina anders dan in een interne workshop. Letterlijke uitspraken die in een veilige werksetting terecht waren, kunnen op een case-pagina afbreuk doen aan de relatie en aan het merk van de klant zelf. Stuurmen toont het inzicht, niet de schaamte.

**Hoe wel:**
- Beschrijf het patroon zonder de klant te citeren ("De markt zag het bedrijf als leverancier van losse onderdelen, niet als de specialist die het was")
- Generaliseer waar mogelijk ("Sales-gesprekken begonnen vaak bij prijs in plaats van bij waarde")
- Gebruik categorieën in plaats van scenes ("Verwarring met aangrenzende productgroepen", in plaats van een specifieke quote)

**Wel direct quoten:** alleen als de quote afkomstig is van een algemeen marktpatroon, niet van een specifieke klant of partner van deze klant. En liever helemaal niet: parafrasering is bijna altijd sterker.

**Format per card (voorbeeld zonder letterlijke quotes):**
> **Kop:** Verward met aangrenzende productgroepen
>
> **Body:** De markt schaalde het bedrijf onbedoeld in bij categorieën waar het niet thuishoorde — schaduwdoekleveranciers, festivaltent-verhuur, generieke buitenproducten. Daardoor begon elk gesprek bij prijs in plaats van bij positie. Het werkelijke product, ontworpen met software uit de zeilbouw, in-house geproduceerd en getest op weerstanden, droeg een ander prijspunt dat zonder context niet uit te leggen viel.

**Bron in materiaal:** "Klanten en partners zien ons als..." en "Maar in werkelijkheid zijn we..." in de Documentatie. Externe interviews, klantfeedback.

---

## Module 5 — De verschuiving

**Figma-component:** `Heading` Large (standalone, groot) + optioneel `Large paragraph` voor context

**Doel:** kern van de case. Eén zin die alles draagt.

**Vorm:** één zin, groot. Plus 2-3 zinnen context daaronder.

**Format:** "Van [oude perceptie] naar [nieuwe positie]."

**Voorbeelden:**
- Mobuline: "Van schaduwdoek-leverancier naar textiel-architect die buitenruimte transformeert."
- CAM Bioceramics: "Van anonieme grondstof-leverancier naar de naam achter beter bot."
- Bergopwaarts: "Van woningcorporatie naar bouwer van betaalbaar wonen voor een nieuwe generatie."

Daaronder 2-3 zinnen die de verschuiving onderbouwen. Wat verandert er door deze nieuwe positie? Welke ruimte ontstaat er?

**Bron:** "Strategie in één zin" in de Documentatie. Brand Concept Presentatie hoofdslide.

---

## Module 6 — De positionering

**Figma-component:** `Text component` (Chapeau + `Heading` Medium + `Large paragraph`)

**Doel:** het narratief dat onder de verschuiving zit. Wat het merk nu claimt en waar het op gebouwd is.

**Vorm:** 2-4 alinea's prose. Geen bullets.

**Wat erin:**
- De positionering zelf (wat claimt het merk in de markt)
- Het narratief: waarom deze klant dat mág claimen (bewijslast: ambacht, software, samenwerking, track record)
- Wat dit voor de klant betekent intern: welke beslissingen worden makkelijker, wat valt af

**Bron:** Brand Concept Presentatie, hoofdstukken positionering en narratief.

---

## Module 7 — Hoe we dat zichtbaar maakten

**Figma-componenten:** afwisseling van `Text component`, `Normal image`, `Double image`

**Doel:** laat zien hoe strategie zich vertaalde naar uitvoering. Hier mag design ademen, maar elke designkeuze hangt aan een strategische redenering.

**Sub-modules (kies welke van toepassing zijn, in deze volgorde):**

### 7a — Merknaam (alleen als Stuurmen die heeft gemaakt of veranderd)
`Text component` met Chapeau "De naam". Wat de naam is, waarom hij is gekozen, wat hij doet voor de positionering. Eventueel `Normal image` met de naam in beeld.

### 7b — Brand hook + tone of voice
`Text component` met Chapeau "De stem". De pay-off, het centrale idee, hoe het merk klinkt. Eén voorbeeld-zin als citaat-blok.

### 7c — Visuele identiteit
`Text component` met Chapeau "Het beeld" + `Normal image` of `Double image` met logo, kleur, typografie, beeldtaal. Korte tekst per element + visueel. Niet "we kozen aardetinten omdat ze warm zijn" maar "aardetinten omdat de overkappingen het buiten naar binnen halen".

### 7d — Website (als van toepassing)
`Text component` met Chapeau "De website" + screenshots. Wat doet de website strategisch? Niet "we bouwden een mooie site". Wel: "de site verkoopt niet meer een product maar een transformatie van een terras".

### 7e — Communicatie en roll-out
`Text component` + image-blokken met sales tools, drukwerk, social, lancering.

**Vorm:** elke sub-module krijgt 2-4 zinnen tekst + 1-3 beelden. Geen losse mood-boards zonder uitleg.

---

## Module 7.5 — Het werk

**Figma-componenten:** `Normal image`, `Double image`, optioneel `Caption`. Bij grote schaal-projecten: meerdere `Double image`-blokken na elkaar.

**Doel:** Stuurmen maakt uiteindelijk gewoon vette shit. Deze module geeft het visuele resultaat eigen ademruimte. Niet als bewijs onder de strategie, maar als eigen waardepunt. De bezoeker ziet wat er ís gemaakt en herkent het vakmanschap. Voor designers en developers in het ICP is dit vaak de bevestiging dat de strategische ambitie niet eindigt in een PowerPoint.

**Vorm:** minimaal **8 beelden**, vaker meer. Mix van:
- Productfotografie of lifestyle-fotografie van het uiteindelijke werk in context
- Drukwerk-mockups of foto's van tastbaar materiaal
- Website-screenshots (desktop en mobile, naast elkaar of als doorscroll)
- Configurator/tool screenshots
- Motion stills, social-uitingen of campagne-beelden
- Brand book pagina's, kleurpalet in toepassing, typografie in praktijk

**Layout-suggestie:**
- Open met één groot beeld dat het project als geheel laat zien (`Normal image` full-width)
- Daarna afwisseling tussen `Double image` (twee gelijkwaardige beelden naast elkaar) en `Normal image`
- Een korte `Caption` (1 regel) onder een beeld of cluster waar context nodig is
- Geen verplichte uitleg per beeld. Het werk spreekt grotendeels voor zichzelf.

**Wat NIET:**
- Geen renders of mock-ups die niet representatief zijn voor het echte werk
- Geen herhaling van beelden uit Module 7 (visuele identiteit) — die zijn klein, deze zijn groot en in toepassing
- Geen design-system pagina's uit Figma in plaats van de uiteindelijke uitvoering
- Geen logos op grijze achtergronden (saai en niet-representatief)

**Bron voor beelden:** vraag in pre-flight uit. Als beelden ontbreken op het moment van schrijven, markeer in gap-list met expliciete vraag naar designteam (Barend voor digital, Ruben/Nick voor brand identity en drukwerk).

---

## Module 8 — Wat het opleverde

**Figma-component:** `Benefits card` in grid (2-4 naast elkaar). Bij zachtere observaties zonder cijfers: `Rows`.

**Doel:** bewijslast. Wat is er meetbaar of voelbaar veranderd na de oplevering?

**Vorm:** elke `Benefits card` heeft:
- `titel` — het cijfer of de claim ("x2 aanvragen", "+€7K avg deal", "Prijsdiscussies verdwenen")
- `body` — 1-2 regels uitleg ("Spontane internationale leads van 0 naar 12 per maand binnen drie maanden")

**Categorieën om uit te kiezen:**
- **Commercie:** aanvragen, conversie, ticket-grootte, prijsdiscussies, deals gewonnen
- **Talent:** nieuwe hires, kwaliteit van sollicitaties, retention
- **Intern:** alignment, hoe het team het bedrijf nu beschrijft, snelheid van besluitvorming
- **Markt:** PR, awards, partner-aanvragen, internationale interesse
- **Operations:** processen die nu wel of niet doorgaan

**Voorbeelden Benefits card:**

```
Titel: x2 aanvragen
Body: In de eerste drie maanden na lancering verdubbelde het aantal binnenkomende offerte-aanvragen.
```
```
Titel: 0 → 12 internationaal
Body: Spontane leads uit Duitsland en België waar voorheen alleen advertising-traffic kwam.
```
```
Titel: 1 verhaal intern
Body: Sales en operations vertellen voor het eerst dezelfde positionering, in plaats van zes verschillende.
```

**Eerlijk zijn:** als er geen cijfers zijn, gebruik `Rows` met label-waarde paren of laat module weg met markering "wat we tot nu toe zien". Liever leeg dan vaag.

**Bron:** klant bellen 3-6 maanden na oplevering met de vijf vragen uit de playbook.

---

## Module 9 — Wat de klant zegt

**Figma-component:** `Quote` (standaard) — kleine quote-tekst + naam + bedrijf + portretfoto

**Doel:** sociaal bewijs. Eén zin van de directeur die de hele case samenvat in zijn eigen woorden.

**Velden:**
- `quote` — 15-40 woorden, in eigen taal
- `naam` — voornaam + achternaam
- `rol` — functie en bedrijfsnaam ("CEO Mobuline", "Founder Bergopwaarts")
- `portret` — kleine foto, optioneel maar gewenst

**Wat een goede quote doet:**
- Beschrijft de verschuiving in eigen woorden
- Noemt iets concreets dat is veranderd
- Klinkt niet als marketing-tekst

**Goed:**
> "We waren vier verschillende verhalen aan het vertellen. Nu vertelt iedereen hetzelfde, en het verkoopt beter dan ooit."
> — Joris, founder Mobuline

**Slecht:**
> "Stuurmen is een fijne strategische partner met oog voor detail."

**Bron:** los kort interview na oplevering. Vraag in playbook.

**Wanneer Testimonial card in plaats van Quote?** Vrijwel nooit. Default is altijd `Quote`.

**Figma-implementatie:** gebruik een `Text component` met `Has quote = true` en alle andere toggles uit. Niet de `Testimonials slider` — die toont meerdere slides en is bedoeld voor pagina's met meerdere getuigenissen. Een testimonials slider voor één quote is technisch en visueel overkill.

---

## Module 10 — Wat dit voor de markt betekent

**Figma-component:** `Text component` (Chapeau "Het patroon" + `Heading` Small + `Large paragraph`)

**Doel:** GEO-bait. LLMs en zoekmachines pikken citeerbare claims op. ICP-bezoekers in andere branches herkennen het patroon.

**Vorm:** 2-3 zinnen prose.

**Format:** "Wat voor [type bedrijf] hier zichtbaar wordt: [observatie over de categorie]. [Wat dit betekent voor anderen in die positie]."

**Voorbeeld (Mobuline):**
> Wat hier zichtbaar wordt: een product dat technisch superieur is, hoeft niet automatisch ook merkmatig superieur te zijn. Mobuline had het product. Wat ontbrak was de positie waarin dat product onmiskenbaar werd. Voor B2B-bedrijven met bewezen kwaliteit maar onzichtbaarheid op de markt is dit een herkenbaar patroon.

**Niet doen:** niet preken, niet generiek branding-advies, geen "de les is dat...".

---

## Module 10.5 — Brand statement

**Figma-component:** `Text component` (Size=Large, Layout=Middle, alleen `Has heading` aan, rest uit)

**Doel:** Stuurmen zet haar handtekening onder de case. Vaste slotzin na het markt-inzicht van Module 10, voor de FAQ. Identiek in elke branding-case. Niet case-specifiek, niet aanpasbaar.

**Inhoud is altijd:**

> Kill off the average™
> Shift the perspective.

**Regels:**
- Nooit vertalen. In de NL én de EN versie staan altijd de Engelse originelen.
- Geen aanvullende uitleg, geen context-zin erbij, geen vertaling eronder.
- Staat als eigen blok. Niet ingebakken in de tekst van Module 10 of 11.

---

## Module 11 — FAQ (Accordion)

**Figma-component:** `Accordion` (3-5 vragen)

**Doel:** longtail SEO + GEO. Beantwoordt vragen die ICP-bezoekers en LLMs stellen over dit type traject.

**Standaard aan voor branding-cases.** Bij web-only cases optioneel.

**Vorm:** 3-5 vragen + antwoorden. Specifiek voor deze case, niet generiek copy-paste.

**Voorbeeldvragen om uit te kiezen:**
- "Voor welk type bedrijf is een traject zoals dit geschikt?"
- "Hoe lang duurde dit traject?"
- "Wat is het verschil met een nieuwe huisstijl?"
- "Wat hebben jullie van [klant] nodig om te starten?"
- "Werkt dit ook als ons merk wel een logo heeft maar geen verhaal?"
- "Is dit een eenmalig project of een doorlopende samenwerking?"
- "Wat als wij geen merkstrategie hebben maar wel willen herbranden?"

**Antwoorden:**
- 60-100 woorden per antwoord
- Specifiek, niet vaag
- Citeerbaar (één claim per zin werkt het beste)
- Stuurmen-toon (je/jij, geen filler)

**Bron:** Sales-team kan vertellen welke vragen daadwerkelijk in gesprekken komen rond dit type case.

---

## Module 12 — Verwante cases + CTA

**Figma-componenten:** `Volgende cases` block + `CTA card` (Large)

**Onderdelen:**
- `services_geleverd` — heldere bullet-lijst van Stuurmen-onderdelen die in deze case zaten. Mapt naar Stuurmen's hoofdfasen (Brand Strategy / Brand Design / Brand in practice). Linkbaar.
- `verwante_cases` — 2 case-cards. Liefst zelfde branche of zelfde type verschuiving.
- `cta` — `CTA card` met "Plan een call". Alleen Stijn of Anne (cal.com-integratie). Default voor branding: Stijn. Round-robin (Stijn + Anne) als beide kunnen.

---

## Output: ook content voor de case-overzichtspagina

**Figma-component:** `Case card` (Small/Medium/Large variant)

Naast de case-pagina zelf, levert de skill ook content voor de case-tegel op de overzichtspagina:

**Velden:**
- `card_titel` — kortere variant van de hero-titel, max 50 karakters. Bijvoorbeeld: "Van schaduwdoek tot textiel-architect"
- `card_klantnaam` — bedrijfsnaam, exact zoals op de pagina
- `card_categorie` — branche-tags, max 3 ("Branding", "Website", "Buitenleven")
- `card_thumbnail_alt` — beschrijvende alt-tekst voor het thumbnail-beeld
- `card_thumbnail` — beeld-suggestie of placeholder

Zo wordt de case ook zichtbaar in `Cases Row` en op de overzichtspagina, met dezelfde strategische framing als de pagina zelf.

---

## Meta — voor `<head>`

Niet zichtbaar op de pagina, wel cruciaal voor SEO en GEO.

**Velden:**
- `meta_title` — max 60 karakters. Format: `[klantnaam] · [strategische verschuiving] · Stuurmen`. Scheidingsteken is de middle dot `·` (U+00B7), nooit een pipe.
- `meta_description` — 140-160 karakters. Eén zin die de verschuiving samenvat plus het type bedrijf. Moet een mens triggeren te klikken én een LLM een goede samenvatting geven.
- `og_title` / `og_description` — meestal gelijk aan meta, soms scherper voor social
- `og_image` — hero-beeld
- `canonical` — de URL zelf
- `hreflang` — koppeling tussen NL en EN versie

**Voorbeeld (Mobuline NL):**
- meta_title: `Mobuline · Van schaduwdoek tot textielarchitect · Stuurmen`
- meta_description: "Hoe Mobuline (voorheen Manta Roofs) zich herpositioneerde van anonieme leverancier naar textielarchitect. Branding, naam, website door Stuurmen."

---

## Schema.org markup (voor de website-implementatie)

Adviseer de developer om de pagina te markeren als `Article` of `CreativeWork` met `about` → de klant als `Organization`. Dit helpt zowel SEO als GEO.

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "<titel>",
  "description": "<meta_description>",
  "author": { "@type": "Organization", "name": "Stuurmen" },
  "about": {
    "@type": "Organization",
    "name": "<klantnaam>",
    "industry": "<branche>"
  },
  "datePublished": "<datum>",
  "image": "<hero_beeld>"
}
```

Bij FAQ Accordion: voeg `FAQPage` schema toe met de Q&A's. Verhoogt kans op rich result en LLM-citatie.

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "<vraag>",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "<antwoord>"
      }
    }
  ]
}
```
