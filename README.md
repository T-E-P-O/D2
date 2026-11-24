# Deliverable D2 — Trento Energy Portfolio Optimizer (TEPO)

Repository ufficiale del **Deliverable D2** (*Sviluppo, Architettura di Sistema, Specifiche Web API e Deployment*) per il progetto **TEPO** (*Trento Energy Portfolio Optimizer*), sviluppato nell'ambito dell'insegnamento di **Ingegneria del Software** (A.A. 2026/2027) presso l'**Università degli Studi di Trento** in cooperazione con l'iniziativa *"100 progetti per il Comune di Trento"*.

- **Codice sorgente del software:** [https://github.com/T-E-P-O/TEPO](https://github.com/T-E-P-O/TEPO)
- **Deliverable D1 (Requisiti):** [https://github.com/T-E-P-O/D1](https://github.com/T-E-P-O/D1)
- **Demo online (Render):** [https://tepo.onrender.com](https://tepo.onrender.com)
- **Team di sviluppo (Gruppo T14):**
  - Mirco Negri
  - Gabriele Duca
  - Riccardo Scheda

---

## Contenuto del Deliverable

In conformità alle direttive del corso per l'A.A. 2026/2027, il documento D2 unifica e integra la documentazione del processo di sviluppo in sprint e la progettazione architetturale di sistema (precedentemente collocata nel D3):

1. **Introduzione e Architettura di Sistema** (`sections/01_Introduzione_Architettura.tex`):
   - Scopo del deliverable D2 e principi guida della PA (*"L'AI propone, l'utente confronta, il Comune decide"*).
   - Architettura logica a livelli e stack tecnologico motivato (Java 21, Spring Boot 3.3.4, Google OR-Tools CP-SAT 9.11, PostgreSQL 16, React 18, Vite, TypeScript, Nginx, Docker, Render).
   - Analisi di trade-off ingegneristico rispetto alle alternative tecnologiche esaminate.
2. **Organizzazione del Repository, Ambienti e Pipeline CI/CD** (`sections/02_Repository_Pipeline.tex`):
   - Albero completo del monorepo multi-modulo.
   - Strategia di branching con feature branch e convenzione dei commit in lingua italiana conforme a *Conventional Commits*.
   - Pipeline di Continuous Integration e Continuous Deployment su GitHub Actions (`.github/workflows/ci.yml`).
   - Manuale operativo di avvio locale con Docker Compose e script di verifica.
3. **Epiche e Product Backlog** (`sections/03_Epiche_ProductBacklog.tex`):
   - Le 5 Macro-Epiche di progetto (EP-01 Dominio, EP-02 Scenari, EP-03 Ottimizzazione, EP-04 Analisi What-If, EP-05 AI e Importazione Dati).
   - Product Backlog completo con stima in Story Points (scala Fibonacci), priorità MoSCoW e allocazione negli sprint.
   - Formalizzazione della *Definition of Ready* (DoR) e della *Definition of Done* (DoD).
4. **Processo di Sviluppo Incrementale in Sprint** (`sections/04_Processo_Sviluppo_Sprint.tex`):
   - Rendicontazione dettagliata dei 4 Sprint di sviluppo bisettimanali (Sprint 1, Sprint 2, Sprint 3, Sprint 4).
   - Per ciascuno sprint: specifiche User Story, piani di implementazione tecnica, evoluzione progressiva dei Component Diagram e Class Diagram, suite di test collaudate e retrospettive agili.
5. **Architettura e Diagrammi Finali di Sistema** (`sections/05_Architettura_Diagrammi_Finali.tex`):
   - Component Diagram finale integrato.
   - Class Diagram completo del backend Spring Boot.
   - Entity-Relationship Diagram (ERD) e schema relazionale PostgreSQL con indici e tipi di dato a 64 bit.
   - Sequence Diagram dei flussi critici (ottimizzazione matematica, assistenza AI sovrintendente con fallback e validazione umana, importazione CSV atomica a due stadi).
6. **Specifiche delle Web API (RESTful & OpenAPI 3.0)** (`sections/06_Specifiche_Web_API.tex`):
   - Standard RESTful, codici di stato HTTP e gestione centralizzata degli errori (RFC 7807).
   - Specifica formale di tutti gli endpoint con URI, payload JSON di richiesta/risposta ed esempi reali ricavati dal dataset demo di Trento.
7. **Frontend Architecture e User Experience** (`sections/07_Frontend_UX.tex`):
   - Architettura della SPA React 18, gestione dello stato di sessione A/B e routing.
   - Design System "Strumento Civico" (doppio registro *Relazione* / *Sala Operativa*, accessibilità WCAG 2.1 AA, tavolozza comandi `Ctrl+K`).
   - Schede analitiche e screenshot reali delle 9 viste operative dell'applicazione.
8. **Deployment e Infrastruttura di Esercizio** (`sections/08_Deployment_Esercizio.tex`):
   - Containerizzazione con immagini Docker multi-stage (backend e frontend).
   - Orchestrazione locale con `docker-compose.yaml`.
   - Blueprint Infrastructure-as-Code `render.yaml` per il deployment automatico su Render con managed PostgreSQL, normalizzazione dinamica della porta e delle connessioni TLS.
   - Monitoraggio prestazionale e rispetto degli SLA in produzione.
9. **Tracciabilità dei Requisiti e Conclusioni** (`sections/09_Tracciabilita_Conclusioni.tex`):
   - Matrice di tracciabilità end-to-end (RF/RNF $\leftrightarrow$ US $\leftrightarrow$ Componenti $\leftrightarrow$ Endpoint API $\leftrightarrow$ Test $\leftrightarrow$ Stato 100%).
   - Analisi delle variazioni rispetto alla baseline di D1.
   - Conclusioni sull'efficacia dello Specification-Driven Development e prospettive evolutive.

---

## Compilazione locale e Overleaf

### Compilazione locale (LaTeX)
Per compilare il documento PDF a partire dai sorgenti:

```bash
# Tramite tectonic (consigliato, compila autonomamente scaricando i pacchetti)
tectonic D2_main.tex

# Oppure tramite latexmk
latexmk -pdf D2_main.tex

# Oppure tramite pdflatex
pdflatex D2_main.tex
pdflatex D2_main.tex
```

Il documento compilato finale è disponibile direttamente in questo repository nel file [`D2.pdf`](./D2.pdf).

### Sincronizzazione con Overleaf
Il repository è predisposto per l'importazione diretta o la sincronizzazione Git con [Overleaf](https://www.overleaf.com):
- Master file: `D2_main.tex`
- Compilatore: `pdfLaTeX`
