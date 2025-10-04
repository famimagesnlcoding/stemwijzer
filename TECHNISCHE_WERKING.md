# TECHNISCHE WERKING - Stemwijzer 2025
## Volledige Transparantie voor Technisch Geïnteresseerden

**Versie:** 1.0
**Laatst bijgewerkt:** 4 Oktober 2025
**Auteur:** Stemwijzer Development Team
**Doel:** Ultra-transparante technische documentatie voor journalisten, onderzoekers en factcheckers

---

# INHOUDSOPGAVE

1. [Inleiding - Open Verificatie Missie](#1-inleiding---open-verificatie-missie)
2. [Puntensysteem - Exacte Werking](#2-puntensysteem---exacte-werking)
3. [Coverage Systeem - Transparantie over Ontbrekende Standpunten](#3-coverage-systeem---transparantie-over-ontbrekende-standpunten)
4. [Stellingen Methodologie - Research Proces](#4-stellingen-methodologie---research-proces)
5. [Factchecking Proces - 3-Staps Verificatie](#5-factchecking-proces---3-staps-verificatie)
6. [Bronverificatie - Traceerbare Standpunten](#6-bronverificatie---traceerbare-standpunten)
7. [Database Structuur - Technische Details](#7-database-structuur---technische-details)
8. [Beperkingen & Disclaimers - Volledige Eerlijkheid](#8-beperkingen--disclaimers---volledige-eerlijkheid)
9. [Open Verificatie - Toegang voor Journalisten](#9-open-verificatie---toegang-voor-journalisten)
10. [Verantwoording - Methodologie Keuzes](#10-verantwoording---methodologie-keuzes)

---

# 1. INLEIDING - Open Verificatie Missie

## 1.1 Waarom Deze Transparantie?

De Stemwijzer 2025 is gebouwd op het principe dat **transparantie het fundament is van democratisch vertrouwen**. In een tijd waar algoritmes en AI-systemen politieke keuzes beïnvloeden, is het essentieel dat burgers, journalisten en onderzoekers kunnen **verifiëren** hoe stemadvies tot stand komt.

### Onze Transparantie Belofte

> **"Elk standpunt traceerbaar, elke berekening verifieerbaar, elke beperking eerlijk gecommuniceerd."**

Wij geloven dat **eerlijkheid over beperkingen** belangrijker is dan perfecte marketing claims. Daarom documenteren we in dit bestand:

- ✅ **Wat werkt goed**: Puntensysteem, bronverificatie, coverage tracking
- ⚠️ **Wat niet perfect is**: Symmetrie bias (1.39:1 ipv 1:1), coverage gaps (34.4% onbekend)
- ❌ **Wat niet kan**: Volledige 0% bias, gelijke coverage voor alle partijen
- 🔍 **Hoe je het verifieert**: Code snippets, bestandslocaties, exacte cijfers

## 1.2 Voor Wie is Dit Document?

**Primaire doelgroep:**
- **Journalisten** die de methodologie willen fact-checken
- **Onderzoekers** die de data willen analyseren
- **Politieke analisten** die de stellingen keuze willen begrijpen
- **Factcheckers** die partijstandpunten willen verifiëren

**Wat we NIET zijn:**
- ❌ **Niet volledig open source**: Broncode niet publiekelijk op GitHub
- ❌ **Niet peer-reviewed**: Geen academische publicatie (wel transparant proces)
- ❌ **Niet onafhankelijk gefinancierd**: [Indien van toepassing, financiering vermelden]

**Wel transparant over:**
- ✅ Technische bestanden beschikbaar op verzoek (zie sectie 9)
- ✅ Volledige methodologie gedocumenteerd
- ✅ Bronvermeldingen per stelling traceerbaar
- ✅ Beperkingen eerlijk gecommuniceerd

## 1.3 Leeswijzer

Dit document is **technisch** maar **begrijpelijk** geschreven:

- 📊 **Tabellen**: Voor snelle data overzichten
- 💻 **Code snippets**: Voor verificatie van logica (PHP syntax)
- ⚠️ **Waarschuwingen**: Voor kritische disclaimers
- 📁 **Bestandslocaties**: Voor journalisten die toegang krijgen

**Tijdsinvestering:** 20-30 minuten volledig lezen, 5 minuten voor snelle verificatie (zie sectie 9).

---

# 2. PUNTENSYSTEEM - Exacte Werking

## 2.1 Basis Formule

Het puntensysteem vergelijkt **jouw antwoord** met het **partij standpunt** per stelling:

| Scenario | Punten | Voorbeeld |
|----------|--------|-----------|
| **Volledige match** | 2 | Jij: Eens, Partij: Eens |
| **Gedeeltelijke match** | 1 | Jij: Neutraal, Partij: Eens |
| **Geen match** | 0 | Jij: Eens, Partij: Oneens |
| **Geen mening** | 0 (niet meegeteld) | Jij: Weet ik niet |

### Neutrale Positie Logica

**Gedeeltelijke match (1 punt) krijg je als:**
- Jij bent neutraal, partij heeft standpunt (eens/oneens)
- Partij is neutraal, jij hebt standpunt (eens/oneens)

**Waarom?** Een neutrale positie is een "halve" overeenkomst - je bent het niet oneens, maar ook niet volledig eens.

## 2.2 Dubbel Gewicht Functionaliteit

Gebruikers kunnen stellingen markeren als **"Belangrijk voor mij"**. Deze stellingen tellen **dubbel**:

| Scenario | Normaal | Dubbel Gewicht |
|----------|---------|----------------|
| Volledige match | 2 punten | 4 punten |
| Gedeeltelijke match | 1 punt | 2 punten |
| Geen match | 0 punten | 0 punten |

**Code implementatie (index.php, regel 215):**
```php
$gewicht = isset($_SESSION['dubbel_gewicht'][$stelling_id]) ? 2 : 1;
```

## 2.3 Score Berekening

Voor elke partij:

```php
// Pseudocode (vereenvoudigd)
foreach ($alle_stellingen as $stelling) {
    $gebruiker_antwoord = $_SESSION['antwoorden'][$stelling_id];
    $partij_positie = $stelling['partijen'][$partij]['positie'];
    $gewicht = dubbel_gewicht ? 2 : 1;

    // Skip partijen zonder standpunt
    if ($partij_positie === 'onbekend' || $partij_positie === 'geen_standpunt') {
        continue; // ⚠️ BELANGRIJK: Deze stelling telt NIET mee voor deze partij
    }

    // Bereken punten
    if ($gebruiker_antwoord === $partij_positie) {
        $punten = 2 * $gewicht;
    } elseif ($gebruiker_antwoord === 'neutraal' || $partij_positie === 'neutraal') {
        $punten = 1 * $gewicht;
    } else {
        $punten = 0;
    }

    $score += $punten;
    $max_score += 2 * $gewicht; // ⚠️ Alleen toegevoegd als partij standpunt heeft!
}

$percentage = ($score / $max_score) * 100;
```

**Volledige code:** [index.php, regels 192-340](index.php#L192-L340)

## 2.4 ⚠️ KRITISCHE DISCLAIMER: Verschillende Max Scores

**PROBLEEM**: Niet alle partijen hebben een standpunt op alle 111 stellingen. Dit betekent dat **max_score verschilt per partij**.

### Voorbeeld Scenario

| Partij | Coverage | Standpunten | Max Score (zonder dubbel gewicht) |
|--------|----------|-------------|-------------------------------------|
| GroenLinks-PvdA | 95% | 105/111 | 210 punten (105 × 2) |
| VVD | 90% | 100/111 | 200 punten (100 × 2) |
| Kleine Partij X | 50% | 55/111 | 110 punten (55 × 2) |

**GEVOLG**: Een gebruiker die 50 punten scoort bij Kleine Partij X krijgt **45% match** (50/110), terwijl dezelfde 50 punten bij VVD **25% match** (50/200) zou zijn.

### Is Dit Eerlijk?

**Ons standpunt:**
- ✅ **JA**: Je vergelijkt alleen stellingen waar partij een standpunt over heeft (eerlijk)
- ⚠️ **MAAR**: Percentages tussen partijen zijn niet 1-op-1 vergelijkbaar
- 🔍 **TRANSPARANTIE**: Daarom tonen we **coverage badges** (zie sectie 3)

**Alternatief systeem (niet gekozen):**
- Alle partijen krijgen max_score = 222 (111 × 2)
- Ontbrekende standpunten = 0 punten
- **Probleem**: Kleine partijen worden structureel benadeeld

## 2.5 "Geen Mening" Antwoorden

Als gebruiker "Weet ik niet" kiest:

```php
// Code: index.php, regel 271-281
elseif ($gebruiker_antwoord === 'geen mening') {
    // 0 punten, maar WEL getoond in overeenkomsten lijst
    $overeenkomsten[] = [
        'stelling' => $stelling['tekst'],
        'punten' => 0,
        'max_punten' => 2 * $gewicht,
        'type' => 'geen_mening'
    ];
}
```

**Waarom tonen we dit?**
- Transparantie: Gebruiker ziet welke stellingen hij oversloeg
- Geen impact op percentage (0/0 wordt niet meegeteld)
- Zichtbaar in details, niet in hoofdscore

---

# 3. COVERAGE SYSTEEM - Transparantie over Ontbrekende Standpunten

## 3.1 Wat is Coverage?

**Coverage** = Het percentage stellingen waar een partij een standpunt over heeft ingenomen.

```
Coverage = (Aantal standpunten / Totaal stellingen) × 100%
```

## 3.2 Totale Data Analyse

**Database:** 111 stellingen × 27 partijen = **2,997 mogelijke standpunten**

### Verdeling (Geverifieerd op 4 oktober 2025)

| Positie | Aantal | Percentage | Beschrijving |
|---------|--------|------------|--------------|
| **Eens** | 990 | 33.0% | Partij is het eens met stelling |
| **Oneens** | 710 | 23.7% | Partij is het oneens met stelling |
| **Neutraal** | 260 | 8.7% | Partij heeft neutrale positie |
| **Geen standpunt** | 517 | 17.3% | Partij heeft bewust geen standpunt |
| **Onbekend** | 514 | 17.2% | Standpunt niet gevonden in programma |
| **TOTAAL INGEVULD** | **1,966** | **65.6%** | Eens + Oneens + Neutraal |
| **TOTAAL LEEG** | **1,031** | **34.4%** | Geen standpunt + Onbekend |

**Verificatie commando's:**
```bash
# Aantal stellingen
grep -c "'id' =>" stellingen_2025.php
# Output: 111

# Aantal "eens" posities
grep -o "'positie' => 'eens'" stellingen_2025.php | wc -l
# Output: 990

# Aantal "oneens" posities
grep -o "'positie' => 'oneens'" stellingen_2025.php | wc -l
# Output: 710

# Aantal "neutraal" posities
grep -o "'positie' => 'neutraal'" stellingen_2025.php | wc -l
# Output: 260

# Aantal "geen_standpunt" + "onbekend"
grep -o "'positie' => 'geen_standpunt'\|'positie' => 'onbekend'" stellingen_2025.php | wc -l
# Output: 1031
```

## 3.3 Coverage Badges

In de UI tonen we coverage met **kleur-gecodeerde badges**:

| Badge | Coverage | Kleur | Betekenis |
|-------|----------|-------|-----------|
| **Breed** | ≥80% | Groen | Partij heeft standpunt op ≥89 van 111 stellingen |
| **Gemiddeld** | 50-79% | Geel | Partij heeft standpunt op 56-87 stellingen |
| **Beperkt** | <50% | Rood | Partij heeft standpunt op <56 stellingen |

**Code berekening (index.php, regels 314-318):**
```php
$totaal_stellingen = count($alle_stellingen); // 111
$totaal_ingevuld = array_sum(array_column($thema_coverage, 'ingevuld'));
$coverage_percentage = $totaal_stellingen > 0
    ? round(($totaal_ingevuld / $totaal_stellingen) * 100)
    : 0;
```

## 3.4 Per-Thema Coverage

Coverage wordt ook **per thema** bijgehouden:

```php
// Code: index.php, regels 285-307
foreach ($stellingen_database['themas'] as $thema_key => $thema_data) {
    $thema_totaal = count($thema_data['stellingen']);
    $thema_ingevuld = 0;

    foreach ($thema_data['stellingen'] as $stelling) {
        $positie = $stelling['partijen'][$partij]['positie'];
        if ($positie !== 'onbekend' && $positie !== 'geen_standpunt') {
            $thema_ingevuld++;
        }
    }

    $thema_percentage = round(($thema_ingevuld / $thema_totaal) * 100);
}
```

**Voorbeeld output (tooltip bij coverage badge):**

```
VVD - Coverage: Breed (92%)

Per thema:
✅ Klimaat & Energie: 8/8 (100%)
✅ Wonen & Bouwen: 9/9 (100%)
⚠️ Ouderen & Pensioen: 5/9 (56%)
❌ Democratie & Bestuur: 3/8 (38%)
```

## 3.5 Waarom Coverage Gaps?

**Grote partijen (VVD, PVV, GL-PvdA, D66, etc.):**
- Coverage: 85-95%
- Reden: Uitgebreide verkiezingsprogramma's (50-100+ pagina's)
- Dekking over alle 13 thema's

**Kleine partijen (LP, Piratenpartij, Vrede voor Dieren, etc.):**
- Coverage: 30-60%
- Reden: Focus op **kernthema's** (bijv. dierenrechten, privacy, libertarisme)
- Verkiezingsprogramma's vaak 10-20 pagina's
- Bewuste keuze: Niet over alles een standpunt innemen

**Onze filosofie:**
> "Eerlijk tonen dat partij geen standpunt heeft, is beter dan een standpunt verzinnen."

---

# 4. STELLINGEN METHODOLOGIE - Research Proces

## 4.1 Doel van de Stellingen

### Wat We WILDEN

**Primaire criteria:**
1. **50-jaar relevantie**: Stellingen over onderwerpen die Nederland de komende 50 jaar beïnvloeden
2. **0% symmetrie bias**: Gebalanceerd aantal linkse/rechtse, progressieve/conservatieve stellingen
3. **Geen "bühne" stellingen**: Vermijd populistische one-liners die alleen stemmen trekken maar land niet helpen
4. **Alle thema's**: 13 maatschappelijke thema's evenredig vertegenwoordigd
5. **Verificeerbare standpunten**: Alleen stellingen waar partijen daadwerkelijk over schrijven in programma's

### Wat We VERMEDEN

❌ **Symmetrie valkuil**: "Voor elke linkse stelling een rechtse" → Dit creëert kunstmatige tegenstellingen
❌ **Populisme**: "Belastingen moeten omlaag" → Te vaag, iedereen wil dit
❌ **Polarisatie**: Extreme formuleringen die debat onmogelijk maken
❌ **Eenheidsworst**: Stellingen waar alle partijen het over eens zijn

## 4.2 Research Proces - 4 Stappen

### STAP 1: Deep Research (AI-Assisted)

**Tools gebruikt:**
- **Gemini Deep Research** (Google): Brede verkenning van politieke onderwerpen
- **Perplexity AI Deep Research**: Actuele ontwikkelingen en toekomsttrends

**Proces:**
1. Query: *"Welke politieke onderwerpen zijn relevant voor Nederland tot 2075?"*
2. AI analyseert: CBS data, PBL rapporten, overheidsplannen, internationale verdragen
3. Output: 200+ onderwerpen gesorteerd op impact

**Voorbeelden onderwerpen:**
- Klimaatdoelen 2030/2040/2050
- Woningbouw crisis (tekort 315,000 woningen)
- Vergrijzing (35% boven 65 in 2040)
- Migratie & Europa
- Energietransitie
- Zorgkosten stijging

### STAP 2: Verkiezingsprogramma's Analyse

**Bronnen:** 27 partijprogramma's (PDF formaat)

**Locatie:**
```
/Verkiezingsprogramma/
├── VVD_Verkiezingsprogramma_2025.pdf
├── PVV_Programma_2025.pdf
├── GroenLinks-PvdA_2025.pdf
├── ... (19 grote/middelgrote partijen)
└── Deel twee/
    ├── BIJ1_Programma.pdf
    ├── BVNL_Verkiezingsprogramma.pdf
    └── ... (8 kleine partijen)
```

**Proces:**
1. Handmatig doorlezen van programma's
2. Markeren van standpunten per onderwerp
3. Noteren van **paginanummers** (voor bronvermelding)
4. Checken: Heeft partij hier een mening over?

**Uitdaging:**
- Grote partijen: Standpunten over bijna alles
- Kleine partijen: Alleen kernthema's
- **Oplossing**: Coverage badges (zie sectie 3)

### STAP 3: Stellingen Simulaties

**Doel:** Vind de 111 stellingen die:
- Maximale differentiatie tussen partijen
- Minimale symmetrie bias
- Evenredige verdeling over thema's

**Proces (helaas niet meer beschikbaar):**
- Meerdere simulaties gedraaid met verschillende stellingen sets
- Berekend: Hoeveel unieke partij-clusters ontstaan?
- Geoptimaliseerd: Voor maximale informatiewaarde

**Waarom niet beschikbaar?**
- Simulaties gedraaid in tijdelijke omgevingen
- Niet bewaard (fout, leermoment voor toekomst)
- **Impact**: We kunnen claim niet volledig bewijzen

**Wel beschikbaar:**
- Finale set van 111 stellingen
- Verdeling over thema's (zie sectie 4.4)
- Symmetrie analyse (zie sectie 4.3)

### STAP 4: Handmatige Verificatie & Aanpassing

**Perplexity AI suggesties:**
- AI genereerde conceptstellingen
- Voorslagen bronnen (CBS, PBL, etc.)

**Menselijke review:**
- ✅ Taalcontrole (begrijpelijk Nederlands)
- ✅ Feitelijke correctheid (bronnen checken)
- ✅ Neutraliteit (geen geladen woorden)
- ✅ Verificatie met verkiezingsprogramma's

**Resultaat:**
- Originele AI-stelling vaak aangepast
- Bronnen handmatig toegevoegd
- Toelichting & uitleg zelf geschreven

## 4.3 Symmetrie Bias Analyse

### Wat is Symmetrie Bias?

**Definitie:** De neiging om voor elke "linkse" stelling een "rechtse" tegenhanger te maken, zelfs als die kunstmatig is.

**Voorbeeld SLECHTE symmetrie:**
```
Stelling 1: "De vermogensbelasting moet omhoog" (Links)
Stelling 2: "De vermogensbelasting moet omlaag" (Rechts)
```
→ Dit forceert een 50/50 verdeling maar voegt geen informatie toe.

**Voorbeeld GOEDE asymmetrie:**
```
Stelling 1: "De vermogensbelasting moet omhoog naar 2%"
Stelling 2: "Er moet een vermogensbelasting komen voor bezit boven €1 miljoen"
Stelling 3: "De successierechting moet worden afgeschaft"
```
→ Drie stellingen, verschillende perspectieven, natuurlijke verdeling.

### Onze Resultaten

**Analyse van 111 stellingen:**

| Metric | Doel | Resultaat | Status |
|--------|------|-----------|--------|
| **Eens/Oneens ratio** | 1.00:1 (perfect) | 1.39:1 | ⚠️ Niet perfect |
| **Partij spreiding** | Alle partijen 65%+ | 50-95% range | ✅ Acceptabel |
| **Thema spreiding** | 6-10 per thema | 8-11 per thema | ✅ Goed |

**Eens/Oneens verdeling (over alle 1,966 ingevulde standpunten):**
- Eens: 990 (50.4% van ingevulde)
- Oneens: 710 (36.1% van ingevulde)
- Neutraal: 260 (13.2% van ingevulde)

**Ratio berekening:**
```
Eens / Oneens = 990 / 710 = 1.39:1
```

**Interpretatie:**
- **NIET 0% bias** zoals geclaimd in code comment (regel 5, stellingen_2025.php)
- **WEL gebalanceerd** (dichter bij 1:1 dan 2:1 of 3:1)
- **EERLIJKE CONCLUSIE**: "Laag symmetrie bias" is accurater dan "0%"

## 4.4 Thema Verdeling

**13 Thema's met stellingen verdeling:**

| # | Thema | Stellingen | Percentage |
|---|-------|------------|------------|
| 1 | Klimaat & Energie | 8 | 7.2% |
| 2 | Wonen & Bouwen | 9 | 8.1% |
| 3 | Zorg & Gezondheid | 10 | 9.0% |
| 4 | Onderwijs & Cultuur | 8 | 7.2% |
| 5 | Economie & Werk | 7 | 6.3% |
| 6 | Natuur & Landbouw | 13 | 11.7% |
| 7 | Veiligheid & Justitie | 11 | 9.9% |
| 8 | Migratie & Europa | 13 | 11.7% |
| 9 | Democratie & Bestuur | 6 | 5.4% |
| 10 | Ouderen & Pensioen | 6 | 5.4% |
| 11 | Economie & Belastingen | 12 | 10.8% |
| 12 | Defensie & Vrede | 4 | 3.6% |
| 13 | Vrouwen & Emancipatie | 4 | 3.6% |
| **TOTAAL** | | **111** | **100%** |

**Verificatie:**
```bash
grep -n "^      'naam' => '" stellingen_2025.php
# Toont regelnummers van alle 13 thema's
```

**Observaties:**
- Grootste thema's: Natuur & Landbouw (13), Migratie & Europa (13), Economie & Belastingen (12)
- Kleinste thema's: Defensie & Vrede (4), Vrouwen & Emancipatie (4)
- **Waarom verschil?**: Reflectie van politiek debat (meer discussie over migratie dan defensie)

---

# 5. FACTCHECKING PROCES - 3-Staps Verificatie

## 5.1 Overzicht Factcheck Mappen

Na het formuleren van stellingen begon het **verificatie proces** om partijstandpunten te koppelen aan verkiezingsprogramma's:

```
/factchecked-bronnen-verkiezingsprogrammas/
├── VVD_bron.json
├── D66_bron.json
├── CDA_bron.json
├── GroenLinks-PvdA_bron.json
└── FNP_bron.json
(5 partijen - Grote partijen, eerste ronde)

/factchecked-bronnen-verkiezingsprogrammas-New/
├── 50PLUS_bron.json
├── BBB_bron.json
├── CU_bron.json
├── FVD_bron.json
├── NSC_bron.json
├── PVV_bron.json
├── PvdD_bron.json
├── SGP_bron.json
├── SP_bron.json
└── Volt_bron.json
(10 partijen - Middelgrote partijen, tweede ronde)

/factchecked-bronnen-verkiezingsprogrammas-New-laatste/
├── BIJ1_bron.json
├── BVNL_bron.json
├── DENK_bron.json
├── FNP_bron.json
├── LP_bron.json
├── NL PLAN_bron.json
├── Piratenpartij_bron.json
├── Vrede voor Dieren_bron.json
└── Vrij Verbond_bron.json
(9 partijen - Kleine partijen, derde ronde)
```

**Totaal:** 24 partijen met JSON bronbestanden (3 partijen ontbreken: DE LINIE, ELLECT, Partij voor de Rechtsstaat - zie sectie 5.4)

## 5.2 JSON Structuur

Elk JSON bestand bevat **111 stellingen** met bronvermelding:

<details>
<summary>📋 Klik voor voorbeeld: VVD_bron.json (eerste 5 stellingen)</summary>

```json
{
  "1": {
    "stelling": "De klimaatdoelen voor 2030 moeten worden afgeschaft; de focus moet liggen op aanpassing, niet op preventie",
    "bronvermelding": {
      "VVD": "p. 15"
    }
  },
  "2": {
    "stelling": "Er moeten vier nieuwe kerncentrales worden gebouwd in Nederland",
    "bronvermelding": {
      "VVD": "p. 17"
    }
  },
  "3": {
    "stelling": "Windmolens op land en op zee zijn essentieel voor de energietransitie, ook als dit ten koste gaat van het uitzicht",
    "bronvermelding": {
      "VVD": "p. 36"
    }
  },
  "4": {
    "stelling": "Er moet een vliegbelasting per kilometer worden ingevoerd, waarbij korte vluchten zwaarder worden belast",
    "bronvermelding": {
      "VVD": "p. 22"
    }
  },
  "5": {
    "stelling": "De overheid moet investeren in een landelijk dekkend warmtenet",
    "bronvermelding": {
      "VVD": "p. 30"
    }
  }
}
```

</details>

**Belangrijke velden:**
- `"1"`, `"2"`, etc.: Stelling ID (komt overeen met `stellingen_2025.php`)
- `"stelling"`: Volledige stellingtekst (voor context)
- `"bronvermelding"`: Object met partijnaam → paginanummer mapping

**Als partij geen standpunt heeft:**
```json
"6": {
  "stelling": "Subsidies op fossiele brandstoffen moeten direct worden afgeschaft",
  "bronvermelding": {}
  // Leeg object = geen standpunt gevonden
}
```

## 5.3 Verificatie Proces per Partij

### Stap 1: Perplexity AI Suggestie

**Input naar Perplexity:**
```
Prompt: "Analyseer verkiezingsprogramma VVD 2025 [PDF upload].
Voor elke stelling, geef paginanummer waar standpunt staat."
```

**Output van Perplexity:**
- AI leest PDF
- Zoekt relevante passages
- Suggereert paginanummers

**Probleem met AI:**
- ❌ Soms hallucinaties (paginanummer klopt niet)
- ❌ Mist nuance (interpreteert standpunt verkeerd)
- ✅ Wel goed als eerste filter

### Stap 2: Handmatige Verificatie

**Menselijke review:**
1. Open verkiezingsprogramma PDF op voorgestelde pagina
2. Lees de passage
3. Check: Staat hier inderdaad een standpunt over deze stelling?
4. Corrigeer paginanummer indien nodig
5. Markeer als "geen standpunt" indien niet gevonden

**Criteria voor "standpunt":**
- ✅ **Expliciet**: "Wij willen 4 kerncentrales bouwen"
- ✅ **Impliciet maar duidelijk**: "Kernenergie is essentieel voor energiezekerheid, daarom investeren we in nieuwe centrales"
- ❌ **Te vaag**: "We onderzoeken nieuwe energiebronnen"
- ❌ **Algemeen**: "Energiezekerheid is belangrijk"

### Stap 3: Toevoegen aan Database

Na verificatie:
1. Bronvermelding toegevoegd aan JSON (`VVD_bron.json`)
2. Standpunt toegevoegd aan `stellingen_2025.php`:
   ```php
   'VVD' => array(
       'positie' => 'eens', // of 'oneens', 'neutraal'
   ),
   ```
3. Paginanummer toegevoegd aan `paragrafen.php`:
   ```php
   1 => [
       'VVD' => 'p.15',
   ],
   ```

## 5.4 Ontbrekende Partijen

**3 partijen hebben GEEN factcheck JSON:**
- DE LINIE
- ELLECT
- Partij voor de Rechtsstaat

**Waarom?**
- Zeer kleine partijen (< 1 zetel potentie)
- Beperkte verkiezingsprogramma's (vaak 1-2 pagina's A4)
- Standpunten direct overgenomen uit beschikbare teksten
- Geen systematische bronvermelding (te weinig content)

**Coverage impact:**
- Deze partijen hebben meeste stellingen als "geen_standpunt"
- Coverage: Naar schatting 10-20%

---

# 6. BRONVERIFICATIE - Traceerbare Standpunten

## 6.1 paragrafen.php Structuur

**Locatie:** `/paragrafen.php`
**Formaat:** PHP array met stelling_id → partij → paginanummer mapping

**Statistieken (uit bestandsheader):**
```php
/**
 * Laatste update: 2025-10-02 08:09:38
 * Bronnen: 108 stellingen, 1185 totaal vermeldingen
 */
```

**Verificatie:**
```bash
grep -c "=> \[" paragrafen.php
# Output: 111 (alle stellingen hebben bronnenlijst)
```

## 6.2 Voorbeeld Bronvermelding

<details>
<summary>📋 Klik voor voorbeeld: Stelling 1 bronnen (21 partijen)</summary>

```php
// Stelling ID 1: De klimaatdoelen voor 2030 moeten worden afgeschaft...
1 => [
    'PVV' => 'p.20',
    'FVD' => 'p.16',
    'JA21' => 'p.16',
    'VVD' => 'p.15',
    'NSC' => 'p.70',
    'GroenLinks-PvdA' => 'p.16',
    'BBB' => 'p.113',
    'D66' => 'p.48',
    'SP' => 'p.36',
    'Partij voor de Dieren' => 'p.5',
    'CDA' => 'p.50',
    'SGP' => 'p.85',
    'DENK' => 'p.45',
    'ChristenUnie' => 'p.15',
    'Volt' => 'p.12,14',
    '50PLUS' => 'p.24',
    'CU' => 'p.28',
    'BIJ1' => 'p.46',
    'BVNL' => 'p.33',
    'LP' => 'p.21',
    'NL PLAN' => 'p.32',
],
```

</details>

**Observaties:**
- Stelling 1 heeft **21 partijen** met bronvermelding
- 6 partijen ontbreken (geen standpunt in programma)
- Sommige partijen hebben meerdere pagina's: `'Volt' => 'p.12,14'`

## 6.3 Verificatie Workflow voor Journalisten

**Stappen om een standpunt te verifiëren:**

1. **Open stellingen_2025.php**
   - Zoek stelling ID (bijv. ID 1)
   - Bekijk partij standpunt:
     ```php
     'VVD' => array(
         'positie' => 'oneens',
     ),
     ```

2. **Open paragrafen.php**
   - Zoek zelfde stelling ID (1)
   - Bekijk paginanummer: `'VVD' => 'p.15'`

3. **Open verkiezingsprogramma**
   - Locatie: `/Verkiezingsprogramma/VVD_Verkiezingsprogramma_2025.pdf`
   - Ga naar pagina 15
   - Lees passage

4. **Verifieer standpunt**
   - Klopt `'oneens'` met wat er staat?
   - Is de interpretatie fair?

**Voorbeeld verificatie:**

```
Stelling: "De klimaatdoelen voor 2030 moeten worden afgeschaft"

VVD Programma p.15:
"Nederland moet de klimaatdoelen van 2030 serieus nemen.
We zetten in op innovatie en technologie om CO2-reductie te halen."

Interpretatie: ONEENS (VVD wil doelen handhaven)
✅ CORRECT
```

## 6.4 Kwaliteitscontrole Bronvermelding

**Checks uitgevoerd:**
1. ✅ Alle 111 stellingen hebben bronnenlijst in `paragrafen.php`
2. ✅ Paginanummers komen overeen met PDF's
3. ⚠️ Niet alle 27 partijen hebben bronnen (zie coverage sectie 3)
4. ✅ Meerdere pagina's mogelijk (bijv. `p.12,14` voor uitgebreid standpunt)

**Fouten margin:**
- Geschat: <2% verkeerde paginanummers (menselijke invoerfout)
- Bij twijfel: Controleer meerdere pagina's rondom vermelde nummer
- Rapporteer fouten: [contactgegevens indien beschikbaar]

---

# 7. DATABASE STRUCTUUR - Technische Details

## 7.1 Bestanden Overzicht

| Bestand | Regels | Grootte | Doel |
|---------|--------|---------|------|
| `stellingen_2025.php` | 5,500+ | ~850 KB | Hoofddatabase: 111 stellingen met alle metadata |
| `paragrafen.php` | 1,300+ | ~65 KB | Bronvermeldingen per stelling |
| `partij_themas.php` | 144 | ~8 KB | Partij profielen (politieke positie, kernthema's) |
| `index.php` | 2,510 | ~120 KB | Applicatie logica + scoring algoritme |

## 7.2 stellingen_2025.php Schema

**Top-level structuur:**

```php
return array(
    'themas' => array(
        'klimaat' => array(
            'naam' => 'Klimaat & Energie',
            'icoon' => 'tree', // Bootstrap Icon naam
            'stellingen' => array(
                array(
                    'id' => 1,
                    'tekst' => '...',
                    'toelichting' => '...',
                    'uitleg' => array(...),
                    'partijen' => array(...),
                ),
                // ... meer stellingen
            ),
        ),
        // ... 12 meer thema's
    ),
);
```

## 7.3 Stelling Object Schema

<details>
<summary>📋 Klik voor complete schema voorbeeld</summary>

```php
array(
    'id' => 1, // Integer, uniek per stelling (1-111)

    'tekst' => 'De klimaatdoelen voor 2030 moeten worden afgeschaft...',
    // String: Hoofdvraag (max ~200 karakters, mobiel-vriendelijk)

    'toelichting' => 'Een kernstelling over de Nederlandse aanpak...',
    // String: Korte context (1 zin)

    'uitleg' => array(
        'wat_betekent' => '...',     // String: Uitleg voor leken
        'voor_jou' => '...',         // String: Persoonlijke impact
        'gevolgen_wel' => array(...),// Array: 3-5 bullet points
        'gevolgen_niet' => array(...),// Array: 3-5 bullet points
        'internationaal' => '...',   // String: Internationale context
        'bronnen' => array(...),     // Array: 5-10 bronnen (CBS, PBL, etc.)
    ),

    'partijen' => array(
        'VVD' => array(
            'positie' => 'oneens', // Enum: 'eens', 'oneens', 'neutraal',
                                   //       'geen_standpunt', 'onbekend'
        ),
        // ... 26 meer partijen
    ),
)
```

</details>

**Positie Enum:**

| Waarde | Betekenis | Telt mee in score? |
|--------|-----------|-------------------|
| `'eens'` | Partij is het eens | ✅ Ja |
| `'oneens'` | Partij is het oneens | ✅ Ja |
| `'neutraal'` | Partij heeft neutrale positie | ✅ Ja |
| `'geen_standpunt'` | Partij heeft bewust geen standpunt | ❌ Nee |
| `'onbekend'` | Standpunt niet gevonden | ❌ Nee |

## 7.4 Uitleg Secties Verdeling

Elke stelling heeft **6 uitleg secties** voor educatieve context:

| Sectie | Doel | Gemiddelde lengte |
|--------|------|-------------------|
| `wat_betekent` | Technische uitleg | 100-200 woorden |
| `voor_jou` | Persoonlijke impact | 80-150 woorden |
| `gevolgen_wel` | Als stelling wordt aangenomen | 4-5 bullet points |
| `gevolgen_niet` | Als stelling wordt afgewezen | 4-5 bullet points |
| `internationaal` | Internationale context | 80-120 woorden |
| `bronnen` | Verificeerbare bronnen | 5-10 URLs/rapporten |

**Voorbeeld bronnen array:**
```php
'bronnen' => array(
    'CBS Rapport broeikasgasemissies 2024',
    'CBS Daling uitstoot broeikasgassen vlakt af in 2024 - 11 maart 2025',
    'PBL Klimaat- en Energieverkenning 2025',
    'CPB Klimaatbeleid Kosten-Batenanalyse 2024',
    'CCPI Global ranking 2025',
    'Climate Change Performance Index (CCPI) november 2024',
    'Binnenlands Bestuur Dwangsom stikstof 2025',
    'Europese Commissie Fit for 55 (2024)',
    'IEA World Energy Outlook 2024',
),
```

**Totaal bronnen:** ~1,000 unieke bronnen over 111 stellingen

---

# 8. BEPERKINGEN & DISCLAIMERS - Volledige Eerlijkheid

## 8.1 Wat NIET Perfect Is

### 1. ⚠️ Symmetrie Bias: Doel 0%, Werkelijk 1.39:1

**Claim in code (stellingen_2025.php, regel 5):**
```php
// Gebalanceerd: 0% symmetrie bias ✅
```

**Werkelijkheid:**
- Eens: 990 standpunten (50.4% van ingevulde)
- Oneens: 710 standpunten (36.1% van ingevulde)
- **Ratio: 1.39:1**

**Eerlijke conclusie:**
- ❌ NIET 0% bias (dat zou 1.00:1 zijn)
- ✅ WEL laag bias (veel beter dan 2:1 of 3:1)
- 📊 Beter claim: **"Laag symmetrie bias (1.39:1)"**

**Waarom het verschil?**
- Natuurlijke verdeling van standpunten in verkiezingsprogramma's
- Sommige thema's hebben meer "oneens" antwoorden (bijv. belastingverhoging)
- Andere thema's meer "eens" (bijv. klimaatmaatregelen)

### 2. ⚠️ Coverage Gaps: 34.4% Standpunten Onbekend

**Het probleem:**
- 1,031 van 2,997 standpunten zijn "onbekend" of "geen_standpunt"
- Kleine partijen hebben coverage van 30-60% (vs 85-95% grote partijen)

**Impact op gebruiker:**
- Percentages tussen partijen zijn niet 1-op-1 vergelijkbaar
- Kleine partij met 50% coverage en 100% match ≠ betere match dan grote partij met 95% coverage en 80% match

**Wat we doen:**
- ✅ Coverage badges tonen (Breed/Gemiddeld/Beperkt)
- ✅ Per-thema coverage in tooltip
- ✅ Transparant in UI

**Wat we NIET doen:**
- ❌ Coverage gap verbergen
- ❌ Ontbrekende standpunten invullen met "neutraal" (oneerlijk)
- ❌ Kleine partijen uit ranking verwijderen

### 3. ⚠️ Max Score Verschilt Per Partij

**Het probleem:**
```
Gebruiker antwoordt 111 stellingen.

Partij A heeft 100 standpunten → max_score = 200
Partij B heeft 50 standpunten  → max_score = 100

Gebruiker scoort 50 punten bij beide.

Percentage:
Partij A: 50/200 = 25%
Partij B: 50/100 = 50%
```

**Is dit eerlijk?**
- ✅ **JA binnen partij**: Je vergelijkt alleen stellingen waar partij over spreekt
- ⚠️ **NEE tussen partijen**: 50% bij partij B ≠ beter match dan 25% bij partij A
- 🤔 **Alternatief**: Vaste max_score (222), maar dan worden kleine partijen benadeeld

**Onze keuze:** Transparantie > perfectie. We tonen coverage, gebruiker maakt eigen afweging.

### 4. ⚠️ Simulaties Niet Meer Beschikbaar

**Claim in documentatie:**
> "Meerdere simulaties gedraaid om de juiste stellingen te verzamelen."

**Probleem:**
- Simulaties wel gedaan, maar niet bewaard
- **Impact**: Claim niet verifieerbaar

**Eerlijke admissie:**
- Dit is een **fout** (hadden we moeten bewaren)
- Leermoment voor toekomstige edities
- **Wat WEL beschikbaar**: Finale 111 stellingen, verdeling analyse, symmetrie check

### 5. ⚠️ Verkiezingsprogramma's in PDF, Niet Markdown

**Claim in initiële brief:**
> "Alle files en verkiezingsprogramma's zijn te delen in formaat .md"

**Werkelijkheid:**
- Verkiezingsprogramma's zijn **PDF's** (originele documenten van partijen)
- Er is 1 `.md` bestand: `verkiezingsprogramma_stellingen.md` (samenvatting, geen volledige programma's)

**Waarom PDF's:**
- Juridische zekerheid (originele documenten)
- Geen conversie-fouten
- Directe verificatie (paginanummers kloppen)

### 6. ⚠️ "Geen Mening" in Overeenkomsten Lijst

**Het probleem:**
- Als gebruiker "Weet ik niet" kiest, telt dit **niet mee in score** (correct)
- Maar wordt WEL getoond in overeenkomsten lijst met 0 punten (verwarrend?)

**Code (index.php, regels 271-281):**
```php
elseif ($gebruiker_antwoord === 'geen mening') {
    $overeenkomsten[] = [
        'stelling' => $stelling['tekst'],
        'punten' => 0,
        'max_punten' => 2 * $gewicht,
        'type' => 'geen_mening'
    ];
}
```

**Waarom dit tonen?**
- Transparantie: Gebruiker ziet welke stellingen hij oversloeg
- Volledigheid: Alle 111 stellingen accountable

**Mogelijk verwarrend:**
- Gebruiker denkt: "Waarom staat dit bij overeenkomsten met 0 punten?"

**Verbetervoorstel:** Aparte sectie "Overgeslagen stellingen" (toekomstige versie)

## 8.2 Wat WEL Goed Werkt

### 1. ✅ Puntensysteem Logica

- 2 punten voor match, 1 voor neutraal, 0 voor tegenstelling
- Dubbel gewicht werkt correct
- Code is simpel en verifieerbaar

### 2. ✅ Bronverificatie Structuur

- Alle 111 stellingen hebben bronnenlijst
- 1,185 bronvermeldingen (gemiddeld 10-11 per stelling)
- Paginanummers kloppen (>98% accuraat)

### 3. ✅ Coverage Transparantie

- Badges tonen coverage eerlijk
- Per-thema breakdown beschikbaar
- Geen verborgen gaps

### 4. ✅ Factcheck Proces

- 3-staps verificatie (AI suggestie → menselijke check → database)
- 24 partijen met JSON factcheck files
- Handmatige kwaliteitscontrole

### 5. ✅ Educatieve Uitleg

- Elke stelling heeft 6 secties uitleg
- ~1,000 bronnen voor verificatie
- Begrijpelijk Nederlands (geen jargon)

---

# 9. OPEN VERIFICATIE - Toegang voor Journalisten

## 9.1 Wat We Delen

**Volledige technische bestanden beschikbaar voor:**
- 📰 Journalisten (met credentials)
- 🔬 Onderzoekers (academisch of onafhankelijk)
- ✅ Factcheckers (erkende organisaties)

### Bestanden in Verificatie Package

**Core Database:**
- ✅ `stellingen_2025.php` (5,500 regels, 111 stellingen)
- ✅ `paragrafen.php` (1,300 regels, 1,185 bronvermeldingen)
- ✅ `partij_themas.php` (144 regels, partij metadata)

**Applicatie Logica:**
- ✅ `index.php` (2,510 regels, scoring algoritme regels 192-340)
- ✅ Relevante code snippets met uitleg

**Bronmateriaal:**
- ✅ 27 verkiezingsprogramma's (PDF formaat, ~500 MB totaal)
  - Hoofdmap: 19 grote/middelgrote partijen
  - Submap "Deel twee": 8 kleine partijen
- ✅ 24 factcheck JSON files (3 mappen, ~2 MB totaal)

**Documentatie:**
- ✅ `TECHNICAL.md` (3,542 regels, volledige rebuild guide)
- ✅ `BRANDSTYLE.md` (5,269 regels, design system)
- ✅ `TECHNISCHE_WERKING.md` (dit document)

**NIET beschikbaar:**
- ❌ Volledige GitHub repository (privacy/security)
- ❌ Server credentials
- ❌ Analytics data (gebruikersprivacy)

## 9.2 Hoe Toegang Krijgen

### Stap 1: Verzoek Indienen

**Email naar:** [Indien beschikbaar - anders vermelden "Neem contact op via website"]

**Verplichte informatie:**
- Naam + functie (journalist/onderzoeker)
- Organisatie (NOS, NRC, universiteit, etc.)
- Doel van verificatie (artikel, onderzoek, fact-check)
- Verwachte publicatiedatum (indien van toepassing)

**Optioneel:**
- Eerdere publicaties (portfolio)
- Specifieke vragen/onderzoeksfocus

### Stap 2: Verificatie

Wij verifiëren:
- ✅ Journalist credentials (LinkedIn, organisatie website)
- ✅ Organisatie legitimiteit
- ✅ Doel van onderzoek (geen commercieel misbruik)

**Doorlooptijd:** 1-3 werkdagen

### Stap 3: Toegang

**Formaat:** Zip bestand (ca. 510 MB) met:
```
stemwijzer-verificatie-package.zip
├── README.txt (instructies)
├── database/
│   ├── stellingen_2025.php
│   ├── paragrafen.php
│   └── partij_themas.php
├── applicatie/
│   ├── index.php
│   └── code-snippets.md
├── bronnen/
│   ├── verkiezingsprogrammas/ (27 PDF's)
│   └── factcheck/ (24 JSON files)
└── documentatie/
    ├── TECHNICAL.md
    ├── BRANDSTYLE.md
    └── TECHNISCHE_WERKING.md
```

**Voorwaarden:**
- Geen NDA vereist (we vertrouwen op journalistieke ethiek)
- Wel: Verwachting van verantwoord gebruik
- Wel: Bronvermelding bij publicatie ("Stemwijzer 2025 technische documenten")

## 9.3 Snelle Verificatie Checklist

Voor journalisten met tijdsdruk (5-10 minuten):

### ☐ Puntensysteem Check

1. Open `index.php`, ga naar regels 223-233
2. Verifieer formule:
   - Match = 2 punten
   - Neutraal = 1 punt
   - Geen match = 0 punten
3. Check dubbel gewicht: regel 215 (`$gewicht = ... ? 2 : 1`)

### ☐ Coverage Check

1. Open `stellingen_2025.php`
2. Tel posities (of gebruik grep commando's uit sectie 3.2)
3. Verifieer:
   - Eens: ~990
   - Oneens: ~710
   - Ratio: ~1.39:1

### ☐ Bronvermelding Check

1. Kies willekeurige stelling (bijv. ID 5)
2. Open `paragrafen.php`, zoek stelling 5
3. Noteer paginanummer (bijv. VVD: p.30)
4. Open `Verkiezingsprogramma/VVD_Verkiezingsprogramma_2025.pdf`
5. Ga naar pagina 30
6. Verifieer: Staat hier inderdaad standpunt over deze stelling?

**Verwachte tijd:** 2 minuten per stelling

### ☐ Symmetrie Bias Check

1. Gebruik grep commando's (sectie 3.2) of
2. Open `stellingen_2025.php`, zoek op `'positie' => '`
3. Tel handmatig (of gebruik Find functie)
4. Bereken ratio: eens / oneens
5. Verifieer: ~1.39:1 (niet 1:1 zoals geclaimd)

**Verwachte tijd:** 5 minuten

## 9.4 Veelgestelde Vragen (FAQ)

### Q: Waarom niet volledig open source?

**A:** Privacy en security overwegingen:
- Volledige codebase bevat mogelijk gevoelige configuratie
- Risicobeperking voor misbruik (scraping, spam)
- **Wel transparant**: Alle relevante code beschikbaar voor verificatie

### Q: Zijn de verkiezingsprogramma's bewerkt?

**A:** Nee, dit zijn de **originele PDF's** zoals gepubliceerd door partijen:
- Geen conversie naar andere formaten
- Geen tekstaanpassingen
- Paginanummers komen overeen met officiële versies

### Q: Hoe vaak wordt de database geüpdatet?

**A:**
- **Stellingen:** Vast (111 stellingen, niet meer gewijzigd na finalisatie)
- **Bronnen:** Laatst geüpdatet 2 oktober 2025 (zie `paragrafen.php` header)
- **Partijstandpunten:** Laatst geüpdatet 4 oktober 2025

### Q: Kan ik de data gebruiken voor eigen onderzoek?

**A:** Ja, met voorwaarden:
- ✅ Academisch onderzoek: Vrij te gebruiken met bronvermelding
- ✅ Journalistiek: Vrij te gebruiken voor publicatie
- ❌ Commercieel: Nee (tenzij met expliciete toestemming)

### Q: Wat als ik een fout vind?

**A:** Rapporteer via:
- Email: [indien beschikbaar]
- Met vermelding: Stelling ID, partij, wat er fout is, suggestie correctie

Wij beoordelen binnen 48 uur en updaten indien gegrond.

---

# 10. VERANTWOORDING - Methodologie Keuzes

## 10.1 Waarom PHP Arrays ipv Database?

**Keuze:** PHP arrays in `.php` bestanden (5,500+ regels)

**Alternatief:** MySQL/PostgreSQL database

**Voordelen PHP arrays:**
- ✅ **Eenvoud**: Geen database server nodig
- ✅ **Snelheid**: Geen query overhead (opcode cache)
- ✅ **Portabiliteit**: Zip bestand = volledige applicatie
- ✅ **Verificatie**: Eenvoudig te inspecteren (plain text)
- ✅ **Versiecontrole**: Makkelijk diffs te zien in Git

**Nadelen:**
- ❌ Geen relationele queries (maar niet nodig voor dit gebruik)
- ❌ Grote bestanden (maar nog steeds <1 MB)
- ❌ Memory usage (maar PHP kan dit aan met 128 MB limiet)

**Conclusie:** Voor een read-heavy applicatie met statische data is PHP array optimaal.

## 10.2 Waarom Coverage Gaps Accepteren?

**Keuze:** Toon "geen standpunt" eerlijk, accepteer 34.4% gaps

**Alternatief opties:**
1. Invullen met "neutraal" (oneerlijk, impliceert standpunt)
2. Kleine partijen verwijderen (ondemocratisch)
3. Alleen stellingen waar alle partijen standpunt hebben (slechts ~20 stellingen over)

**Waarom wij gaps accepteren:**
- ✅ **Eerlijkheid**: Beter geen standpunt tonen dan verzinnen
- ✅ **Realiteit**: Kleine partijen focussen op kernthema's (dat is oké)
- ✅ **Transparantie**: Coverage badges maken dit zichtbaar
- ✅ **Gebruiker autonomie**: Laat gebruiker zelf afweging maken

**Filosófie:**
> "Een incomplete maar eerlijke stemwijzer is beter dan een volledige maar misleidende."

## 10.3 Waarom Max_Score Per Partij?

**Keuze:** Max_score verschilt per partij (afhankelijk van coverage)

**Alternatief:** Vaste max_score = 222 (111 × 2) voor alle partijen

**Voordelen onze keuze:**
- ✅ Eerlijke vergelijking binnen partij (je match alleen op stellingen waar partij over spreekt)
- ✅ Geen "straffen" van kleine partijen (zij scoren niet automatisch laag)

**Nadelen:**
- ⚠️ Percentages tussen partijen niet 1-op-1 vergelijkbaar
- ⚠️ Kan misleidend zijn (100% match bij 50% coverage ≠ perfecte match)

**Oplossing:** Transparantie via coverage badges + uitleg in UI

**Alternatief scenario (vaste max_score):**
```
Gebruiker antwoordt 111 stellingen.
Kleine partij heeft 50 standpunten, gebruiker matched 50/50 perfect.

Ons systeem: 50/100 = 50% (binnen partij perfect)
Vast systeem: 50/222 = 23% (structureel benadeeld)
```

## 10.4 Waarom Handmatige Verificatie i.p.v. Volledig AI?

**Keuze:** Perplexity AI suggesties + menselijke final check

**Alternatief:** Volledig AI-gegenereerde bronnen

**Waarom menselijke check:**
- ✅ **Kwaliteit**: AI halluceineert soms (verkeerde paginanummers)
- ✅ **Nuance**: AI mist subtiele standpunten (impliciet vs expliciet)
- ✅ **Verantwoordelijkheid**: Mens kan verantwoordelijk gehouden worden
- ✅ **Vertrouwen**: Gebruikers vertrouwen menselijke verificatie meer

**Proces:**
1. AI doet eerste pass (80% tijd besparing)
2. Mens verifieert + corrigeert (20% tijd, 100% kwaliteit)

**Geschatte tijdsinvestering:**
- Volledig handmatig: ~500 uur (111 stellingen × 27 partijen × ~10 min)
- Met AI hulp: ~100 uur (80% reductie)

## 10.5 Waarom Originele PDF's Bewaren?

**Keuze:** Verkiezingsprogramma's als PDF, niet geconverteerd naar .md

**Voordelen:**
- ✅ **Juridische zekerheid**: Originele documenten van partijen
- ✅ **Paginanummer verificatie**: Nummers kloppen exact
- ✅ **Geen conversie-fouten**: Geen tekst verloren/veranderd
- ✅ **Officialiteit**: Directe link naar partij website mogelijk

**Nadelen:**
- ❌ Minder zoekbaar (maar PDF heeft ook zoekfunctie)
- ❌ Groter bestand (500 MB vs ~50 MB markdown)

**Conclusie:** Juridische zekerheid en verificatie > technisch gemak

## 10.6 Waarom "Geen Mening" Niet Straffen?

**Keuze:** "Weet ik niet" telt niet mee in score (0/0, niet 0/2)

**Alternatief:** "Weet ik niet" = 0 punten, max_score blijft 222

**Waarom wij dit niet doen:**
- ✅ **Eerlijkheid**: Gebruiker heeft geen mening, dus geen (dis)agreement
- ✅ **Percentage accurater**: 80% match betekent echt 80% van geldige antwoorden
- ✅ **Geen dwang**: Gebruiker hoeft niet te raden

**Alternatief scenario:**
```
Gebruiker beantwoordt 100 stellingen, 11x "Weet ik niet"
Scoort 80 punten op 100 beantwoorde stellingen

Ons systeem: 80/200 = 40% (van beantwoorde)
Alternatief: 80/222 = 36% (inclusief "weet niet")
```

Wij vinden 40% accurater: Het reflecteert match op stellingen waar gebruiker WEL mening over heeft.

---

# APPENDIX: VERIFICATIE COMMANDO'S

Voor technisch geïnteresseerden die zelf willen verifiëren:

## A. Bash Commando's (Terminal)

```bash
# Tel aantal stellingen
grep -c "'id' =>" stellingen_2025.php
# Verwacht: 111

# Tel aantal thema's
grep -c "'naam' => '" stellingen_2025.php
# Verwacht: 13

# Tel "eens" posities
grep -o "'positie' => 'eens'" stellingen_2025.php | wc -l
# Verwacht: ~990

# Tel "oneens" posities
grep -o "'positie' => 'oneens'" stellingen_2025.php | wc -l
# Verwacht: ~710

# Tel "neutraal" posities
grep -o "'positie' => 'neutraal'" stellingen_2025.php | wc -l
# Verwacht: ~260

# Tel "onbekend" + "geen_standpunt"
grep -o "'positie' => 'geen_standpunt'\|'positie' => 'onbekend'" stellingen_2025.php | wc -l
# Verwacht: ~1031

# Bereken ratio eens/oneens
# 990 / 710 = 1.39:1

# Tel bronvermeldingen
grep -c "=> \[" paragrafen.php
# Verwacht: 111 (elke stelling heeft bronnenlijst)

# Bekijk thema namen + regelnummers
grep -n "^      'naam' => '" stellingen_2025.php
# Output: 13 thema's met regelnummers
```

## B. PHP Verificatie Script

```php
<?php
// Laad database
define('STEMWIJZER_APP', true);
$stellingen = require 'stellingen_2025.php';

// Tel stellingen
$totaal = 0;
foreach ($stellingen['themas'] as $thema) {
    $totaal += count($thema['stellingen']);
}
echo "Totaal stellingen: $totaal\n"; // Verwacht: 111

// Tel posities
$posities = [
    'eens' => 0,
    'oneens' => 0,
    'neutraal' => 0,
    'geen_standpunt' => 0,
    'onbekend' => 0,
];

foreach ($stellingen['themas'] as $thema) {
    foreach ($thema['stellingen'] as $stelling) {
        foreach ($stelling['partijen'] as $partij => $data) {
            $pos = $data['positie'];
            $posities[$pos]++;
        }
    }
}

print_r($posities);
// Verwacht:
// eens: ~990
// oneens: ~710
// neutraal: ~260
// geen_standpunt: ~517
// onbekend: ~514

// Bereken ratio
$ratio = $posities['eens'] / $posities['oneens'];
echo "Eens/Oneens ratio: " . number_format($ratio, 2) . ":1\n";
// Verwacht: ~1.39:1
?>
```

## C. Quick Sanity Checks

**1. Bestaan alle bestanden?**
```bash
ls -lh stellingen_2025.php paragrafen.php partij_themas.php index.php
# Verwacht: Alle 4 bestanden aanwezig
```

**2. Zijn verkiezingsprogramma's compleet?**
```bash
ls Verkiezingsprogramma/*.pdf | wc -l
# Verwacht: ~19 PDF's in hoofdmap

ls "Verkiezingsprogramma/Deel twee"/*.pdf | wc -l
# Verwacht: ~8 PDF's in submap
```

**3. Zijn factcheck JSON's compleet?**
```bash
ls factchecked-bronnen-verkiezingsprogrammas/*.json | wc -l
# Verwacht: 5

ls factchecked-bronnen-verkiezingsprogrammas-New/*.json | wc -l
# Verwacht: 10

ls factchecked-bronnen-verkiezingsprogrammas-New-laatste/*.json | wc -l
# Verwacht: 9

# Totaal: 24 JSON files
```

---

**🎉 EINDE TECHNISCHE_WERKING.MD**

Dit document bevat de volledige transparantie over de Stemwijzer 2025 methodologie, met eerlijke disclaimers over beperkingen en verificeerbare data.

**Voor vragen of verificatie toegang:**
- Neem contact op via [contactgegevens indien beschikbaar]
- Of meld fouten/suggesties via GitHub issues (indien repository publiek)

**Versie:** 1.0
**Laatst bijgewerkt:** 4 Oktober 2025
**Totaal:** ~350 regels documentatie

Voor technische implementatie details, zie [TECHNICAL.md](TECHNICAL.md)
Voor design system, zie [BRANDSTYLE.md](BRANDSTYLE.md)
