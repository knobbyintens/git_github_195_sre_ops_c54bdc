# Severity and Priority Matrix

Priority is derived from severity and customer impact:

| Severity | Customer impact | Priority |
|----------|-----------------|----------|
| SEV1     | yes             | P0       |
| SEV1     | no              | P1       |
| SEV2     | yes             | P1       |
| SEV2     | no              | P2       |
| SEV3     | either          | P3       |

## Work item conventions

- Title: `[<incident_id>] <service>: <summary>`
- Body lines:
  `Incident`, `Service`, `Severity`, `Priority`, `Customer impact`,
  `Owning team`, `On-call engineer`, `Paging channel`, `Detected at`,
  `Incident record`.
  The on-call engineer is the primary engineer for the owning team from the
  roster.  Paging channel also comes from the roster.
- Labels are not part of this tracker's workflow; the body lines above are the
  authoritative metadata.
- Hotfix branch: every P0 incident that receives a new work item also gets a
  branch named `hotfix/<incident_id>-<service>` cut from the default branch.

## Status handling

- `open` incidents are triaged and get a new work item unless one already
  exists for the incident id.
- `resolved` incidents do not get a new work item; any still-open work item
  for them is closed.
- Any other status is left alone.
