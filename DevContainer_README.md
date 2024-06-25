# Flask Webanwendung Dev Container

Dieses Projekt ist eine einfache Flask-Webanwendung mit SQLite-Datenbankintegration. Der Dev-Container ist so konfiguriert, dass er eine einheitliche Entwicklungsumgebung bereitstellt.

## Voraussetzungen
- Visual Studio Code
- Docker

## Schritte zum Starten des Projekts im Dev-Container
1. Öffnen Sie das Projekt in VSCode.
2. Öffnen Sie die Kommando-Palette (F1) und wählen Sie `Dev Containers: Reopen in Container`.
3. Warten Sie, bis der Container erstellt und gestartet wurde.
4. Drücken Sie F5, um die Anwendung zu starten.

Die Anwendung ist jetzt unter `http://localhost:5000` verfügbar.

## Debugging
- Setzen Sie Breakpoints wie gewohnt in Ihrer Python-Datei.
- Drücken Sie F5 zum Starten des Debuggings.

## Struktur der `.env` Datei
Die `.env` Datei sollte folgendes Format haben:

```plaintext
FLASK_APP=app.py
FLASK_ENV=development
DATABASE_URL=sqlite:///test.db
```



### 2. Automatisierte Installation

**`Dockerfile`**:

```Dockerfile
FROM python:3.12

WORKDIR /workspace

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

CMD ["flask", "run", "--host=0.0.0.0"]
