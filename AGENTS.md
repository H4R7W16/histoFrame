# AGENTS.md

Du arbeitest im Repository `chronotop`. Der historische Name `histoFrame` bezeichnet eine ältere Arbeitskopie desselben Projekts und ist kein eigenes Repository.

## Arbeitsmodell

- Quellcode und Versionshistorie werden ausschließlich über GitHub synchronisiert.
- Jedes Gerät verwendet einen eigenen lokalen Clone unter `%USERPROFILE%/AI-Workspace-Local/Repos/chronotop`.
- Lege diesen Checkout, `.git`, `node_modules`, lokale Datenbanken, Caches und Builds nicht in OneDrive ab.
- Der optionale fachliche und organisatorische Kontext liegt im separat angebundenen OneDrive-`AI-Workspace`.

Wenn der AI-Workspace als zusätzlicher Codex-Ordner verfügbar ist, lies für die Projektzuordnung:

- `Shared/Codex/Projects/Chronotop - Lokales Codex-Projektprofil.md`

Für fachliche Geschichtsarbeit lade anschließend nur die einschlägigen Dateien aus:

- `Vault/40_Projekte/Geschichte-Kursstufe/`

Wenn der zusätzliche Ordner fehlt, arbeite mit den Repository-Dateien weiter und benenne fehlenden Workspace-Kontext ausdrücklich. Erfinde keinen OneDrive-Pfad.

## Git-Regeln

Vor jeder Arbeit:

```powershell
git status --short --branch
git fetch --prune
git pull --ff-only
```

- Wenn Fetch oder Fast-forward-Pull scheitert, nicht pushen; zuerst Authentifizierung, Upstream oder Konflikt klären.
- Vor einem Gerätewechsel den aktiven Branch pushen. Auf dem anderen Gerät zuerst denselben Branch auschecken und aktualisieren.
- Nicht gleichzeitig auf zwei Geräten denselben Branch verändern. Für parallele Arbeit getrennte Branches verwenden und einen Integrationspunkt benennen.
- Kein Force-Push und kein History-Rewrite ohne ausdrückliche Nutzerfreigabe.
- `.git` nie manuell bearbeiten.

## Projektstart und Prüfung

Voraussetzungen: Node.js ab Version 20 und npm ab Version 9.

```powershell
npm install
npm run seed:local
npm run dev
```

Für Produktcode mindestens die betroffenen Tests und den Build ausführen. Verfügbare Gesamtprüfungen:

```powershell
npm test
npm run build
```

End-to-End-Tests nur ausführen, wenn Umfang und lokale Voraussetzungen dies rechtfertigen. Keine Secrets, `.env`, `node_modules`, lokalen Datenbanken, Caches oder Build-Ausgaben committen.

## Handoff

Nach relevanten Änderungen Branch, Commit, Push-Status, ausgeführte Prüfungen und offene Punkte dokumentieren. Wenn Workspace-Planung betroffen ist, die dortige Task-Notiz, Initiative, Kanban und Codex Session Summary aktualisieren.
