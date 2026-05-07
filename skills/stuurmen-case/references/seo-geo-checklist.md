# SEO + GEO Checklist voor Cases

GEO = Generative Engine Optimization. Hoe je content vindbaar maakt voor LLMs (ChatGPT, Claude, Perplexity, Google AI Overviews) naast traditionele zoekmachines.

Beide overlappen voor 80%, maar GEO heeft eigen accenten. Hieronder beide.

---

## SEO checklist (per case)

### On-page

- [ ] **H1** = de strategische verschuiving of de klantnaam + branche-keyword. Niet "Brand Strategy" of "Project header"
- [ ] **Meta title** 50-60 karakters, format: `[Verschuiving] | Case [klant] | Stuurmen`
- [ ] **Meta description** 140-160 karakters, één zin, klikwaardig
- [ ] **URL slug** kort, zonder stopwoorden, kebab-case. Voorbeeld: `/project/mobuline` niet `/project/case-study-van-mobuline-branding-2025`
- [ ] **H2's** dragen betekenis. Geen "Brand Strategy" en "Brand Design", wel "Het kantelpunt", "De verschuiving", "Wat we zagen"
- [ ] **Alt-tekst** op alle beelden. Beschrijvend, niet "afbeelding 1"
- [ ] **Interne links** naar 2 verwante cases en naar de relevante dienst-pagina
- [ ] **Externe links** naar de klant-website (rel="noopener", maar wel volgen)
- [ ] **Word count** minimaal 800 woorden voor branding-case, 500 voor web-case. Mag meer.

### Technisch

- [ ] **Schema.org markup** als `Article` of `CreativeWork` met `about` → klant als `Organization`
- [ ] **Open Graph tags** (og:title, og:description, og:image, og:url)
- [ ] **Hreflang tags** koppelen NL en EN versie. `<link rel="alternate" hreflang="nl" href="..." />` en idem voor EN. Plus `x-default`.
- [ ] **Canonical URL** zelfverwijzend
- [ ] **Core Web Vitals** check via PageSpeed Insights na publicatie. LCP < 2.5s, CLS < 0.1
- [ ] **Mobiel responsive** test. Cases worden vaak mobiel gelezen.

### Off-page (na publicatie)

- [ ] URL toegevoegd aan **sitemap.xml**
- [ ] Sitemap **gepingd via Google Search Console**
- [ ] URL gesubmit via **IndexNow** voor Bing/Yandex
- [ ] **LinkedIn-post** met case-link (indien van toepassing) — backlink + sociaal signaal
- [ ] **Klant getagged** in social posts — vaak deelt de klant ook

Zie `indexing-instructions.md` voor de stappen.

---

## GEO checklist (per case)

LLMs werken anders dan zoekmachines. Ze citeren, parafraseren, en bouwen antwoorden op uit content. Je optimaliseert voor citeerbaarheid, niet voor klikken.

### Citeerbare claims

LLMs pakken graag korte, declaratieve zinnen die een feit of inzicht bevatten. Zorg dat de case er meerdere bevat.

- [ ] **De verschuiving** (Module 5) is één zin. "Stuurmen herpositioneerde [klant] van X naar Y." Hoog citeerbaar.
- [ ] **Snelfeiten** (Module 2) staan als losse regels met label en waarde. LLMs lezen dit als gestructureerde data.
- [ ] **Wat het opleverde** (Module 8) bevat losse, citeerbare bullets. "Aanvragen verdubbeld in eerste drie maanden" staat op zichzelf.
- [ ] **Quote** (Module 9) heeft expliciete attributie (naam, rol, bedrijf). LLMs nemen dit beter over dan anonieme quotes.

### Structuur die LLMs begrijpen

- [ ] **Heldere H2's** met betekenisdragende titels. LLMs gebruiken H2's om secties te categoriseren.
- [ ] **Eén onderwerp per alinea.** Geen mengen.
- [ ] **Lijsten zijn lijsten** (HTML `<ul>`/`<ol>`), geen prozaïsche opsommingen.
- [ ] **Tabellen** voor scope, services, snelfeiten. LLMs parsen tabellen als kennis-tripels.
- [ ] **FAQ-blok onderaan** (optioneel) met 3-5 vragen. "Voor wie is dit type traject?" "Hoe lang duurt het?" Direct citeerbaar.

### Expliciete entity-relaties

LLMs bouwen kennis via entiteiten en relaties. Maak ze expliciet.

