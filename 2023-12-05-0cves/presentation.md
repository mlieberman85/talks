---
marp: true
---

# The Road to 0 CVES
## People and Technology

---

Intro Slide for Andy

---

Intro Slide for Mike

---

Highlight the problem and where we're coming from.
Supply chain attacks are on the rise. 
Recent North Korean attack for example.
Dependency confusion/typo squatting
Software gets increasingly more complex with increased reliance on third party, often open source software

---

Governments come in!
US, and Europe are leading the charge but we're seeing efforts throughout Asia on securing supply chains.
Regulations, legislation, etc. are being developed like US EOs, EU CRA, etc.
Not just regulations, governments are actively trying to help provide guidance 
Highlight: https://www.ncsc.gov.uk/files/Guidelines-for-secure-AI-system-development.pdf as an example here.
Highlight how > 20 of the world's leading security agencies participated on that document including Japan's NISC.


---

Highlight the general solution. 0 CVEs is not just about trying to get 0 CVEs.
It is an exercise in security hygiene for how you produce and consume software.
This is done through understanding your environment and secure by design

---

0 CVEs is more about the journey than the destination.
There will always be vulnerabilities, attacks, etc.
However, by instituting good hygiene, instituting guardrails for how you produce software it makes it easier to address issues as they come up

---

Talk about the alternative. Too much focus on "vulnaerability mitigation prioritization."
Prioritization outside of specific cases is often a losing battle.
You spend more time prioritizing than just fixing issues

---

Loop back to the regulations and legislations and how they impact how we view the problem.
Some regulations, especially those coming out of the US demand 0 CVEs, this is unreasonable even if the 

---

How do we get started?
Highlight that it's about addressing issues quickly and providing guardrails to prevent stuff that is obviously bad getting in in the first place
Practically this means we need good data about the issues and need to build an understanding of our supply chain!

---

Show Isaac Hepworth's diagram on the depth of supply chain: https://user-images.githubusercontent.com/3060102/196563695-a1cdc8bd-9946-482f-873a-937bf75891dc.png

Talk about when addressing CVEs we first need to understand what we're pulling in, how we're pulling it in, etc. Before addressing whether or not we're pulling in code with a CVE are we pulling in the right code in the first place! This is where Sigstore, SLSA, GUAC and policy come in.

---

Now we go more in depth.
The suggestions we make won't be universal. Not every vendor or open source dependency will apply these practices.
We will highlight alternatives from a consumption standpoint.
e.g. SLSA is useful when folks are producing software using SLSA. S2C2F includes practices for consuming software securely even when folks aren't using SLSA though you should consume SLSA when you can.

---

Some assumptions.
You have some sort of SDLC
You have a source repo, build system, and use soemthing for packaging or downloading packages from

---

Are you pulling down from trusted parties?
If you don't then how do you even know you're downloading what you're supposed to.

Ideally - Signed, e.g. Sigstore, TUF
(some of these from S2C2F and others)
Alternatives -  Build from source. Check checksums, etc.

---

Are the parties you're trusting to provide software doing the right things from security hygiene?

Ideally - Build with SLSA, using Scorecard, in-toto, etc.
(some of these from S2C2F and others)
Alternatives - Build from source, scan source, scan packages.

---

Are you keeping track of the up to date data on the software you're running? It is hard to eliminate CVEs if you don't know what you have in the first place.

Ideally - GUAC, event driven architectures, osquery ,subscribing
Alternatives - Scan, CMDB

(Each of these builds on the last)

Note: Keeping track of everything is important and only figuring out if you're impacted when a major CVE is discovered is BAD.

---

Are you building policies and rules? If you are not being consistent with how you consume software, how you handle updates, when vulns are discovered etc. you are kind of updating blindly and not addressing issues as they come up.

Ideally - Use policy engines like OPA, Kyverno that query sources of truth like GUAC in conjunction with artifact proxies
Alternatives - Use artifact proxies with somewhat arbitrary rules, enforce rules manually (this is bad and does not scale)

---

Takeaways
- Security hygiene activivities of projects tends to correlate with security health, e.g. scorecard, slsa, etc. mean those projects tend to have less CVEs and also resolve CVEs faster
- Regulations and legislation are a move in the right direction even if implemented quite poorly right now
- It's about the DATA. It's hard to prove 0 CVEs when you don't have the data on CVEs or even know what's running in your environment.
- 0 CVEs is more about the journey than the destination, it's about how we can all be doing more to keep fixing the problem than to say that only 0 CVEs means we're secure.