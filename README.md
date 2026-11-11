# SRE Incident Registry

This repository is the shared registry for the platform engineering on-call
rotation.  It contains:

- `incidents/` - raw incident records captured by the observability pipeline.
  Each file is a JSON document describing one incident.
- `services/services.json` - service ownership map (owning team, tier, codebase).
- `oncall/roster.json` - current on-call rotation with primary/secondary
  engineers and paging channels per team.
- `policy/severity_matrix.md` - how severity, customer impact and priority map
  to follow-up work items.

Records are appended by the incident bot.  Humans are expected to triage the
open records at the start of every on-call shift and to keep the work item
tracker in sync.
