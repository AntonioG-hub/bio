# Bio AI — Product & Continuity Rules

## One-liner
Bio AI explains biomedical papers (starting with reviews + compatible research articles) in structured outputs, with three depth modes.

---

## Target (LOCKED)
- Snapshot: anyone (fast orientation)
- Academic: early-year / master students
- Deep Dive: PhD students, researchers, clinicians

---

## Supported Content (v1)
- ✅ Review papers
- ✅ Original research articles (interpreted as a paper explanation, not clinical guidance)
- ❌ Clinical-trial-specific module (future)
Note: We always declare the paper type.

---

## Modes (LOCKED ORDER)
1) Snapshot
2) Academic
3) Deep Dive

---

## Output Structure (LOCKED)
### Snapshot JSON keys
- paper_type_note
- summary
- why_it_matters
- key_concepts
- limits

### Academic JSON keys
- paper_type_note
- summary
- why_it_matters
- key_concepts
- limits

### Deep Dive JSON keys
- paper_type_note
- summary
- why_it_matters
- key_concepts
- bias_and_methodological_issues
- mechanisms_and_pathways
- limits

---

## Article Type Declaration (LOCKED)
- Every mode MUST include:
  - `paper_type_note` (one sentence)
- Types:
  - Review
  - Original research article
  - Clinical study (if encountered: still declare, but no clinical guidance)

---

## Limits Definition (LOCKED)
- `limits` = limitations of the paper / limitations of current scientific knowledge / open challenges.
- Never mention AI limitations.

---

## Quantitative Data Rules (LOCKED)
- Snapshot: NO quantitative data anywhere.
- Academic & Deep Dive:
  - Summary: NO quantitative data
  - Quantitative data allowed ONLY in:
    - why_it_matters
    - key_concepts
  - Must be explained (what it means), proportional to audience depth.

---

## References Policy (v1)
- No external bibliographic citations (DOI/PubMed).
- Use only internal phrasing (e.g., “the authors report…”, “the study shows…”).

---

## What Must NOT Change
- Mode names + order
- Section names/structure
- Meaning of limits
- Rule: `paper_type_note` always present
- Quantitative data placement rules
