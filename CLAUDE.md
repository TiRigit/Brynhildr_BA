# Projekt-Agent-Anweisungen: Brynhildr_BA

## Projekt
Name: Brynhildr_BA
Typ: Bachelorarbeit (Germanistik / Mediävistik)
DB-Schema: Brynhildr_BA

## Thema
Vergleich der Brynhildr-Figur in der Völsunga saga und dem Nibelungenlied
(Arbeitstitel: "Brünhild zwischen Heldin und Antagonistin")

## Projektstruktur
```
Brynhildr_BA/
├── 01_brainstorming/       ← Ideensammlung, Mindmaps, Notizen
├── 02_forschungsfrage/     ← Forschungsfrage, Exposé, Gliederung
├── 03_quellen/             ← Exzerpte, Zotero-Exporte, Primärtexte
├── 04_kapitel/             ← Kapitel-Rohtexte (je Datei ein Kapitel)
├── 05_lektorat/            ← Lektoratsdurchläufe, Kommentare
├── 06_export/              ← Pandoc-Exporte (PDF, DOCX)
├── 07_ki-log/              ← KI-Nutzungsdeklaration (Pflicht)
└── src/                    ← (leer, bei Bedarf für Tools)
```

## Regeln
1. Sprache: Deutsch für Kommunikation und Fließtext, Englisch für Code
2. Zitierformat: Universität Passau (UP) — Fußnotenformat
3. Quellen vor Verwendung exzerpieren (→ /exzerpt)
4. Vor Schreibphasen: Observer-Check (→ /observer)
5. Nach jeder Arbeitsphase: KI-Deklaration (→ /ki-deklaration)
6. Keine externen APIs für inhaltliche Arbeit — Ollama lokal
7. Datenbank: Schema "Brynhildr_BA" in bestehender PostgreSQL-Instanz
8. Keine Credentials in Code — .env nutzen

## Primärtexte
- Völsunga saga (sagadb.org, NL digital)
- Nibelungenlied (Bartsch/de Boor-Edition)

## Wichtige Skills
- /brainstorming — Sammelordner auswerten
- /konzept — Forschungsfrage + Gliederung entwickeln
- /exzerpt — Quelle annotieren
- /observer — Halluzinationscheck
- /kapitel-rohtext — Kapitel schreiben (Phase C)
- /ba-lektorat — Lektorat (Phase D+E)
- /ki-deklaration — KI-Log nach jeder Arbeitsphase
- /ba-stats — Projektstatistik
- /zeitwaechter — Deadline-Tracking
