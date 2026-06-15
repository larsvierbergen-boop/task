# Vault PWA

Mobiele taakbeheer voor je Obsidian vault — Annado-compatibele syntax, werkt via GitHub als brug.

## Hoe het werkt

```
Obsidian (Mac) → obsidian-git plugin → GitHub repo
                                            ↕ GitHub API
                                       Vault PWA (Netlify)
                                            ↓
                                       iPhone / Android
```

## Deploy op Netlify

1. Zet deze map in een GitHub repo
2. Ga naar netlify.com → "Add new site" → "Import from Git"
3. Kies je repo, build command leeg laten, publish directory: `.`
4. Deploy

## Eerste gebruik

1. Ga naar je Netlify URL op je telefoon
2. Vul in:
   - **GitHub Token**: maak aan via github.com/settings/tokens (scope: `repo`)
   - **Gebruikersnaam**: je GitHub username
   - **Repository**: de naam van je vault repo
   - **Daily Notes map**: bijv. `00. Daily Notes`
   - **Datum formaat**: bijv. `00. Daily Notes/YYYY-MM-DD`
3. Installeer als app: Safari → Deel → "Zet op beginscherm"

## Vault sync instellen

Installeer de **Obsidian Git** plugin in Obsidian:
- Settings → Community Plugins → Obsidian Git
- Stel auto-commit in op bijv. elke 10 minuten
- Push naar je private GitHub repo

## Task syntax (Annado-compatibel)

```
- [ ] Taak titel @when(morgen) @time(09:00) [[Project]] !(1) #tag @due(2025-03-01)
```

| Annotatie | Voorbeeld | Betekenis |
|---|---|---|
| `@when(...)` | `@when(2025-03-15)` | Geplande datum |
| `@due(...)` | `@due(2025-03-01)` | Deadline |
| `@time(...)` | `@time(09:00)` | Tijdstip |
| `@duration(...)` | `@duration(1h30m)` | Duur |
| `[[WikiLink]]` | `[[Project X]]` | Project |
| `!(1-3)` | `!(1)` | Prioriteit |
| `#tag` | `#werk` | Tag |

### When-waarden
- `inbox` — ongepland
- `today` / `vandaag` — vandaag
- `anytime` / `altijd` — flexibel
- `someday` / `ooit` — backlog
- `YYYY-MM-DD` — specifieke datum

## Features v1

- ✅ Taken laden uit hele vault
- ✅ Vandaag / Gepland / Inbox / Klaar tabs
- ✅ Taak afvinken (schrijft terug naar markdown)
- ✅ When en prioriteit aanpassen
- ✅ Quick Add (schrijft naar daily note)
- ✅ Annado-syntax volledig compatibel
- ✅ Installeerbaar als PWA

## Roadmap

- [ ] Offline support (Service Worker)
- [ ] Deadline weergave en filtering
- [ ] Tags filteren
- [ ] Zoeken
- [ ] Terugkerende taken
- [ ] Agenda view
