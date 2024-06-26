# FastAPI Dev Container

Dieses Projekt ist eine einfache FastAPI-Webanwendung. Der Dev-Container ist so konfiguriert, dass er eine einheitliche Entwicklungsumgebung bereitstellt.

## Voraussetzungen
- Visual Studio Code
- Docker

## Schritte zum Starten des Projekts im Dev-Container
1. Öffnen Sie das Projekt in VSCode.
2. Öffnen Sie die Kommando-Palette (F1) und wählen Sie `Dev Containers: Reopen in Container`.
3. Warten Sie, bis der Container erstellt und gestartet wurde.
4. Drücken Sie F5, um die Anwendung zu starten.

Die Anwendung ist jetzt unter `http://localhost:8000` verfügbar.

## Debugging
- Setzen Sie Breakpoints wie gewohnt in Ihrer Python-Datei.
- Drücken Sie F5 zum Starten des Debuggings.

## Struktur der `.env` Datei
Die `.env` Datei sollte folgendes Format haben:

```plaintext```
DATABASE_URL=sqlite:///test.db


### 6. docker-compose.yml
Erstelle ein `docker-compose.yml`, um das Projekt in der Produktion zu starten.

**docker-compose.yml**:

```yaml```
version: '3.8'

services:
  web:
    build: .
    ports:
      - "8000:8000"
    environment:
      - DATABASE_URL=sqlite:///prod.db
    volumes:
      - .:/workspace
