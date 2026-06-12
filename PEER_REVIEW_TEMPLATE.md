# Peer Review Report

## Your Details

| Field | Your answer |
|-------|------------|
| Full Name | 松怡琳 |
| Student ID | 113403535 |
| Team ID | Team 17 |
| Date submitted | 2026-06-12 |

---

## Section A — Self-Assessment

### A1. What did you personally implement?
* Wrote all the `seed_*` sub-functions in `skeleton/seed_postgres.py` to correctly import our raw JSON data into PostgreSQL.
* Created and designed the overall database relationship diagram (`ERD.png`).
* Handled the integration testing across our three databases (SQL, Vector, and Graph) to make sure the Agent doesn't crash when calling tools.
* Authored `TEAM.md` 、 Section 1、Section 2 of `Team17_DESIGN_DOC.md`.

### A2. What challenges did you face?
Our mock timetable and schedule data had multiple levels of nested arrays, which threw errors when trying to import them directly into the relational tables. To fix this, I had to write custom Python flattening logic to break the nested structures into clean, individual rows to satisfy 1NF requirements before running the bulk inserts. 

Another big headache was coordinating local environments. At the start, our team had conflicting container port mappings and different LLM choices. I had to debug these connection issues and write setup docs to sync our local service configurations so everyone could test the pipeline smoothly without breaking each other's code.

### A3. Self-rating

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| I delivered the tasks assigned to me in the work allocation | 3 | I finished all my seeding scripts and integration tasks on time as planned. |
| The quality of my work was satisfactory | 3 | Everything runs fine, though I think my integration test cases could cover a few more edge cases. |
| I communicated well and kept the team informed | 4 | I always updated the team during syncs and made sure to document our workflow changes. |
| I met deadlines agreed within the team | 4 | I pushed my code to the repository before our agreed internal milestones. |
| **Overall self-rating** | **14** | Did my job properly and kept my parts of the project on track. |

### A4. Estimated contribution percentage
My estimated contribution: **33%**

---

## Section B — Peer Assessments

### B1. Assessment of Teammate 1: cammie20260621

#### What did this teammate deliver?
Responsible for the relational DB setup. They wrote the data tables and constraints in `databases/relational/schema.sql`, and built the query functions in `databases/relational/queries.py` so the AI agent can look up transactional user records.

#### Did their actual contribution match the agreed work allocation?
Yes, they did exactly what we planned during our initial setup meetings and delivered the core PostgreSQL component.

#### Peer rating for this teammate

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| Delivered the tasks assigned in the work allocation | 5 | They delivered the SQL schema quickly and even helped verify field types for my seeding script. |
| Quality of their work was satisfactory | 4 | Table indexes and foreign key relations are very clean and solid. |
| Communicated well and kept the team informed | 4 | They gave clear updates whenever they changed query logic or database fields. |
| Met deadlines agreed within the team | 5 | Finished ahead of schedule, which gave me plenty of time to build the seeder on top of it. |
| **Overall rating for this teammate** | **18** | Did an amazing job setting up a reliable relational database foundation. |

#### Estimated contribution percentage for this teammate
My estimate of their contribution: **33%**

---

### B2. Assessment of Teammate 2: Oeo941014

#### What did this teammate deliver?
Handled the Graph DB domain. They created the Neo4j station nodes and transit route edges in `databases/graph/seed.cypher`, and coded the pathfinding and transfer algorithms in `databases/graph/queries.py`.

#### Did their actual contribution match the agreed work allocation?
Yes, they took full ownership of the graph database routing functions just as we agreed.

#### Peer rating for this teammate

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| Delivered the tasks assigned in the work allocation | 4 | Got all the Neo4j node structures and routing tools running properly. |
| Quality of their work was satisfactory | 4 | The Cypher path queries are fast and calculate complex route changes very accurately. |
| Communicated well and kept the team informed | 4 | Proactively shared updates about port changes and network mapping updates in our chat. |
| Met deadlines agreed within the team | 4 | Submitted all graph scripts right within our project deadlines. |
| **Overall rating for this teammate** | **16** | Worked hard on a tough graph structure and delivered great route-finding logic. |

#### Estimated contribution percentage for this teammate
My estimate of their contribution: **33%**

---

## Section C — Contribution Percentage Summary

| Member | Your estimated % | Notes |
|--------|----------------|-------|
| Yourself | 25% | Seeding routines, ERD engineering, documentation layout, and integration checks. |
| cammie20060621 | 45% | Relational table generation, constraint models, and relational SQL queries. |
| Oeo941014 | 30% | Neo4j network mapping, Cypher scripts, and spatial route queries. |
| **Total** | **100%** | |

---

## Section D — Overall Team Reflection

### D1. What went well in the team's collaboration?
Our division of labor was very clean because each person focused on a specific database component (SQL, Graph, or Seeding/Testing). Working out of separate directories prevented Git merge conflicts. We communicated smoothly in our group chat, meaning database updates were integrated without blocking anyone's workflow.

### D2. What would you do differently if you did this project again?
If we did this again, we would align on our local LLM vector embedding dimensions during week one—getting 768 and 3072 mixed up forced us to wipe the database volumes and re-seed multiple times near the end. We should also set up automated testing sooner so we don't have to manually run the seed scripts every time schema adjustments are made.

### D3. Is there anything else the markers should know about team dynamics or individual contributions?
Nothing to add. Everyone put in their fair share of work and the teamwork was highly cooperative.

---

## Declaration
I confirm that this peer review reflects my honest and independent assessment.

**Signed:** 松怡琳 **Date:** 2026-06-12
