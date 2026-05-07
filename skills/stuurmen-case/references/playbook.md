# Playbook — een case schrijven

Voor teamleden die met Claude een case willen maken. Lees dit één keer. Daarna gebruik je `/stuurmen-case` en kost het je 30 minuten in plaats van een dag.

---

## Voor je begint: bronmateriaal verzamelen

Hoe meer je klaarzet, hoe minder je zelf hoeft te schrijven. Zet alles in één folder: `context/cases/[klantnaam]/`.

**Verplicht:**
- Brand Concept Presentatie (PDF)
- Documentatie / workshop-output (PDF) — hier zit goud in: "klanten zien ons als", "in werkelijkheid zijn we", "strategie in één zin", "hopes & fears"
- Project plan met scope en looptijd

**Helpt enorm:**
- Transcript(s) van workshops of intake-gesprekken (Granola of Mac Whisperer export)
- Brand Summary
- Web Strategy (als er een site bij hoorde)
- Externe interviews (als die er waren)
- Zes maanden na oplevering: een kort gesprek met de directeur over wat er veranderd is

**Optioneel maar fijn:**
- Foto's van het eindresultaat (drukwerk, website, kantoor, etc.)
- Logo + huisstijl files
- Voor/na screenshots van de oude website

---

## De vijf vragen voor de klantquote

Stuurmen heeft niet altijd een quote in het materiaal. Bel de klant 3-6 maanden na oplevering en stel deze vijf vragen. Antwoord 2 of 5 wordt vaak de quote.

1. **"Als ik je vraag in één zin uit te leggen wat dit traject heeft veranderd, wat zou je zeggen?"** Pak het antwoord, parafrasering of letterlijk.
2. **"Wat zegt je team intern anders dan een jaar geleden?"** Hier komen verrassende observaties uit.
3. **"Welke gesprekken voer je nu wel die je toen niet voerde, of welke voer je niet meer?"** Concrete gedragsverandering.
4. **"Is er iets meetbaar veranderd sinds de oplevering, ook al is het zacht?"** Aanvragen, hires, prijsdiscussies, deals.
5. **"Wat zou je tegen een collega-directeur zeggen die overweegt dit ook te doen?"** Hier komt de echt bruikbare quote, omdat het geen marketing-vraag is.

Stuur de geselecteerde quote ter goedkeuring naar de klant voor publicatie. Altijd.

---

## Do's

- **Eerst materiaal verzamelen, dan pas de skill draaien.** Met een halve folder krijg je een halve case en moet je twee keer werk doen.
- **Lees de gegenereerde case kritisch.** Claude vult op basis van wat er is. Lege plekken worden expliciet gemarkeerd, fact-checken is aan jou.
- **Hou de strategische verschuiving (Module 5) als ankerpunt.** Als je twijfelt over een keuze in tekst of beeld, vraag jezelf: ondersteunt dit de verschuiving?
- **Schrijf in Stuurmen-toon.** Je/jij. Geen filler. Geen em dashes. Geen "ontzorgen", "klantgericht", "full-service". Niet "we hielpen X met Y" maar "X stond op een kantelpunt. Wij verschuiven het verhaal."
- **Zet de NL versie eerst af voor publicatie. EN komt na akkoord.**
- **Submit de URL aan Google Search Console na live gaan.** Skill helpt hierbij.

---

## Don'ts

- **Geen "Brand Strategy" als kop.** De lezer komt niet voor onze fase-namen, maar voor wat dit voor hém betekent. De koppen moeten betekenis dragen, niet ons proces beschrijven.
- **Geen losse design-modules.** Elke designkeuze hangt aan een strategische redenering. Mood-boards zonder uitleg voegen niets toe.
- **Geen poëtische taglines als hero-titel.** "Ervaar de luxe van textiel" zegt niets over wat wij hebben gedaan. "Van schaduwdoek tot textiel-architect" wel.
- **Geen vage cijfers.** "Veel meer aanvragen" is geen resultaat. Cijfer of niets, of expliciet "wat we tot nu toe zien".
- **Geen quote zonder naam, rol en bedrijf.** Anonieme quotes lezen als verzonnen.
- **Geen dubbele content tussen NL en EN.** Hreflang tags goed zetten, anders krijg je SEO-straf.

---

## Type A of Type B?

- **Type A (branding):** Stuurmen heeft merkstrategie + ontwerp gedaan. Met of zonder website.
- **Type B (web only):** alleen website, positionering stond al. Voorbeeld: ZZDP.

Twijfel? Type A. Liever te veel strategisch frame dan te weinig.

---

## Hoe de skill werkt — 4 stappen

**1. Start de skill**
```
/stuurmen-case [klantnaam]
```
De skill kijkt automatisch in `context/cases/[klantnaam]/` voor bronmateriaal.

**2. Skill stelt 3-5 vragen om gaten te vullen**
Wat ontbreekt in het materiaal: meestal de quote, harde cijfers, of de officiële scope.

**3. Skill genereert de NL case**
Volgens de vaste structuur. Inclusief meta title + description en wat er nog mist.

**4. Akkoord? → vertaling EN + submit URL**
Pas dan vertaling. Pas dan indexing. Niet eerder, want vertalen of submitten van een halve versie is dubbele kosten.

---

## Tijd-inschatting

Met goed bronmateriaal in de folder:
- Skill draaien + review: 30-45 min
- Klantquote ophalen (los gesprek): 30 min
- Photo-shoot of beeldkeuze: 1-3 uur
- Website-implementatie: aan developer
- Vertaling EN: 15 min met skill
- Indexing-stap: 5 min

Totaal: half uurtje voor een eerste draft, één werkdag voor publicatie-klaar.

---

## Wanneer Stijn betrekken

- Als de strategische verschuiving in Module 5 niet 100% klopt
- Als je twijfelt of de klant akkoord is met publicatie
- Als de quote nog niet bestaat en je niet kunt bellen
- Voor de eindredactie voor publicatie. Altijd.
