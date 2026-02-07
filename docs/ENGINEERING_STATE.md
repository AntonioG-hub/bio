# Bio AI — Engineering State

## Current Phase
- Phase: Phase 2 — MVP Technical + Minimal UI
- Status: ✅ Working end-to-end (UI → API → LLM → JSON → UI)

---

## What’s Implemented (DONE)

### Runtime
- Next.js App Router project (NO `src/` folder)
- Dev server runs (`npm run dev`)
- Webpack mode in dev (not Turbopack)

### API
- Endpoint: `POST /api/analyze`
- File: `app/api/analyze/route.ts`
- Multi-provider routing (OpenAI / Anthropic)
- Intelligent router (input length, structure, domain, mode)
- Fallback + circuit breaker
- Strict JSON parsing + normalization
- Guardrails per mode

### Additional API
- Endpoint: `POST /api/analyze_pdf`
- Node runtime (`export const runtime = "nodejs"`)
- PDF upload via multipart/form-data
- Text extraction pipeline (currently under stabilization)

### UI
- Single-page chat UI: `app/page.tsx`
- Modes selector (Snapshot → Academic → Deep Dive, order locked)
- History sidebar (ChatGPT-like)
- Component extraction + UX polish (collapsible sections, copy buttons, loading state)
- Length / token limits enforced

### Persistence
- Supabase connected (server-side, service role)
- Tables:
  - `analyses`
  - `analysis_events`
- Analyses persisted with:
  - input_text
  - output_json
  - mode
  - provider_used
  - fallback_used
  - latency_ms
  - violations_count

### Metrics & Analytics
- `analysis_created` event logged after successful insert
- Infrastructure ready for:
  - views
  - copy
  - toggle events

---

## Current Behavior (LOCKED)
- Modes order: Snapshot → Academic → Deep Dive
- Every output includes `paper_type_note`
- `limits` = scientific limitations / open challenges (NEVER AI limits)
- Quantitative rules:
  - Snapshot: NO numbers anywhere
  - Academic & Deep Dive:
    - NO numbers in `summary`
    - Numbers allowed ONLY in `why_it_matters` and `key_concepts`
- Deep Dive target: PhD / researchers / clinicians
- Academic target: early-year / master students

---

## Known Environment Notes (Windows)
- PowerShell `curl` is alias → use `curl.exe`
- Desktop path under OneDrive
- Next dev running with Webpack (`next dev --webpack`)
