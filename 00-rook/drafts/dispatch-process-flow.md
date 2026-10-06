# Dispatch process flow: incident to assignment (draft)

Drafted 6 Oct 2026 from the Dispatch one-pager and the 4.2 release notes. Parts marked [not documented] are gaps to confirm with Wen, Marcus or Nadia.

```
INCIDENT ARRIVES
Handler enters it in the console, or an intake system pushes it in
        |
        v
DISPATCH RANKS RESPONDERS
Every available responder is scored on:
 - proximity (travel-time estimate since 4.1; weighted up in 4.2)
 - current availability
 - capability match (required tags)
 - recent acceptance history (misses and turn-downs lower it)
Result: a routing priority order
        |
        v
PING TO THE TOP-RANKED RESPONDER
Offered to one responder at a time, on their phone
The ping stays live for the ping wait: 60 seconds (90 before 4.2)
        |
   +----+-----------------+-------------------+
   |                      |                   |
 TAKEN             TURNED DOWN            MISSED (no answer in time)
   |                      |                   |
   |                      +---------+---------+
   |                                |
   |                  Ping moves to the next responder in the order
   |                  and the cycle repeats. Both outcomes lower
   |                  that responder's recent acceptance.
   v
RESPONDER MARKED "ENGAGED"; INCIDENT ASSIGNED
Maintenance scheduling in Supply reads this availability record

        |
        v
[not documented] responder attends and completes the job,
then returns to available
```

## Who does what

- **Handler (web console):** enters incidents, watches coverage, overrides routing, and manages availability and capability tags.
- **Responder (phone app):** takes or turns down a ping, and sets availability.
- **Configuration:** routing config, including the ping wait, ships with the release. It is not a runtime setting.

## Open questions

| Gap | Who to ask |
|---|---|
| How a job is completed and how the responder returns to available | Marcus or Nadia |
| What happens when nobody takes the callout (the ping data shows unfilled callouts) | Marcus or Nadia |
| Where in the flow a handler override happens, and whether it's logged | Wen, Marcus |
| How required capability tags are set on an incident | Wen |
| Ranking weights and how missed pings feed the score | Wen |
