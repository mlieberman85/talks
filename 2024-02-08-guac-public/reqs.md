# Scope

## Primary Goals

- Understand the open source security needs of end users
  - What data/metadata do they need about the open source software they use and intend to use and what questions about that do they need answered in order to feel safe
- Understand the security needs of maintainers and any blockers in them adopting security tooling and best practices, in particular OpenSSF tools and best practices
  - e.g. why can't they adopt scorecard or generate SBOMs
- Understand where there are gaps in open source security frameworks, tools, etc. intended to secure production, distribution, and consumption of open source software
  - What features need to be added, how do we make adoption easier, etc.
  - How do we ensure all these tools interoperate well together?
  - This includes various OpenSSF projects like GUAC, Scorecard, SLSA, etc.

---

## Secondary Goals

- Test scalability of some elements of GUAC. We will be throwing a reasonable amount of supply chain metadata at it.
- Test feasability of running the various tools as a or part of a public service (not necessarily funded by OpenSSF or LF)
- Dog food OpenSSF tools
  - This might help A-O and other initiatives in helping automate and provide better tooling for some of the large scale drives on implementation efforts they are doing

---

## Running the PoC

- Work with a handful (3-5) of maintainers of open source projects to throw their supply chain metadata at guac.
- Work with a handful (3-5) of end users of open source projects to ask questions of GUAC to help with feeling safe to use these open source projects based on the answers from GUAC.
- Work with the security toolbelt to iterate on what info gets generated by the projects (SBOMs, SLSA, scorecard, etc.) what features might need to be added to GUAC, as well as any integrations/tools that work with GUAC to answer questions for end users.
- Generate a report at the end about how well this worked along with challenges, intended next steps, etc.

## Resource Reqs

- To start off with we just need GUAC running in the cloud. This could just be via docker compose on an EC2 instance. Just something to get the ball rolling
- Over time if things go well we can spin this up to look more representative of a toolbelt with GUAC as the data store for software producer metadata (SBOM, SLSA, etc.) along with ingestion focused tools like those in S2C2F.
  - EKS or Fargate
  - RDS
  - ALB and other supporting tools
  - IAM and federation related services so that we can make controlling access more straightforward (e.g. just give folks underneath an OSSF managed Github team access to GUAC)
