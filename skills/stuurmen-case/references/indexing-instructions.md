# Indexing — nieuwe case-URL submitten

Na publicatie wil je dat zoekmachines en LLMs de pagina zo snel mogelijk oppikken.

Deze instructies zijn voor Claude. Als je deze skill gebruikt, draait Claude de relevante stappen voor je. Lees mee zodat je weet wat er gebeurt.

---

## Wat werkt en wat niet

**Mythe:** "Submit URL to Google" via Search Console.
**Werkelijkheid:** Google heeft die functie in 2023 gedeprecreerd voor reguliere URLs. Alleen `JobPosting` en `BroadcastEvent` mogen via de Indexing API geforceerd worden.

**Wat wel werkt voor case-URLs:**

1. **Sitemap re-submit via Google Search Console API** (laat Google weten dat de sitemap is bijgewerkt)
2. **URL Inspection API** (check of pagina al bekend is, en handmatige indexering aanvragen via UI)
3. **IndexNow** voor Bing, Yandex, Seznam, Naver (directe URL-push)
4. **Sociale signalen** (LinkedIn-post met de URL versnelt zowel SEO als GEO)

LLM-spelers (Anthropic, OpenAI, Perplexity, Google AI) crawlen via dezelfde of vergelijkbare paden. Goede SEO-fundering = goede GEO-zichtbaarheid.

---

## Stap 1 — Voorbereiding

Voor de URL gesubmit kan worden:

- [ ] Pagina is live op productie-URL
- [ ] Pagina geeft 200-statuscode (geen redirect)
- [ ] Pagina staat in `sitemap.xml` van stuur.men
- [ ] `robots.txt` blokkeert de URL niet
- [ ] Hreflang-tags staan correct tussen NL en EN

Check 1-3 met:
```bash
curl -I https://stuur.men/project/[slug]
curl -s https://stuur.men/sitemap.xml | grep -i "[slug]"
curl -s https://stuur.men/robots.txt
```

---

## Stap 2 — Google Search Console

### Optie A: API (geautomatiseerd)

Gebruik de bestaande `google-search-console` skill in deze plugin (of de losse skill als die geïnstalleerd is). Die heeft authenticatie geregeld.

Wat de skill kan:
- Sitemap re-submitten zodat Google merkt dat er content is bijgekomen
- URL Inspection draaien om te zien of de pagina al geïndexeerd is en wat de status is
- Search-performance trekken na 2-4 weken om effect te meten

Workflow voor de case-skill:
```
1. Sitemap submit voor stuur.men
2. URL Inspection op /project/[slug] en /en/project/[slug]
3. Output: status (Indexed / Crawled but not indexed / Discovered) + lastCrawlTime
4. Sla resultaat op zodat Stijn kan zien wanneer de pagina officieel staat
```

### Optie B: Handmatig in de UI

Als de API-route niet werkt:

1. Ga naar [Google Search Console](https://search.google.com/search-console)
2. Selecteer property `stuur.men`
3. Bovenin: plak de volledige URL (bijvoorbeeld `https://stuur.men/project/mobuline`)
4. Klik "URL Inspection" → "Request Indexing"
5. Herhaal voor de EN-versie

Doorlooptijd: meestal binnen 1-7 dagen geïndexeerd.

---

## Stap 3 — IndexNow (Bing, Yandex, Seznam, Naver)

IndexNow is een open protocol dat directe URL-submission ondersteunt. Bing eet het meteen op. Yandex en kleinere spelers ook.

### Hoe het werkt

1. Een API-key file moet één keer op de root van stuur.men staan (`/[key].txt`)
2. Daarna kun je elke URL pushen met een GET- of POST-request

### Eenmalige setup (door developer)

Genereer een random key (32+ karakters, bijvoorbeeld via `openssl rand -hex 16`). Plaats het bestand `[key].txt` in de website-root met de key als enige inhoud.

Bijvoorbeeld key `a1b2c3d4e5f6...`:
- Bestand: `https://stuur.men/a1b2c3d4e5f6.txt`
- Inhoud: `a1b2c3d4e5f6` (zelfde key)

### Per URL submitten

```bash
curl -X POST https://api.indexnow.org/IndexNow \
  -H "Content-Type: application/json; charset=utf-8" \
  -d '{
    "host": "stuur.men",
    "key": "<key>",
    "keyLocation": "https://stuur.men/<key>.txt",
    "urlList": [
      "https://stuur.men/project/[slug]",
      "https://stuur.men/en/project/[slug]"
    ]
  }'
```

Response 200/202 = ontvangen. Doorlooptijd Bing: enkele uren tot een dag.

---

## Stap 4 — LLM-discovery versnellen

Geen officiële API om "ChatGPT, lees dit even". Wel routes die effect hebben:

- **LinkedIn-post** met de URL — wordt door LLM-crawlers (en door menselijke ICP) gezien
- **Klant linkt vanaf eigen site** — backlink uit gezaghebbende bron
- **Wikipedia-update** als de klant een artikel heeft — invloed op LLM-kennis is aantoonbaar
- **Reddit/HN-post** alleen als het organisch past — anders is het spam

Geen van deze stappen is verplicht voor de skill, wel handig voor de teamleden die de case promoten.

---

## Stap 5 — Monitoring

2-4 weken na publicatie:

- Check via GSC: hoeveel impressies, op welke queries?
- Plak de URL in ChatGPT en Perplexity met "wat staat er op deze pagina?" en "wat heeft Stuurmen voor [klant] gedaan?". Komt er een correct, citeerbaar antwoord?
- Check met `site:stuur.men [klantnaam]` of de pagina bovenaan staat voor de klantnaam zelf

Als de pagina na 4 weken niet geïndexeerd is:
- Check `robots.txt`, `noindex`-headers, canonical
- Check of de pagina niet duplicate content is met de oude case
- Voeg interne links toe vanuit andere pagina's (homepage, andere cases)
- Submit opnieuw via GSC met "Request Indexing"
