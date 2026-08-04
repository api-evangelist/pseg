# PSEG (pseg)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Public Service Enterprise Group (PSEG) is a diversified energy holding company headquartered in Newark, New Jersey. Its regulated utility subsidiary Public Service Electric and Gas (PSE&G) is New Jersey's largest electric and gas distribution utility, and PSEG Long Island operates the transmission and distribution system on behalf of the Long Island Power Authority. PSEG sits squarely in the utility-retailer tier of the United States energy value chain — it meters, bills, and serves end customers, and it sells generation into the PJM wholesale market rather than publishing that market's data itself. Its API posture is honestly closed. There is no developer portal: developer., developers., api., docs., and data.pseg.com do not resolve, and /developers, /api, and /docs on pseg.com return the site's soft-404 page. Green Button is present only as a file: PSEG Long Island's MySmartEnergy FAQ states customers can "download data information in CSV or Green Button (.XML) format," which is Download My Data behind a customer login, not Connect My Data. There is no documented programmatic third-party access to customer usage data — in the New Jersey BPU AMI docket PSE&G described manual secondary-user sharing, a Letter of Authorization with spreadsheets emailed back, and EDI for BPU-licensed suppliers. Grid data is equally closed: the PSE&G NJ and PSEG Long Island outage maps are vendor-hosted KUBRA StormCenter applications with no published data API. Open market data for this territory comes from PJM and the EIA, not from PSEG.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/pseg/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/pseg/refs/heads/main/apis.yml)

## Tags

- Energy
- United States
- Utilities
- Electricity
- Gas
- Smart Metering
- Green Button
- Grid
- New Jersey

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

No public APIs are documented by PSEG. See [review.yml](review.yml) for every URL probed and the result.

## Energy Data Posture

- **Home market:** United States (New Jersey via PSE&G; Long Island, New York via PSEG Long Island)
- **Mandate regime:** `green-button-voluntary` — no US federal consumer energy data mandate. The New Jersey BPU's PSE&G AMI proceeding directs Green Button-referenced meter data sharing with non-discriminatory third-party access, which is a state regulatory direction rather than a consumer data right.
- **Mandate status:** `live-claimed-unverified` — Green Button **Download My Data** is documented in PSEG Long Island's public MySmartEnergy FAQ but reachable only after a customer login, so it could not be verified anonymously, and no Green Button Alliance certification listing names PSEG. Green Button **Connect My Data** is verifiably absent.
- **Data standard:** Green Button / NAESB REQ.21 ESPI, Download My Data profile only, as a CSV/XML file export. No version published. Legacy retail-choice EDI for licensed third-party suppliers.
- **Consumer data API:** No. Customer usage data leaves PSEG only as a self-service file download, a view-only secondary user inside MyMeter/MySmartEnergy, a Letter of Authorization answered with emailed spreadsheets, or EDI.
- **Market data open:** No. The PSE&G NJ and PSEG Long Island outage maps are KUBRA StormCenter applications hosted at kubra.io with no documented data API. PJM and the U.S. EIA publish the open data for this footprint.
- **Access gate:** `customer-account-required` — no signup, no keys, no application form, no sandbox. You must be a customer and log in at `nj.myaccount.pseg.com`.
- **Auth model:** Session login only. No OAuth 2.0, no API keys, no mTLS, and no OpenID Connect discovery document served on any probed host.

## Artifacts

Everything below is a probe record. Nothing was generated to fill a gap.

- [`well-known/pseg-well-known.yml`](well-known/pseg-well-known.yml) — eight hosts × the full `/.well-known/` discovery set. **Result: none.** Read the note: the Sitecore-hosted PSEG sites answer extensionless `/.well-known/` paths with HTTP 200 and an HTML page, a soft 404. Every 200 was opened and confirmed to be HTML, never a document. No `WellKnown` pointer is wired in `apis.yml`, because there is no well-known surface to point at.
- [`packages/pseg-packages.yml`](packages/pseg-packages.yml) — zero first-party SDKs. `github.com/PSEGLI` is a genuine PSEG Long Island GitHub organization (contact `DL-PSEGLI-GitHub-Support@pseg.com`, created 2018) with **zero public repositories**; there is no parent-company org. The only code that exists is community work that logs in as the customer: the PyPI `pseg` gas-meter utility (unmaintained since 2019) and the `ha-psegli` Home Assistant integration (actively maintained).
- [`security/pseg-domain-security.yml`](security/pseg-domain-security.yml) — TLS 1.3, HSTS with a one-year max-age, SPF and DMARC at `p=reject` on both `pseg.com` and `psegliny.com`; no DNSSEC and no CAA on either. Solid mail and transport hygiene, no DNS hardening.
- [`llms/pseg-llms.txt`](llms/pseg-llms.txt) — generated, because PSEG serves no `/llms.txt` on any host. Written for the agent that arrives looking for a PSEG API: it leads with what does not exist, then the four human-mediated routes to customer data, then points at PJM and the EIA for the data that is actually open.

No vulnerability-disclosure policy, bug bounty or trust center was found — `/security`, `/cybersecurity` and `/responsible-disclosure` all soft-404, no `security.txt` on any host, and no HackerOne/Bugcrowd/Intigriti program. Nothing was written for those rather than record an absence as a program.

## Properties

- [Website](https://www.pseg.com/)
- [Website — PSEG Long Island](https://www.psegliny.com/)
- [About](https://corporate.pseg.com/)
- [Blog](https://corporate.pseg.com/newsroom)
- [LinkedIn](https://www.linkedin.com/company/pseg)
- [GitHubOrganization](https://github.com/PSEGLI) — PSEG Long Island, zero public repositories
- [Login](https://nj.myaccount.pseg.com/user/login)
- [Support](https://nj.myaccount.pseg.com/customersupport) — PSE&G New Jersey
- [Support](https://www.psegliny.com/en/myaccount/customersupport) — PSEG Long Island
- [TermsOfService / PrivacyPolicy](https://corporate.pseg.com/websitetermsandconditions) — both live on one page; the privacy policy was last updated 2025-01-15
- [Rates](https://nj.pseg.com/aboutpseg/regulatorypage/electrictariffs) — filed electric tariffs, not data
- [Documentation](https://www.psegliny.com/myaccount/serviceandrates/mysmartenergy) — MySmartEnergy FAQ, the Green Button (.XML) download reference
- [Documentation](https://nj.myaccount.pseg.com/myservicepublic/smartmeters) — PSE&G NJ smart meters and MyMeter

## Maintainers

- Kin Lane — kin@apievangelist.com
