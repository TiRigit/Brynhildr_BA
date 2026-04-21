# BA Memory — Brynhildr_BA

> Persistente Projektnotizen + aktuelle Session-Übergabe.
> Einzige Quelle der Wahrheit für Projektstatus.
> Nur nach Human-Freigabe aktualisieren.
> Projekt: `/Users/tr/workspace/projects/Brynhildr_BA/`

---

## Metaebene

- **Ziel:** Summa cum laude + reproduzierbarer KI-Workflow als Demonstration
- **KI-Policy:** Explizit erlaubt mit Deklarationspflicht → `07_ki-log/` führen
- **Institut:** Universität, Institut für Germanistik, Abt. Literaturwissenschaft
- **Umfang:** ~25 Seiten Textteil (Deckblatt/Verzeichnisse zählen nicht)

## Status

- **Phase:** Vorbereitung (A) — bereit für Forschungsfrage-Entwicklung
- **Deadline:** (noch nicht festgelegt)
- **Betreuer:** (noch nicht eingetragen — Erstgespräch ausstehend)
- **Letzter Stand:** Workspace-Audit 2026-04-12

## Meilensteinplan (9 Wochen)

| Woche | Ziel | Gate |
|-------|------|------|
| 1–2 | Primärtexte + Forschungsfrage + Gliederung | Human-Freigabe RQ |
| 3–4 | Forschungsstand + Quellen-Analyse | Observer-Check |
| 5–7 | Rohtext (kapitelweise) | Observer + Argumentationscheck |
| 8 | Lektorat + Argumentationscheck | /ba-lektorat + Human |
| 9 | Export + Abgabe | Pandoc → PDF/DOCX |

## Offene Schritte (priorisiert)

1. **BLOCKER:** Primärtexte beschaffen — sagadb.org, heimskringla.no → `03_quellen/primaertexte/`
2. **BLOCKER:** Edda-Lieder einbeziehen? → blockiert Gliederung
3. Forschungsrichtung A (Brünhild-Figur) vielversprechend — Betreuer-Absprache ausstehend
4. Zotero einrichten, erste Quellen erfassen (Byock 1990, Andersson 1980)
5. Gliederung erstellen → `02_forschungsfrage/gliederung.md`

## Offene Entscheidungen

- [ ] **Forschungsrichtung:** A (Brünhild-Figur) / B (Sigurd-Held) / C (Transformation) / D (Einzelmotiv)
- [ ] **Primärtexte:** Nur NL + Völsunga saga — oder auch Edda-Lieder?
- [ ] **Methode:** textimmanent / komparatistisch / kulturhistorisch
- [ ] **Betreuer-Erstgespräch** terminieren

## Quellen-Stand

| Typ | Anzahl | Hinweis |
|-----|--------|---------|
| Primärtexte | 1 | Geschichte von den Voelsungen.pdf |
| Sekundär DE | 2 | Deichl Brynhild.pdf, Steger Brünhild.pdf |
| Sekundär EN | 0 | — |
| Zotero-BIB | 5 | zotero-export.bib (5 Einträge) |

## System-Status (2026-04-12)

| Komponente | Status |
|------------|--------|
| ba-memory.md | ✅ konsolidiert |
| 06_meta/ | ✅ tool-log + prompt-log |
| Skills (BA) | ✅ vollständig + Namen korrekt |
| ba-fortschritt.base | ✅ angelegt |
| Zotero-Sync | ⬜ ZOTERO_USER_ID fehlt noch |
| **Workspace-Audit** | ✅ Phase 1+2 abgeschlossen, Phase 3 offen (Nutzer-Entscheidung) |

### Audit-Ergebnis (aufgabe.md — Phase 1+2)

**Vorhanden & OK:** macOS 26.3, Ollama 0.17.7, Node 25.6, Python 3.14, Pandoc 3.9, Docker-Stack (PG16+pgVector, n8n, Ollama-Container), pandoc.yaml + CSL, Zotero 7 (läuft)

**Fehlt komplett:**
- Open WebUI (GUI) — weder Docker noch pip
- uv (Python-Paketmanager)
- MCP-Schicht: mcpo, zotero-mcp, obsidian-mcp, filesystem-mcp
- Obsidian-Plugins: Local REST API, Templater
- Zotero: Better BibTeX (BBT nicht installiert)
- RAG: ChromaDB + sentence-transformers
- Schreib-Loop-Engine + Feedback-DB (SQLite)
- HPC-SSH-Anbindung + LoRA-Pipeline

**Ollama-Modelle:** Soll-Modelle (Gemma 27B, Qwen3, DeepSeek-R1 14B) nicht geladen. Nur: gpt-oss:20b, deepcoder:14b, glm4, nomic-embed-text, qwen2.5-coder:7b, mistral

**Vorgeschlagene Tier-Reihenfolge:**
1. uv + Open WebUI + Ollama-Modelle
2. mcpo + MCP-Server (Zotero, Obsidian, Filesystem)
3. Obsidian-Plugins (Local REST API, Templater) + Zotero BBT
4. ChromaDB + Feedback-DB + Schreib-Loop
5. HPC + LoRA (benötigt Uni-Zugang)

**Offene Entscheidung:** Nutzer muss Tier-Auswahl + Modell-Strategie bestätigen (Gemma 27B vs 12B vs Qwen3 MoE bei 24GB RAM)

## Session-Archiv

### Session 5 — 2026-04-12 (Claude Opus 4.6 1M)
- **aufgabe.md**: Workspace-Audit (Phase 1+2) komplett durchgeführt
- System-Scan: Ollama, Docker, Zotero, Obsidian, Pandoc, Python, Node, SSH, MCP, RAG
- Ist-Soll-Tabelle mit 24 Zeilen erstellt, Deltas identifiziert
- 5-Tier-Implementierungsplan vorgeschlagen
- **Status:** Phase 3 (Diskussion) offen — wartet auf Nutzer-Freigabe für Tier-Auswahl
- **Kein Code geändert**, nur Audit + Dokumentation

### Session 4 — 2026-04-07 (Claude Sonnet 4.6 1M)
- Kepano-Skills installiert (defuddle, json-canvas, obsidian-bases, obsidian-markdown, obsidian-cli)
- Strukturelles Setup: ba-memory, 06_meta/, Skill-Namen fixiert, CLAUDE.md ergänzt
- ba-lektorat + ki-deklaration Skills erstellt
- .env: ZOTERO_API_KEY eingetragen

### Session 3 — 2026-03-13 (Claude Sonnet 4.6)
- Infrastruktur-Bereinigung: .claudeignore, observer.md, pandoc.yaml, quellen-merge, ba-memory cleanup
- Audit + Konsolidierung: Scaffolding entfernt, Skill-Duplikate bereinigt, Meilensteinplan erstellt

### Session 2 — 2026-03-13 (Claude Sonnet 4.6)
- Tool-Stack Erweiterung, alle Skills erstellt, Quellenstruktur, Loseblatt-Ordner

### Session 1 — 2026-03-11 (Claude Sonnet 4.6)
- Projektplanung, Tool-Recherche, System-Architektur, Dateistruktur
