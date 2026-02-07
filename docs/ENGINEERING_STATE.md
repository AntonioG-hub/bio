# Engineering State — Bion

## Status
- MVP: ✅ completed
- Core analysis pipeline: ✅ stable
- History, analytics, persistence (Supabase): ✅ working
- Text-based analysis: ✅ production-ready
- Retrieval: ✅ implemented (single-document scope, no multi-source comparison yet)
- PDF ingestion: 🚧 in progress
  - Known issue: unreliable text extraction on Windows
  - Current focus: stabilizing extraction without breaking existing pipeline

## Frontend
- Framework: Next.js (App Router)
- Bundler: Webpack
- Styling: incremental UI system (no global refactor)
- Sidebar:
  - Continuous (no vertical divider)
  - Narrower width (ChatGPT-like)
  - Persistent DNA circular logo (blue/green)
- Central Home:
  - Brand-focused empty state
  - “Bion” as primary visual identity

## Backend
- API routes stable (`/api/analyze_*`)
- LLM integration:
  - Cost-efficient models only
  - No “latest” aliases
  - Explicit model IDs
- Guardrails:
  - No medical advice
  - Explanatory / interpretative only

## Branding / Assets
- Sidebar logo:
  - Circular DNA (blue + green)
  - Inline SVG
  - Optional subtle micro-animation (respect prefers-reduced-motion)
- Central logo:
  - “Bion” wordmark
  - Smaller, refined
  - Faux-3D via SVG strokes (no heavy gradients)
  - Optional abstract serpent wrapping (symbolic, non-cartoonish)

## Constraints
- NO breaking changes
- NO refactor of existing logic
- UI and branding changes must be incremental
