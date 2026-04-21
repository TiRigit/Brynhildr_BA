# Brynhildr_BA — Agent Instructions

## Projekt

- **Thema:** Brünhild/Brynhildr im Nibelungenlied und der Völsunga saga — komparatistische Figurenanalyse
- **Typ:** Bachelorarbeit, Institut für Germanistik, Abt. Literaturwissenschaft
- **Umfang:** ~25 Seiten Textteil (Deckblatt/Verzeichnisse zählen nicht)
- **KI-Policy:** Erlaubt mit Deklarationspflicht → `07_ki-log/`

## Sitzungsstart (immer in dieser Reihenfolge)

1. Lies `00_system/ba-memory.md` — aktueller Projektstand + offene Blocker
2. Prüfe aktuelle Phase (A–F) und wähle passende Skills
3. Lies das aktuelle Kapitel in `04_kapitel/` (falls Phase C läuft)

## Sitzungsende

Immer `/session-wrap-up` ausführen → ki-deklaration + Übergabe + openbrain.

## Memory-Schichten

| Schicht | Ort | Inhalt |
|---|---|---|
| Session | `CLAUDE.md` (diese Datei) | Stilregeln, Phase, Zitierformat |
| Projekt | `00_system/ba-memory.md` | Entscheidungen, Blocker, Quellen-Stand — *single source of truth* |
| Global | PostgreSQL `lab_results` via `/openbrain` | Session-Archiv, semantische Suche |

## Phasen & Skills

```
Phase A — Vorbereitung
  /brainstorming        01_brainstorming/ → 02_forschungsfrage/thesen.md
  /konzept              RQ + Gliederung  → 02_forschungsfrage/
  /zeitwaechter         Deadline-Check

Phase B — Quellenarbeit
  /observer             Pflicht vor /exzerpt
  /quellen-multilingual Zotero sync, Quelle eintragen (UP-Stil)
  /exzerpt              PDF → 03_quellen/sekundaerliteratur/exzerpte/<key>.md

Phase C — Rohtext
  /schreibstil          Coaching vor dem Schreiben
  /komparatistik        NL ↔ Saga Tabellen → 02_forschungsfrage/vergleiche/
  /kapitel-rohtext      Schreiben → 04_kapitel/  [observer automatisch integriert]

Phase D+E — Lektorat
  /pruefung             Logik + Stil eines Kapitels
  /ba-lektorat          5-Schritte → 05_lektorat/protokoll_<kap>.md
  /sprachkorrektur      Grammatik (LanguageTool lokal)
  /plagiatcheck         Zitatcheck + KI-Deklarations-Vollständigkeit

Phase F — Export
  /pandoc-export        Kapitel zusammenführen → 06_export/
  /ki-deklaration       finales Audit-Log → 07_ki-log/

Immer verfügbar
  /ki-deklaration       nach jeder Arbeitsphase (Pflicht)
  /session-wrap-up      Sitzungsende
  /ba-stats             Schnellübersicht: Wörter, Quellen, Fortschritt
  /recherche            intern (von observer/exzerpt/komparatistik aufgerufen)
  /openbrain            Session-Archiv mit pgVector
```

## Tool-Stack

| Tool | Funktion | Wo |
|---|---|---|
| Zotero + BetterBibTeX | Literaturverwaltung — einzige Quelle für Keys | `03_quellen/zotero-export.bib` |
| Pandoc + CSL | Export → DOCX/PDF | `06_export/pandoc.yaml` |
| Ollama (lokal) | Exzerpte, Übersetzung, Embeddings | localhost:11434 |
| pgVector via openbrain | Session-Archiv, semantische Suche | `lab_results` Schema |
| LanguageTool | Grammatikprüfung lokal | Port 8081 |
| DeepL API | Übersetzungshilfe (Arbeitsmittel, keine Quelle) | via .env |

## Verzeichnisstruktur

```
Brynhildr_BA/
├── 00_system/          ← ba-memory.md (Projektgedächtnis), memoryLog.md
├── 01_brainstorming/   ← Ideen, Recherchelisten, freie Gedanken
├── 02_forschungsfrage/ ← RQ, Gliederung, Vergleichstabellen
├── 03_quellen/         ← PDFs, Exzerpte, zotero-export.bib, glossar.md
├── 04_kapitel/         ← Rohtext, je Datei ein Kapitel
├── 05_lektorat/        ← Lektoratsprotokolle
├── 06_export/          ← pandoc.yaml, PDF/DOCX-Ausgaben
├── 07_ki-log/          ← Deklaration.md, tool-log.md (Pflicht)
└── config/             ← models.yaml, paths.yaml
```

## Zitierformat

Universität Passau (UP) — Fußnotenformat.
Jede inhaltliche Aussage trägt `[@zotero_key, S. x]` **oder** `[UNBELEGT]`.
Block-Zitate (≥3 Zeilen): eingerückt, einzeilig, Fußnote mit Vollbeleg beim ersten Vorkommen.

## Git-Konvention

Commit-Präfixe: `ai:` | `human:` | `mixed:` — Grundlage für KI-Deklarationsanhang.

## Qualitäts-Anker

1. **Forschungsfrage zuerst** — kein Rohtext ohne Human-freigegebene RQ
2. **Zotero als einzige Wahrheit** — kein Zitieren ohne `[@key]`
3. **Observer niemals überspringen** — einziger Schutz gegen Halluzinations-Drift
4. **Eine Sitzung = ein Kapitel** — parallele Kapitelarbeit zerstört den Observer-Kontext
5. **Pandoc früh testen** — Export-Pipeline in Phase B prüfen, nicht in Woche 9
6. **Englische Sekundärliteratur ist Pflicht** — Byock, Andersson, Clover (mind. 3 EN-Quellen)
7. **ba-memory.md ist die einzige Wahrheit** — kein zweites Statusdokument
8. **Betreuer-Absprache vor Phase C** — RQ + Korpus (Edda ja/nein) sind Hard-Gates

## NEVER

- NEVER Text generieren ohne Quellengrundlage im Kontext
- NEVER Zitate erfinden oder aus dem Gedächtnis zitieren
- NEVER Forschungsfrage oder Gliederung ohne Human-Freigabe finalisieren
- NEVER `07_ki-log/` nach Arbeitsphasen vergessen
- NEVER außerhalb der deklarierten `memory_access`-Pfade eines Skills schreiben
