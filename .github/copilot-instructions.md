<!--
Kort, taakgerichte instructies voor AI-codeagents die in deze repo werken.
Deze file is bedoeld om een agent snel productief te maken: welke bestanden te openen,
welke ontdekkingsstappen te volgen en welke repo-specifieke gewoonten te respecteren.
-->

# Copilot / AI-agent richtlijnen

- **Doel:** Deze repository is momenteel zeer minimaal (alleen [README.md](README.md)).
  Beoordeel eerst of er überhaupt broncode of build-configuratie aanwezig is.

- **Snelstart ontdekking:**
  - Zoek naar project-manifesten: `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Makefile`.
  - Zoek naar mappen `src/`, `app/`, `cmd/`, of `pkg/` en naar testmappen `tests/` of `__tests__/`.
  - Commando-voorbeeld (lokale sessie):
    - `rg -n --hidden "package.json|pyproject.toml|Cargo.toml|go.mod|Makefile|src/|tests/" || true`

- **Big picture & architectuur (hoe te bepalen):**
  - Als er een `package.json` is: kijk naar `scripts` en `main`/`module` velden om entrypoints en test-commands te vinden.
  - Voor Python: als er `pyproject.toml` of `requirements.txt` is, controleer `tool.poetry` of `build-system` secties.
  - Als de repo geen manifests heeft, rapporteer dat en vraag naar de beoogde taal/stack.

- **Project-specifieke conventies (ontdekt):**
  - Huidige snapshot bevat alleen [README.md](README.md). Er zijn geen project-specifieke codeconventies om te volgen.
  - Als je componenten toevoegt, documenteer ze kort in de README en update deze instructiefile.

- **Ontwikkel- en testworkflows:**
  - Gebruik beschikbare manifest-scripts (npm/poetry/cargo/go) als primaire commands.
  - Als er geen scripts zijn, stel voorstelcommando's voor (bijv. `npm init` / `python -m venv .venv`), maar wacht op bevestiging voordat je veranderingen pusht.

- **Integratiepunten & afhankelijkheden:**
  - Zoek naar CI/CD config: `.github/workflows/`, `.gitlab-ci.yml`, `Dockerfile`.
  - Als je externe services verwacht, vermeld dat de agent moet vragen naar API-keys/credentials en nooit secrets in de repo te plaatsen.

- **Wanneer wijzigingen committen:**
  - Maak kleine, gefocuste commits met duidelijke boodschappen.
  - Voeg tests of minimaal een eenvoudige sanity-check toe bij functionele wijzigingen.
  - Push of open PRs alleen na expliciete bevestiging van een menselijke reviewer.

- **Melding van ontbrekende informatie:**
  - Als kerninformatie ontbreekt (taal, build command, test command), voeg dan een kort `ISSUE.md` voorstel toe of vraag de gebruiker direct.

- **Voorbeelden (concrete hints):**
  - "Als je `package.json` vindt met `scripts.test` — run `npm test` lokaal en rapporteer failures." 
  - "Als `pyproject.toml` aanwezig is — zoek `tool.poetry.scripts` of `entry-points` voor CLI entrypoints."

- **Samenvoegregels (merge guidance voor deze file):**
  - Als er al een `.github/copilot-instructions.md` bestaat, behoud bestaande secties die specifieke commando's of secrets-policy noemen.
  - Voeg nieuwe ontdekkingen toe als korte bullets; houd file compact (20–50 regels).

---
_Vraag_: wil je dat ik testscripts of detectiestappen (bijv. `detect-language.sh`) toevoeg om toekomstige agents automatisch te laten detecteren welke stack gebruikt wordt?