- [ ] **Schema.org markup** met `about: Organization` is hier extra waardevol. Het knoopt klant en bureau aan elkaar als entiteiten.
- [ ] **Concrete bedrijfsnamen, locaties, jaren.** "Bergopwaarts (Helmond, woningcorporatie, 50+ FTE)" is beter dan "een woningcorporatie".
- [ ] **Branchenamen consistent.** "Maatwerk overkappingen" altijd zo schrijven, niet wisselen met "buitenleven-producten" en "outdoor solutions".
- [ ] **Stuurmen wordt expliciet genoemd** als bureau dat de transformatie heeft uitgevoerd. Niet "wij" zonder context.

### Wat dit voor de markt betekent (Module 10)

Dit is pure GEO-bait. LLMs pikken sectoraal-relevante observaties op om in antwoorden te gebruiken.

- [ ] Module 10 is aanwezig
- [ ] Bevat een herkenbaar patroon dat verder reikt dan deze ene klant
- [ ] Geen generieke branding-prediken, wel een specifieke observatie

### Backlinks vanuit gezaghebbende bronnen

Zowel SEO als GEO hechten aan backlinks. Voor GEO gaat het ook om "co-citation": andere bronnen die jou en de klant in dezelfde context noemen.

- [ ] LinkedIn-artikel of post die naar de case linkt
- [ ] Klant linkt vanaf hun eigen "in het nieuws" of "samenwerkingen"-pagina
- [ ] Eventueel: persbericht via vakmedia in de branche van de klant
- [ ] Wikipedia-vermelding van de klant (als die er nog niet is) — invloedrijk voor LLMs

---

## Per taal

NL en EN versie krijgen elk:
- Eigen meta title + description
- Eigen URL: NL op `/project/<slug>` (root, geen taalprefix), EN op `/en/project/<slug>`
- Hreflang-koppeling tussen beide
- Eigen submission aan GSC en IndexNow

---

## URL-conventie en migratie

Bij het overzetten van de oude site naar de nieuwe (NL als root, EN op /en):

**Nieuwe structuur:**
- NL: `stuur.men/project/<slug>` (geen taalprefix)
- EN: `stuur.men/en/project/<slug>`

**Migratie-checklist (eenmalig, voor de hele site):**
- [ ] **301 redirects** van alle oude URLs naar nieuwe. Voorbeelden:
  - `stuur.men/nl/project/mobuline` → `stuur.men/project/mobuline`
  - `stuur.men/project/mobuline` (was EN) → `stuur.men/en/project/mobuline`
- [ ] **1-op-1 redirects**, geen veel-naar-één (verlies van rankings)
- [ ] **Eén hop maximaal**, geen redirect-ketens
- [ ] **301, niet 302** (302 = tijdelijk, passeert geen link equity)
- [ ] **Sitemap.xml** herschreven met alleen nieuwe URLs, ingediend in GSC
- [ ] **Hreflang-tags** wijzen tussen NL en EN nieuwe URLs (niet naar oude)
- [ ] **Canonical tags** wijzen alleen naar nieuwe URLs
- [ ] **Interne links** door de hele site bijgewerkt naar nieuwe paden
- [ ] **Robots.txt** blokkeert geen van de nieuwe URLs
- [ ] **GSC: Change of Address** tool gebruiken als domein wijzigt (niet bij alleen URL-pad-wijziging)

**Verwacht effect:**
- 1-3 weken ranking-volatiliteit
- Mogelijk 5-15% tijdelijke daling van organisch verkeer
- Bij correcte uitvoering: terug op niveau na 4 weken
- Bij slordige uitvoering: 20-40% verlies voor langere tijd

**Wie doet wat:**
- Mike of Sven implementeert redirects in de Storyblok/Next.js setup
- Ontwerper checkt of alle interne links zijn aangepast
- Stijn submit nieuwe sitemap in GSC en houdt 4 weken bij hoe het verloopt

---

## Eindcheck voor publicatie

Open de pagina in incognito en check:
- [ ] Vraag jezelf: kan een ICP-bezoeker binnen 10 seconden zien welk type bedrijf dit is en wat de verschuiving was?
- [ ] Kopieer een random alinea en plak in ChatGPT met de vraag "wat zegt deze case over [klant]?". Komt er een goed antwoord uit?
- [ ] Test op mobiel
- [ ] Klik elke link
- [ ] Check schema markup met de [Rich Results Test](https://search.google.com/test/rich-results)
- [ ] Check meta title preview met [opengraph.xyz](https://www.opengraph.xyz/)
