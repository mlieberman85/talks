---
marp: true
theme: gaia
style: |
    section{
      justify-content: flex-start;
    }
---

# GUAC PoC Proposal

---

## Problem(s)

OSS consumers want a place where they can discover and consume metadata and analytics about the software they ingest.

Toolbelt needs a way to store metadata that comes from the toolbelt (e.g. scorecard, SBOMs, SLSA, etc.) and for that metadata to be consumed by end users

OpenSSF incubating project GUAC needs some real world case studies to help identify additional features, bugs or scalability issues

---

## Solution

Build a PoC internal service for a case study.

- This is not a public service but should be a pilot
- This should be used by a set of maintainers and end users for the study

---

## Other things considered

- Why not deps.dev or OSV?
  - These are data sources into a deeper analysis that GUAC can provide.
  - OSV/deps.dev don't provide the ability to add additional metadata.
  - The public services are not run by OSSF
- Looking at other OpenSSF/Open Source supply chain analysis tools
  - There are not many and GUAC has grown in popularity.

---

## Proposal

- Run GUAC for some OpenSSF case studies like work in the Security Toolbelt group. This is not a public service but would be limited to maintainer and end user participants
- This can evolve over time and if determined to not be useful to the community and/or deemed too expensive to run at scale by OSSF GB can be shut down

---

## Cost

- ~$1k a month in cloud resources for the initial case study
  - GUAC requires various resources like an api server, an event stream, a database, etc. that all need to run
  - This initial case study would also allow us to understand how GUAC scales.
  - Primary cost factors are size of ingestion and how many users are running complex queries against it.
