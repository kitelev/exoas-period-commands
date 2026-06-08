# exoas-period-commands

Exocortex **starter period/daily command library** (RFC `5aa2a73a` A3).

Holds the daily-planning `exocmd__Command` instances (+ their groundings, command
bindings, and period-specific support assets) extracted from `exoas-exocmd` so
that `exocmd` can become **TBox-only** for the starter. Commands reference the
`exocmd` TBox (class defs, grounding types, inheritance rules) **cross-repo by
UID** — both AssetSpaces are mounted together in the starter profile.

Under `period-commands/`:

- **9 commands** — Plan on Today, Plan for Evening, Shift Day Forward/Backward,
  Set/Remove Scheduled Date, Set Planned Start/End, Create Task for DailyNote.
- **9 groundings** (1:1 with the commands) + **6 command bindings**.
- **3 support assets** — `$todayStart` event prototype, `plannedStartTimestamp=$today`
  property default, "Has scheduled date" precondition.

Discovery is **class-based** (`rdf:type = exocmd__CommandBinding`), so these render
as action buttons wherever the AssetSpace is mounted — `isDefinedBy` is not a
discovery filter (CommandResolver, verified RFC A3).

Member of the `starter` knowledge profile (`exoas-starter-registry`).
