# Changelog

Alle belangrijke wijzigingen aan dit project worden gedocumenteerd in dit bestand.

Het formaat is gebaseerd op [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
en dit project volgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2024-01-29

### Added
- Initiële versie van de Personen en Processen API
- Ondersteuning voor drie proces types:
  - Aanvraag processen met specifieke velden voor documentatie en kosten
  - Klacht processen met beschrijving en oplossingsvoorstellen
  - Onderzoek processen met methodologie en bevindingen
- Complete CRUD operaties voor personen en processen
- JWT Bearer token authenticatie
- Paginatie ondersteuning voor personen collectie
- Filtering van processen op type
- Nederlandse postcode validatie
- Uitgebreide error handling met gestandaardiseerde error responses
- OpenAPI 3.0.3 specificatie met volledige validatie
- Voorbeeld JSON bestanden voor alle proces types
- GitHub Actions workflow voor automatische spec validatie

### Technical Details
- RESTful API design met logische URL structuren
- Polymorphic process types using `oneOf` construct
- Comprehensive input validation and constraints
- Proper HTTP status codes en response structures
- Support voor optionele velden en default waardes

## [0.9.0] - 2024-01-28 (Beta)

### Added
- Basis API structuur
- Personen endpoints
- Simpele proces ondersteuning

### Fixed
- OpenAPI spec validatie fouten
- Structural errors in schema definitions

---

## Versioning Strategy

We gebruiken [Semantic Versioning](https://semver.org/) voor version numbering:

- **MAJOR version** - incompatible API changes
- **MINOR version** - backwards-compatible functionality additions  
- **PATCH version** - backwards-compatible bug fixes

## Migration Guide

### Van versie 0.9.x naar 1.0.0

#### Breaking Changes
- Proces schema heeft nieuwe `typeSpecifiekeData` veld structuur
- Oude `aanvraagspecifiek`, `klachtspecifiek` velden zijn vervangen
- Authenticatie is nu verplicht voor alle endpoints

#### Migration Steps
1. Update je client code om nieuwe schema structuur te gebruiken
2. Implementeer JWT token authenticatie
3. Test je integraties met nieuwe voorbeeld bestanden

#### New Features
- Drie verschillende proces types volledig ondersteund
- Verbeterde error handling
- Paginatie voor betere performance