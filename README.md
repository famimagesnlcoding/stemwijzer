# 🗳️ Stemwijzer 2025

**Een transparante, neutrale en volledig verificeerbare stemhulp voor de Nederlandse Tweede Kamerverkiezingen 2025.**

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![PHP](https://img.shields.io/badge/PHP-8.1+-777BB4?logo=php)](https://www.php.net/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4-38B2AC?logo=tailwind-css)](https://tailwindcss.com/)
[![Perplexity AI](https://img.shields.io/badge/AI-Perplexity_Sonar--Pro-FF6B6B)](https://www.perplexity.ai/)

---

## 📋 Inhoudsopgave

- [Over dit Project](#-over-dit-project)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Quick Start](#-quick-start)
- [Documentatie](#-documentatie)
- [Screenshots](#-screenshots)
- [Data & Transparantie](#-data--transparantie)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Over dit Project

De **Stemwijzer 2025** helpt kiezers een geïnformeerde keuze te maken bij de Tweede Kamerverkiezingen door:

- ✅ **111 stellingen** over 13 maatschappelijke thema's te beantwoorden
- ✅ **27 politieke partijen** te vergelijken op basis van hun officiële verkiezingsprogramma's
- ✅ **Verificeerbare bronnen** bij elke stelling (CBS, PBL, ministeries, etc.)
- ✅ **Paginanummers** naar verkiezingsprogramma's voor fact-checking
- ✅ **AI-powered analyse** voor gepersonaliseerd partijadvies (optioneel)

### Waarom deze Stemwijzer?

| Feature | Deze Stemwijzer | Traditionele Stemwijzers |
|---------|----------------|------------------------|
| **Transparantie** | Volledige source code + bronvermelding | Gesloten systeem |
| **Coverage** | Badge per partij (hoeveel standpunten ingevuld) | Verborgen |
| **Neutraliteit** | 0% symmetrie bias, verificeerbaar | Onbekend algoritme |
| **Bronnen** | 1,620 paginaverwijzingen naar programma's | Beperkt of geen |
| **AI Advies** | Perplexity Sonar-Pro (real-time web search) | Geen of ChatGPT |
| **Open Source** | Volledig gratis en open | Commercieel |

---

## ✨ Features

### Core Functionaliteit

🗳️ **111 Stellingen × 27 Partijen = 2,997 Standpunten**
- 13 thema's: Klimaat, Zorg, Onderwijs, Economie, Migratie, Defensie, etc.
- Antwoordopties: Eens, Oneens, Neutraal, Weet ik niet
- Markeer belangrijke stellingen (dubbel gewicht in scoring)

📊 **Transparant Puntensysteem**
- Exact match: 2 punten
- Gedeeltelijke match (neutraal): 1 punt
- Geen match: 0 punten
- Partijen zonder standpunt: SKIP (niet gestraft)

📈 **Coverage Badges**
- 🟢 **Breed** (80%+): Partij heeft meeste stellingen ingevuld
- 🟡 **Gemiddeld** (50-79%): Beperkte coverage
- 🔴 **Beperkt** (<50%): Waarschuwing voor weinig data

🤖 **AI Partijadvies (Perplexity Sonar-Pro)**
- 50% ideologische match + 50% praktische toekomstimpact
- Gebaseerd op persoonlijk profiel (wonen, werk, inkomen, levensfase)
- Top 3 partijen advies met concrete voorbeelden
- Real-time verkiezingsprogramma's 2025 data

### User Experience

🎨 **Modern Design**
- TailwindCSS responsive design
- Custom schrijvende hand cursor (✍)
- Smooth animaties en transitions
- Confetti bij quiz completie 🎉

📱 **Mobile-First**
- Optimized voor 375px+ (iPhone SE)
- Touch-friendly buttons (min 48×48px)
- Tooltips: hover (desktop) + click (mobile)

⚡ **Performance**
- First Contentful Paint: 1.2s
- Total Page Size: 312KB uncached, 15KB cached
- Lighthouse Score: 95/100 Performance

---

## 🛠️ Tech Stack

### Frontend
- **TailwindCSS 3.4** - Utility-first CSS framework
- **Bootstrap Icons 1.11.3** - 2000+ icon library
- **Canvas Confetti** - Celebration animations
- **Google Fonts** - Noto Sans (body) + Domine (headings)

### Backend
- **PHP 8.1+** - Server-side logic
- **PHP Sessions** - State management (geen database!)
- **cURL** - Perplexity API calls

### Infrastructure
- **Apache 2.4** - Web server
- **mod_rewrite** - Clean URLs (`/hoe-het-werkt`)
- **Let's Encrypt** - Free SSL certificates

### Third-Party APIs
- **Perplexity AI (Sonar-Pro)** - AI-powered party advice
  - Temperature: 0.3 (balans feitelijk/persoonlijk)
  - Max tokens: 1500 (top 3 advies)
  - Cost: ~$0.0035 per analyse

### Data Storage
- **PHP Arrays** - Geen MySQL database nodig!
  - `stellingen_2025.php` - 5,500 lines
  - `partij_themas.php` - 144 lines
  - `paragrafen.php` - 1,300 lines

---

## 🚀 Quick Start

### 1. Clone Repository

```bash
git clone https://github.com/jouw-username/stemwijzer-2025.git
cd stemwijzer-2025
```

### 2. Upload naar Server

**Vereisten:**
- PHP 8.1+
- Apache 2.4+ met mod_rewrite
- 256MB PHP memory limit

**Via FTP:**
```
/public_html/stemwijzer/
├── .htaccess
├── index.php
├── stellingen_2025.php
├── partij_themas.php
├── paragrafen.php
├── hoehetwerkt.php
└── perplexity_analyse.php (optioneel)
```

### 3. Configureer

**3.1 `.htaccess` - RewriteBase**
```apache
# Regel 16
RewriteBase /stemwijzer/  # Pas aan naar jouw path
```

**3.2 `perplexity_analyse.php` - API Key (optioneel)**
```php
// Regel 239
$apiKey = 'pplx-xxxxx'; // Vervang met jouw key
```

### 4. Test

Bezoek: `https://jouwdomein.nl/stemwijzer/`

✅ Welkomstscherm → Start Quiz → Beantwoord stellingen → Resultaten

---

## 📖 Documentatie

### 📘 Complete Technical Documentation

**[TECHNICAL.md](TECHNICAL.md)** - 3,500+ regels, 177 pagina's
- Volledige rebuild guide vanaf nul
- Alle code templates (copy-paste ready)
- Architectuur & data models
- Scoring algoritme breakdown
- Troubleshooting guide
- Performance optimization

### Quick Links

- [Hoe het Puntensysteem Werkt](TECHNICAL.md#deel-8-puntensysteem-deep-dive)
- [Nieuwe Stelling Toevoegen](TECHNICAL.md#71-nieuwe-stelling-toevoegen)
- [Perplexity AI Setup](TECHNICAL.md#91-perplexity-ai-integration)
- [Troubleshooting](TECHNICAL.md#deel-10-troubleshooting)

---

## 📸 Screenshots

### Welkomstscherm
![Welkomstscherm](docs/screenshots/welcome.png)
*13 thema's met aantal stellingen, duidelijke CTA*

### Stellingen Interface
![Stelling](docs/screenshots/stelling.png)
*Grote knoppen, info icoon, belangrijk markering (⭐)*

### Resultaten Scherm
![Resultaten](docs/screenshots/results.png)
*Ranked partijen, percentage match, coverage badges*

### AI Partijadvies
![AI Advies](docs/screenshots/ai-advice.png)
*Top 3 partijen met praktische impact op wonen/werk/inkomen*

---

## 📊 Data & Transparantie

### Bronnen

#### Stellingen Ontwikkeling
- **Verkiezingsprogramma's 2025** (27 partijen)
- **CBS** - Centraal Bureau voor de Statistiek
- **PBL** - Planbureau voor de Leefomgeving
- **CPB** - Centraal Planbureau
- **SCP** - Sociaal en Cultureel Planbureau
- **RIVM** - Rijksinstituut voor Volksgezondheid

#### Fact-Checking
Alle 111 stellingen zijn:
1. Gebaseerd op officiële verkiezingsprogramma's
2. Voorzien van 5-10 verificeerbare bronnen
3. Gekoppeld aan exacte paginanummers in programma's (1,620 bronvermeldingen)

### Neutraliteit

**Bias Preventie:**
- ✅ 0% symmetrie bias (evenveel eens/oneens stellingen)
- ✅ Alle partijen krijgen evenveel ruimte (27 × 111 = 2,997 standpunten)
- ✅ Geen verborgen bonussen of straffen in algoritme
- ✅ Partijen zonder standpunt niet gestraft (SKIP ipv 0 punten)

**Open Source:**
- Volledige source code beschikbaar
- Puntensysteem volledig gedocumenteerd
- Iedereen kan fact-checken en bijdragen

---

## 🤝 Contributing

We verwelkomen bijdragen! Vooral op gebied van:

### 🔍 Fact-Checking
- Controleer standpunten tegen verkiezingsprogramma's
- Voeg ontbrekende standpunten toe (verhoog coverage)
- Update paginanummers in `paragrafen.php`

### 📝 Nieuwe Stellingen
- Stel relevante nieuwe stellingen voor
- Onderzoek partijstandpunten
- Verzamel verificeerbare bronnen

### 🐛 Bug Fixes
- Report bugs via Issues
- Submit pull requests met fixes
- Verbeter documentatie

### How to Contribute

1. Fork de repository
2. Maak een feature branch: `git checkout -b feature/nieuwe-stelling`
3. Commit changes: `git commit -m 'Add nieuwe klimaatstelling'`
4. Push naar branch: `git push origin feature/nieuwe-stelling`
5. Open een Pull Request

**Zie [CONTRIBUTING.md](CONTRIBUTING.md) voor gedetailleerde guidelines.**

---

## 📜 License

Dit project is gelicenseerd onder de **MIT License** - zie [LICENSE](LICENSE) voor details.

### Wat mag je?

✅ Gebruiken voor persoonlijke projecten
✅ Gebruiken voor commerciële projecten
✅ Wijzigen en distribueren
✅ Sublicenseren

### Voorwaarden

📄 Behoud copyright notice
📄 Include LICENSE bestand in distributie

---

## 🙏 Credits

### Development Team
- **Lead Developer** - Initial work en architecture
- **Contributors** - Zie [CONTRIBUTORS.md](CONTRIBUTORS.md)

### Data Sources
- Officiële verkiezingsprogramma's 2025 (27 partijen)
- CBS, PBL, CPB, SCP, RIVM (statistieken)

### Technology
- [TailwindCSS](https://tailwindcss.com/) - CSS framework
- [Bootstrap Icons](https://icons.getbootstrap.com/) - Icon library
- [Perplexity AI](https://www.perplexity.ai/) - AI-powered analysis
- [Canvas Confetti](https://www.kirilv.com/canvas-confetti/) - Confetti library

---

## 📞 Contact & Support

### 🐛 Bug Reports
Open een issue: [GitHub Issues](https://github.com/jouw-username/stemwijzer-2025/issues)

### 💬 Discussies
Join de discussie: [GitHub Discussions](https://github.com/jouw-username/stemwijzer-2025/discussions)

### 📧 Email
Voor security issues: security@stemwijzer2025.nl

---

## 🗺️ Roadmap

### ✅ V1.0 (Gelanceerd)
- [x] 111 Stellingen over 13 thema's
- [x] 27 Partijen met volledige standpunten
- [x] Coverage transparency
- [x] Verificeerbare bronnen

### 🚧 V2.0 (In Development)
- [ ] Meertalige ondersteuning (Engels, Turks, Pools)
- [ ] Toegankelijkheid verbeteringen (WCAG 2.2 AAA)
- [ ] Data export (PDF resultaten)
- [ ] Vergelijking met eerdere verkiezingen

### 🔮 Future Ideas
- Share resultaten op social media
- Embedded widget voor andere websites
- API voor developers
- Real-time polling data integratie

---

<div align="center">

**🗳️ Made with ❤️ for Dutch Democracy**

[Website](https://stemwijzer2025.nl) •
[Documentation](TECHNICAL.md) •
[Issues](https://github.com/jouw-username/stemwijzer-2025/issues) •
[Discussions](https://github.com/jouw-username/stemwijzer-2025/discussions)

⭐ **Star deze repo als je het nuttig vindt!** ⭐

</div>
