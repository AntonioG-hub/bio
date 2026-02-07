# Bio AI — Engineering State

## Current Phase
- Phase: Phase 2 — MVP Technical + Minimal UI
- Status: ✅ Working end-to-end (UI → API → OpenAI → JSON → UI)

---

## What’s Implemented (DONE)
### Runtime
- Next.js App Router project (no `src/` folder)
- Dev server runs (`npm run dev`)

### API
- Endpoint: `POST /api/analyze`
- File: `app/api/analyze/route.ts`
- Provider: OpenAI (model: `gpt-4o-mini`)
- Strict JSON parsing (fails if invalid JSON)

### UI
- Single-page minimal chat UI: `app/page.tsx`
- User can paste text, choose mode, click Analyze
- Renders assistant output as structured sections
- Works with all three modes

### Environment
- `.env.local` contains:
  - `OPENAI_API_KEY=...`
- Confirmed `/api/analyze` exists (GET returns 405)

---

## Current Behavior (LOCKED)
- Modes order: Snapshot → Academic → Deep Dive
- Always include `paper_type_note` in every mode output
- `limits` = scientific limitations/open challenges of the paper/field (NOT AI limitations)
- Quantitative data rules:
  - Snapshot: NO numbers anywhere
  - Academic & Deep Dive:
    - NO numbers in `summary`
    - Numbers allowed only in `why_it_matters` + `key_concepts` (explained, proportional to mode)
- Deep Dive audience includes PhD / researchers / clinicians
- Academic audience includes early-year / master students

---

## Known Setup Notes (Windows)
- PowerShell can block npm scripts (ExecutionPolicy). Fixed by allowing current user scripts.
- `curl` in PowerShell is alias; use `Invoke-RestMethod` for POST tests.
- Ensure `.env.local` is not `.env.local.txt` (enable file extensions).

---

## Next Concrete Steps (choose sequence)
1) Add “Analyses history” (ChatGPT-like sidebar list) — first in-memory, then DB
2) Add multi-provider routing (OpenAI / Anthropic etc.) with per-mode choice + fallback
3) Add persistence (Supabase): store inputs + outputs + timestamps + mode + provider used
4) UX polish: collapsible sections, copy buttons, loading skeleton, token/length limits

---

## Restart Protocol (critical)
When switching chats:
1) Make sure these docs are up to date.
2) In a new ChatGPT conversation, paste the “START PROMPT” from `docs/START_PROMPT.md` (or from this message).
