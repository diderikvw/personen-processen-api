# Personen en Processen API

Een OpenAPI 3.0 specificatie voor het beheren van personen en hun bijbehorende processen. Deze API ondersteunt verschillende proces types met type-specifieke attributen.

## 📖 Documentatie

### Interactieve Documentatie

- **[Swagger Editor](https://editor.swagger.io/?url=https://raw.githubusercontent.com/diderikvw/personen-processen-api/main/openapi.yaml)** - Bekijk de API interactief

### Lokaal bekijken

```bash
# Clone de repository
git clone https://github.com/JOUW-USERNAME/personen-processen-api.git
cd personen-processen-api

# Open in Swagger Editor (lokaal)
npx @apidevtools/swagger-parser validate openapi.yaml
```

## 🏗️ API Overzicht

### Kern Concepten

- **Personen**: Collectie van personen met basis gegevens (naam, email, adres, etc.)
- **Processen**: Elke persoon kan meerdere processen hebben
- **Proces Types**: Verschillende types met eigen specifieke attributen

### Ondersteunde Proces Types

1. **Aanvraag** - Voor aanvragen zoals rijbewijzen, vergunningen
2. **Klacht** - Voor klachtenafhandeling
3. **Onderzoek** - Voor compliance onderzoeken en audits

## 🚀 Quick Start

### Basis URL

```
https://api.example.com/v1
```

### Authenticatie

Alle endpoints vereisen JWT Bearer authenticatie:

```bash
Authorization: Bearer <your-jwt-token>
```

### Voorbeeld Requests

#### Nieuwe persoon aanmaken

```bash
curl -X POST https://api.example.com/v1/personen \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d @examples/create-person.json
```

#### Proces toevoegen aan persoon

```bash
curl -X POST https://api.example.com/v1/personen/{persoonId}/processen \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d @examples/create-process-aanvraag.json
```

## 📁 Repository Structuur

```
├── openapi.yaml              # Hoofd OpenAPI specificatie
├── README.md                 # Deze documentatie
├── examples/                 # Voorbeeld JSON bestanden
│   ├── create-person.json
│   ├── create-process-aanvraag.json
│   ├── create-process-klacht.json
│   └── create-process-onderzoek.json
├── docs/                     # Aanvullende documentatie
│   ├── authentication.md
│   ├── error-handling.md
│   └── changelog.md
└── .github/
    └── workflows/
        └── validate-spec.yml  # CI/CD voor spec validatie
```

## 🔍 API Endpoints

### Personen

- `GET /personen` - Lijst alle personen
- `POST /personen` - Maak nieuwe persoon
- `GET /personen/{id}` - Haal specifieke persoon op
- `PUT /personen/{id}` - Update persoon
- `DELETE /personen/{id}` - Verwijder persoon

### Processen

- `GET /personen/{id}/processen` - Lijst processen van persoon
- `POST /personen/{id}/processen` - Voeg proces toe
- `GET /personen/{id}/processen/{procesId}` - Haal specifiek proces op
- `PUT /personen/{id}/processen/{procesId}` - Update proces
- `DELETE /personen/{id}/processen/{procesId}` - Verwijder proces

## 🛠️ Ontwikkeling

### Spec Valideren

```bash
# Met npm
npx @apidevtools/swagger-parser validate openapi.yaml

# Met Docker
docker run --rm -v $(pwd):/workspace \
  openapitools/openapi-generator-cli validate \
  -i /workspace/openapi.yaml
```

### Code Genereren

```bash
# Client code genereren (JavaScript)
npx @openapitools/openapi-generator-cli generate \
  -i openapi.yaml \
  -g javascript \
  -o ./generated/client

# Server stub genereren (Node.js)
npx @openapitools/openapi-generator-cli generate \
  -i openapi.yaml \
  -g nodejs-express-server \
  -o ./generated/server
```

## 📋 Validatie & Status

![Spec Validation](https://github.com/JOUW-USERNAME/personen-processen-api/workflows/Validate%20OpenAPI%20Spec/badge.svg)

Deze repository bevat GitHub Actions die automatisch de OpenAPI spec valideren bij elke commit.

## 🤝 Contributing

1. Fork de repository
2. Maak een feature branch (`git checkout -b feature/nieuwe-functie`)
3. Commit je wijzigingen (`git commit -am 'Voeg nieuwe functie toe'`)
4. Push naar de branch (`git push origin feature/nieuwe-functie`)
5. Maak een Pull Request

### Guidelines

- Volg de bestaande naamconventies
- Voeg voorbeelden toe voor nieuwe endpoints
- Update de documentatie
- Test je wijzigingen met Swagger Editor

## 📝 Changelog

Zie [CHANGELOG.md](docs/changelog.md) voor een overzicht van wijzigingen per versie.

## 📄 Licentie

Dit project valt onder de MIT licentie. Zie het `LICENSE` bestand voor details.

## 📞 Contact

Voor vragen of suggesties kun je:

- Een issue aanmaken in deze repository
- Contact opnemen via [email@example.com](mailto:email@example.com)

---

**Versie**: 1.0.0  
**Laatst bijgewerkt**: $(date +%Y-%m-%d)
