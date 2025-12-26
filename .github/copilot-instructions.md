<!--
Kort, taakgerichte instructies voor AI-codeagents die in deze repo werken.
Dit is een statische HTML/CSS-site – geen build tools, dependencies of complex architecture.
Focus op inhoud en styling aanpassingen.
-->

# Copilot / AI-agent richtlijnen

## 📋 Project overzicht
**verbose-fiesta** is een eenvoudige one-page profielsite voor Bram Verstraten (Backend Developer).
- **Taal/Stack:** Plain HTML5 + CSS3 (geen build tools, frameworks of dependencies)
- **Bestanden:** `index.html` (inhoud), `styles.css` (styling)
- **Doelgroep:** Portfolio/CV-site

## 🚀 Lokaal testen
```bash
python3 -m http.server 8000
# open http://localhost:8000 in je browser
```
Geen build-stap nodig. Wijzigingen verschijnen onmiddellijk na refresh.

## 🏗️ Architectuur
- **HTML structuur:** `<header>` (avatar + intro) → `<main>` met `.card` secties (Over mij, Technologieën, Samenvatting, Ervaring)
- **Styling:** CSS custom properties (`:root` variabelen) voor kleurenschema; minified opmaak
- **Responsive:** Mobile breakpoint op `560px` (flexbox aanpassingen)
- **Externe content:** GitHub avatar URL, links naar vostools.be & vulpp.be

## 📝 Wijzigingen guidelines
1. **Inhoud:** Update secties in `index.html` (h2-titels, p-teksten, li-items)
2. **Styling:** CSS-variabelen in `:root` wijzigen voor kleur/thema; media-query voor mobile aanpassen
3. **Links:** Controleer `href` en `rel="noreferrer"` bij externe verwijzingen
4. **Commits:** Korte boodschappen, bijv. "Update skills section" of "Adjust mobile padding"

## ⚠️ Opmerkingen
- **Geen testframework** – visuele verificatie is primair (browser preview)
- **Git-based preview:** GitHub Pages kan direct vanuit `main` deployen (geen build config nodig)
- **Taalvoorkeur:** Content is Nederlands; zorg voor consistentie in nieuwe tekst
