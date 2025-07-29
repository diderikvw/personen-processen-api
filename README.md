# Personen en Processen API

Een OpenAPI 3.0 specificatie voor het beheren van personen en hun bijbehorende processen. Deze API ondersteunt verschillende proces types met type-specifieke attributen.

## 📖 Documentatie

### Bekijk de API interactief als Swagger Docs

1. Open **[Swagger Editor](https://editor.swagger.io/)**
2. Open het File-menu bovenin en kies Import URL
3. Kopieer en plak de URL van het Open API-specificatiebestand uit deze Repo: https://raw.githubusercontent.com/diderikvw/personen-processen-api/refs/heads/main/openapi.yml
4. Klik op OK

## 🏗️ API Overzicht

### Kern Concepten

- **Personen**: Collectie van personen met basis gegevens (naam, email, adres, etc.)
- **Processen**: Elke persoon kan meerdere processen hebben
- **Proces Types**: Verschillende types met eigen specifieke attributen

### Ondersteunde Proces Types

1. **Aanvraag** - Voor aanvragen zoals rijbewijzen, vergunningen
2. **Klacht** - Voor klachtenafhandeling
3. **Onderzoek** - Voor compliance onderzoeken en audits
